---
description: Guida rapida per diversi metodi di trasferimento file in DWB.
title: Governance del trasferimento dei file
uuid: a3e19f8a-1cc4-437c-9661-408f675109c0
exl-id: a0ecd8e1-6d6f-4811-9869-092837dc9e55
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 1%

---

# Governance del trasferimento dei file{#file-transfer-governance}

{{eol}}

Guida rapida per diversi metodi di trasferimento file in DWB.

La governance del trasferimento dei file è un processo standard per trasferire i file da una directory interna a qualsiasi altro server o movimento interno di file.

## Metodi di trasferimento file diversi {#section-972bb39ba1954c6ebd35f6d042593efe}

1. AWS (Amazon Web Services)

   1. Crea un ticket per installare l’interfaccia della riga di comando di AWS sul server se non è già installato (vedi [https://docs.aws.amazon.com/cli/latest/userguide/installing.html](https://docs.aws.amazon.com/cli/latest/userguide/installing.html)).
   1. Come controllare? Prova a configurare AWS utilizzando il prompt dei comandi (vedi [https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html)).

1. Trasferisci i file dal server FTP alla directory NAS.

   1. Feed offline FTP dal server ftp alla directory NAS. I dettagli riportati di seguito sono necessari per l&#39;FTP.

      ftp_username

      ftp_password

      ftp_port

      indirizzo_ftp

      ftp_directory

      delete_ftp_files

      ftp_file_extension

      local_directory

      (I dettagli FTP saranno disponibili nella lista di controllo del progetto. Utilizzare l&#39;utente ftp esterno per trasferire i file)

   1. Utilizza lo script ftp_winscp_get.pl allegato di seguito e la pianificazione in base ai requisiti.

      ftp_winscp_get.pl

      Questo script deve essere posizionato in E:\scripts\Scripository\Library\Perl

      >[!NOTE]
      >
      >Se la cartella di archivio non è disponibile, vedi [Rielaborazione settimanale](../../../home/dwb-implement-overview/dwb-implement-configure/dwb-implement-reprocess-scripting.md#concept-60529e12d6d94386a02c1c6fdedf0295) per scaricare la cartella.

   1. Pianifica lo script in base alla disponibilità dei file su ftp_address.
   1. La convenzione di denominazione del file deve essere YYYYMMDD-&lt;offline_feed_name>-00.&#42;

1. Trasferisci i file dalla directory NAS al server FTP.

   1. Utilizza lo script ftp_winscp_put.pl e la pianificazione in base ai requisiti.

      Questo script deve essere posizionato in E:\scripts\Scripository\Library\Perl

      Per eseguire lo script sono necessari i dettagli riportati di seguito.

      ftp_username

      ftp_password

      ftp_port

      indirizzo_ftp

      ftp_directory

      delete_ftp_files

      ftp_file_extension

      local_directory

      ```
      #######################################################################################################################
      # PLUGIN NAME HERE
      my $pluginname = "FTP WinSCP";
      # 20140421 Script tp put files on the FTP
      #######################################################################################################################
      # INCLUDE SCRIPOSITORY CORE
      use FindBin;                 # locate this script
      BEGIN {push @INC, $FindBin::Bin}
      require 'core.pl';
      
         # check for the required parameters
       GetOptions('local_directory:s'     => \$local_directory,
                     'source_file_pattern:s' => \$source_file_pattern,
                     'ftp_file_extension:s' => \$ftp_file_extension,
                     'ftp_address=s'  => \$ftp_address,
                     'ftp_username=s'  => \$ftp_username,
                     'ftp_password:s'  => \$ftp_password,
                     'ftp_port:s'   => \$ftp_port,
                     'ftp_directory:s'     => \$ftp_directory,
           'log_directory:s'  => \$log_directory,
                     'error_directory:s'  => \$error_directory,
                     'mail_from:s'  => \$mail_from,
                     'mail_to:s'   => \$mail_to,
                     'host:s'   => \$host,
                     'trigger_directory:s' => \$trigger_directory,
                     'trigger_file_extension:s' => \$trigger_file_extension,
                     'delete_ftp_files:s'  => \$delete_ftp_files,);
      
       # FOR LEFT OVER PARAMS, WE CAN CHECK GLOBAL PARAMS
       check_parameters(@argv);
      
       my $ftp_winscp_script = "winscpscript.txt";
       if (index($trigger_file_extension, '.') != -1) {
        my @trigger_file_extension1=split(/\./,$trigger_file_extension,2);
        $trigger_file_extension =  $trigger_file_extension1[1];
       }
       if (index($ftp_file_extension, '.') != -1) {
        my @ftp_file_extension1=split(/\./,$ftp_file_extension,2);
        $ftp_file_extension =  $ftp_file_extension1[1];
       }
       if ($trigger_file_extension ne "_empty_" && $trigger_directory ne "_empty_") {
         print $trigger_file_extension;
        my $ftp_winscp_trigger_script = "winscpscript_trigger.txt";
        create_winscp_script($ftp_winscp_trigger_script,$ftp_port,$ftp_username,$ftp_password,$ftp_address,$trigger_directory,$ftp_directory,$delete_ftp_files,"*",$trigger_file_extension);
        sleep(10);
        system("\"E:\\Scripts\\Scripository\\Library\\WinSCP\\WinSCP.exe\" /console /script=$ftp_winscp_trigger_script /log=$logfile");
        $files = getFiles($trigger_directory,$trigger_file_extension,$days_ago,$months_ago);
        my $ftp_file_pattern="";
        my $numberoffiles = @$files;
        my $i=0;
        foreach my $trigger_file(@$files) {
         $i++;
         my $file_string=substr($trigger_file,length($trigger_directory), length($trigger_file)-length($trigger_directory));
         my @file_string1=split(/\./, $file_string, 2);
         if ($i == $numberoffiles) {
          $ftp_file_pattern.=$file_string1[0].".".$ftp_file_extension;
         }
         else {
          $ftp_file_pattern.=$file_string1[0].".".$ftp_file_extension.", ";
         }
      
        }
      
        #unlink($ftp_winscp_trigger_script);
        print $local_directory;
        print $trigger_directory;
        create_winscp_script($ftp_winscp_script,$ftp_port,$ftp_username,$ftp_password,$ftp_address,$local_directory,$ftp_directory,$delete_ftp_files,$ftp_file_pattern, "");
        runLogger("$pluginname: Sleeping for 10 sec to give enough time for the temp script to be available");
        sleep(10);
        runLogger("$pluginname: FTP started");
        system("\"E:\\Scripts\\Scripository\\Library\\WinSCP\\WinSCP.exe\" /console /script=$ftp_winscp_script /log=$logfile");
        runLogger("$pluginname: FTP ended");
      
       }
       else {
        if ($source_file_pattern eq "_empty_") {
         $source_file_pattern="*";
        }
        else {
         if (index($source_file_pattern, '.') != -1) {
          my @source_file=split(/\./,$source_file_pattern,2);
          $source_file_pattern =  $source_file[0];
         }
        }
        $ftp_file_extension=".".$ftp_file_extension;
      print $local_directory;
        create_winscp_script($ftp_winscp_script,$ftp_port,$ftp_username,$ftp_password,$ftp_address,$local_directory,$ftp_directory,$delete_ftp_files,$source_file_pattern,$ftp_file_extension);
        runLogger("$pluginname: Sleeping for 10 sec to give enough time for the temp script to be available");
        sleep(10);
        runLogger("$pluginname: FTP started");
        system("\"E:\\Scripts\\Scripository\\Library\\WinSCP\\WinSCP.exe\" /console /script=$ftp_winscp_script /log=$logfile");
        runLogger("$pluginname: FTP ended");
       }
       unlink($ftp_winscp_script);
      
      sub create_winscp_script() {
       my ($ftp_script,$ftp_port,$ftp_username,$ftp_password,$ftp_address,$local_directory,$ftp_directory,$delete_ftp_files,$file_pattern, $file_extension) = @_;
       open (FTP, "> $ftp_script") or die "Can't open log: $!";
       print FTP "\# Automatically answer all prompts negatively not to stall\n";
       print FTP "option batch on\n\n";
       print FTP "\# Disable overwrite confirmations that conflict with the previous\n";
       print FTP "option confirm off\n\n";
       print FTP "\# Connect using a password\n";
       if ($ftp_port eq "22") {
        print FTP "open sftp://$ftp_username:$ftp_password\@$ftp_address\n\n";
       }
       else {
        print FTP "open ftp://$ftp_username:$ftp_password\@$ftp_address\n\n";
       }
       print FTP "\# Change local directory\n";
       print FTP "lcd \"$local_directory\"\n\n";
       print FTP "\# Change remote directory\n";
       if ($ftp_directory eq "_empty_") {
       }
       else {
        print FTP "cd \"$ftp_directory\"\n\n";
       }
       print FTP "\# Force binary mode transfer\n";
       print FTP "option transfer binary\n\n";
       print FTP "\# Download the file to specified directory\n";
       my @get_files=split(/,/,$file_pattern);
       foreach my $file (@get_files){
        if ($delete_ftp_files eq "Y" || $delete_ftp_files eq "Yes") {
         print FTP "put -nopreservetime -nopermissions -delete $file$file_extension\n";
      
        }
        else {
         print FTP "put -nopreservetime -nopermissions $file$file_extension\n";
      
        }
      
       }
      
       print FTP "\n\n";
       print FTP "\# Disconnect\n";
       print FTP "close\n\n";
       print FTP "\# Exit WinSCP\n";
       print FTP "exit\n\n";
       close(FTP);
       runLogger("$pluginname: creating temporary winscp file");
      
      }
      ```

   1. Pianifica lo script in base alla disponibilità dei file su ftp_address.
   1. La convenzione di denominazione del file deve essere YYYYMMDD-&lt;offline_feed_name>-00.&#42;

1. Trasferisci i file da una directory NAS ad un&#39;altra directory NAS.

   1. Copiare e incollare i file direttamente collegati a una directory NAS da un&#39;altra. Segui la procedura seguente:)

      accedere al server -> vai a Esegui -> \\server_name\E$ [viene aperta una nuova cartella che consente di copiare o spostare direttamente i file]

   1. Utilizza lo script &quot;copy_files.pl&quot; per copiare i file da un server all&#39;altro o &quot;move_files.pl&quot; per spostare i file da un server all&#39;altro. (Questi file sono disponibili in E:\scripts\Scripository)
