# Backup-Bash-Shell-Scripting-
Simple Shell Script The following shell script uses tar to create an archive file on a remotely mounted NFS file system. The archive filename is determined using additional command line utilities.  

# Long listing of files in $dest to check file sizes. ls -lh $dest $backup_files: a variable listing which directories you would like to backup. The list should be customized to fit your needs. 
$day: a variable holding the day of the week (Monday, Tuesday, Wednesday, etc).

This is used to create an archive file for each day of the week, giving a backup history of seven days. There are other ways to accomplish this including using the date utility. 

$hostname: variable containing the short hostname of the system. Using the hostname in the archive filename gives you the option of placing daily archive files from multiple systems in the same directory.  $archive_file: the full archive filename. 
$dest: destination of the archive file. The directory needs to be created and in this case mounted before executing the backup script. See ??? for details of using NFS.  

status messages: optional messages printed to the console using the echo utility. 

tar czf $dest/$archive_file $backup_files: the tar command used to create the archive file.  
c: creates an archive.  z: filter the archive through the gzip utility compressing the archive. 
f: output to an archive file. Otherwise the tar output will be sent to STDOUT.  
ls -lh $dest: optional statement prints a -l long listing in -h human readable format of the destination directory. 
This is useful for a quick file size check of the archive file.
This check should not replace testing the archive file.
