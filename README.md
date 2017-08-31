# bashscripts
Some more or less useful bash scripts I wrote.

Most scripts were written (and sometimes even tested ...) on [Ubuntu MATE](https://ubuntu-mate.org/) 16.04 with [i3wm](https://i3wm.org/).

**Remark:**

These bash scripts were obviously written with **my** system in mind and may not run equally flawless on every other system. Although I tried to write them as universally applicable or at least easily adaptable as possible, there are always some assumptions about the context they are executed in (e.g. see [caveats](#install-caveats) for the install script).
Some standard variables may be a bit Ubuntu-centric and some scripts (e.g. [signal-messenger](#signal-messenger) and [togtouch](#togtouch) ) may only be useful if you have a keyboard-heavy workflow like using i3wm with dmenu.

## <code>install</code> script
Script to "install" bash scripts to a directory via symlinks.

<code>install -h</code> will print usage information

The script will make the files specified in the <code>script_list</code> var executable and create symlinks to them in the directory specified in the <code>bin_dir</code> var. It also checks if <code>bin_dir</code> is in the <code>$PATH</code> and reminds the user to add it to <code>$PATH</code> if not.

If a symlink with the same name already exists in the <code>bin_dir</code>, the script will check if it links to the same location. If it does not, the script will **not** overwrite the link and ask to be rerun with the <code>-f</code> (force) flag to finish this particular operation.
### <a name="install-caveats">Caveats</a>
This script is very simple and does not cope very well with weird file names or directories. "Weird" means special characters and especially whitespaces. Rule of thumb: If you have to put a filename or path in quotes when you issue a command with it as an argument in a standard bash, it's definitely weird. Other than that, it seems quite robust as of now.

If it ever comes to a situation where I knowingly and willingly created file names or paths with whitespaces in them, I would need to sit down and rethink my life anyways.

## <code><a name="signal-messenger">signal-messenger</a></code> script
Script to start "Signal Private Messenger" Chrome extension via command line without attaching it to the terminal.

<code>signal-messenger -h</code> will print usage information

## <code><a name="togtouch">togtouch</a></code> script
Bash script to toggle the touchpad on /off

TODO requires, limitations

