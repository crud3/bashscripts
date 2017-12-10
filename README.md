# bashscripts

Most scripts were written (and sometimes even tested) on Ubuntu Mate 16.04.  

**Remark:**

These bash scripts were obviously written with **my** system in mind and may not run equally flawless on other systems.
There are always some assumptions about the context they are executed in (e.g. see [caveats](#install-caveats) for the "install" script) and some default values may be a bit ubuntu-centric.

If a script seems to be really unnecessary or overkill for the simple task it is accomplishing, it probably really is.

## <code>install</code> script
Script to "install" bash scripts to a directory via symlinks. 

<code>install -h</code> will print usage information

The script will make the files specified in the <code>script_list</code> var executable and create symlinks to them in the directory specified in the <code>bin_dir</code> var. It also checks if <code>bin_dir</code> is in the <code>$PATH</code> and reminds the user to add it to <code>$PATH</code> if not.

If a symlink with the same name already exists in the <code>bin_dir</code>, the script will check if it links to the same location. If it does not, the script will **not** overwrite the link and ask to be rerun with the <code>-f</code> (force) flag to finish this particular operation.
### <a name="install-caveats">Caveats</a>
This script is extremely simple and does not cope very well with weird file names or directories. "Weird" in this case means special characters and especially whitespaces.
Rule of thumb: If you have to put a filename or path in quotes when you issue a command with it as an argument, it is definitely a little weird.

## <code><a name="togtouch">togtouch</a></code> script
A very overkill bash script to toggle the touchpad on my ThinkPad on/off.

Requires xinput. Looks for a touchpad with xinput, grep and really ugly regexes,
         then tries to disable it via xinput.

