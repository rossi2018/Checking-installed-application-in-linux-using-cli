## Every once in a while , we love to check the installed application in linux operaring system(in my own case its debian base os:ubuntu)
To list all installed application in ubuntu installed via apt manager use this command 

`$ apt list --installed`

To filter for a particular result of application you searching for, use grep like this

`$ apt list --installed | grep <name of application>`

To list package installed using dpkg (which stands for debian package manager). Dpkg command will list virtually all packages installed in the system which you installed and the ones that was already installed as well. Use this command

`$ dpkg-query -l`

You can filter out for a specific application using grep like this

`$ dpkg-query -l | grep <name of application> `

To show all the snap packages installed in your system use this command

`$ sanp list`

When yo want to list recently installed packages. You do in two ways. The first method is using the dpkg way where you search for it in the log file this way 

$

