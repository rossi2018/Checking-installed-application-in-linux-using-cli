# Every once in a while , we love to check the installed application in linux operaring system(in my own case its debian base os:ubuntu)
## To list all installed application in ubuntu installed via apt manager use this command 

`$ apt list --installed`

To filter for a particular result of application you searching for, use grep like this

`$ apt list --installed | grep <name of application>`

To list package installed using dpkg (which stands for debian package manager). Dpkg command will list virtually all packages installed in the system which you installed and the ones that was already installed as well. Use this command

`$ dpkg-query -l`

You can filter out for a specific application using grep like this

`$ dpkg-query -l | grep <name of application> `

To show all the snap packages installed in your system use this command

`$ sanp list`

## When you want to list recently installed packages.
You do it in two ways. The first method is using the dpkg command where you search for it in the log file using grep this way 

`$ grep " install " /var/log/dpkg.log`

This will list the recent installed packages and deppedencies with date

The other way is using apt,going to apt history.log file using grep.This will only show packages installed using apt package manager excluding the depencies but the details are present in the log 

`grep " install " /var/log/apt/history.log`

When you view the history.log file (by changing directory cd /var/log/apt/history.log) it shows in detail the time,date,who installed the package using apt package manager.

## Uninstalling packages
In uninstalling packages you have to consider if its installed using apt package manager or snap 
When the package is installed using apt package.First of all search for the full name pakage using this command

`$apt list --installed`

After confirming the full name of the package, uninstall the package by using this command

`$sudo apt remove <name of application>`

This way the package is only remove without removing the dependencies. When you want to remove the package and the depedencies all together use the purge command like this 

`$sudo apt purge < name of application>

When the package is installed via snap tool. List the application first to get the full name of the package using this command 

`$snap list`

After getting the full name of the package, use this command to uninstall it

`$sudo snap remove <package name>`
 
 Lastly, when you have remove packages using apt, you can use autoremove to remove package that where automatically installed because some other package required them but, with those other packages removed, they are no longer needed. Sometimes, an upgrade will suggest that you run this command. The packages to be removed are often called "unused dependencies".Do this be using this command
  
 `sudo apt autoremove`
