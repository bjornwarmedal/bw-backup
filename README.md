# bw-backup
A simple wrapper around rsync for easily doing or restoring small backups

The program has only one setting, defining the remote mirror of your repo. This setting is placed in a file called .backupconf, which in turn is placed at the root of the file tree you wish to backup.

Usage:

       bw-backup push|pull|info|help
       bw-backup init|pushonce [remote-user@remote-host:remote-path]

       OPTIONS:
       push
             Runs rsync to preset remote destination.
       pull
             Runs rsync from preset remote destination.
       info
             Prints settings for the current repository.
       help
             Prints this text and exits.
       init [remote-user@remote-host:remote-path]
             Initiates a new repository in the current
             working directory, verifying that the remote
             destination exists - and creating it if needed.
       pushonce [remote-user@remote-host:remote-path]
             Does not set up a repository, or even check if
             one already exists. Instead only does one push. 
	     Notably this command does NOT use the --delete
	     flag to rsync, and will thereby never erase data
	     in the remote destination (though it may override
	     with local files of the same name).

