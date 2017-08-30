# bashscripts
Some more or less useful bash scripts I wrote
## install
Script to "install" bash scripts to a directory via symlinks.

The script will make the files specified in the <code>script_list</code> var executable and create symlinks to them in the directory specified in the <code>bin_dir</code> var. It also checks if <code>bin_dir</code> is in the <code>$PATH</code> and reminds the user to add it to <code>$PATH</code> if not.

If a symlink with the same name already exists in the <code>bin_dir</code>, the script will check if it links to the same location. If it does not, the script will **not** overwrite the link and ask to be rerun with the -f (force) flag to finish this particular operation.
#### Caveats
This script is very simple and does not cope very well with weird file names or directories. "Weird" means special characters and especially whitespaces. Rule of thumb: If you have to put a filename or path in quotes when you issue a command with it as an argument in a standard bash, it's definitely weird.

## signal-messenger
Script to start "Signal Private Messenger" Chrome extension via command line
