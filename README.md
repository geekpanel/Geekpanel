<h1>Geek Panel Free Linux Web Hosting Control Panel</h1>

Install Geek Panel via command line:

curl -o latest -L https://download.geekpanel.com && chmod +x latest && ./latest

Install Geek Panel (Lite) via command line:

curl -o latest -L https://download.geekpanel.com && chmod +x latest && ./latest lite

Demo:

http://demo.geekpanel.com:2020

https://demo.geekpanel.net/gp

<h2>How to Restore Full cPanel Backup via Geek Panel?</h2>
The first method is to restore the full cPanel backup via Geek Panel. Of course, in order to be able to restore the backup using this method you need to have root access to Geek Panel which is listening on port 2020. So if your domain is example.com, you can access Geek Panel via web browser at http://example.com:2020.
Once you log in to Geek Panel, navigate to Backups and then select Restore a Full Backup. This Geek Panel feature will allow you to restore specific backup with File.
To restore with file, you must upload the full cPanel backup file to the following directory:
/backup

Restore Full cPanel Backup via command line. Yes, this is another method which some server admins find much easier than the first one. For this method you need to have SSH access to the server. Connect to your Linux server via SSH and run the following command as root:

/gp/restore username

or

/gp/restore filename.tar.gz

Of course, you need to replace username with the actual cPanel username or filename.tar.gz for the account you want to restore. Also, make sure that the full cPanel backup is properly uploaded in the /backup directory on your server before starting the restoration process.

<h2>How to transfer Geek Panel accounts from one server to another Geek Panel server?</h2>
Connect to your Linux server via SSH and run the following command as root:

/gp/backup all full scp RemoteIP root RemotePassword 22 /backup

<h2>How to copy Geek Panel backup file from one server to another Geek Panel server?</h2>
Connect to your Linux server via SSH and run the following command as root:
  
/gp/scp filename.tar.gz RemoteIP RemotePassword
  
Or
  
/gp/scp all RemoteIP RemotePassword

<h2>How to Copy Folder from Geek Panel Server to Remote Backup Server(Storage Box)?</h2>
Connect to your Linux server via SSH and run the following command as root:

/gp/backup LocalFolderPath RemoteFolderPath

Example:

/gp/backup /home/ /backup/home/

(Setup Schedule Backup Required via Dashboard)
