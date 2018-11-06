# bw-backup
A simple wrapper around rsync for easily doing or restoring small backups

Usage: /usr/bin/tb push|pull|info|help
       /usr/bin/tb init|pushonce [remote-user@remote-host:remote-path]

       The program /usr/bin/tb will push/pull data to/from remote site
       according to configured settings.

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

