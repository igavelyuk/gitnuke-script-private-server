# gitnuke-script-private-server
##Git init script for private server repo

### General description

This script uses BASH and intend little improve productivity on regular tasks with git server
Made for use as private server, so you install any OS in you localhost and uses it as private git server

You can use GIGOLO to maintain easy acess to anoter server and use terminal in folder (CAJA PLUGIN) to make easy to work with.

For example if you use Debian you have ROOT user and aditionaly create GIT (git) user during install.
so you able to acces it by
```
git clone ssh://git@192.168.0.2/git/2021/yourrepo.git
```
you can use much smaller url if you really need it
as
```
git clone ssh://git@192.168.0.2/yourrepo.git
```
but for that you need special config or simply put repo in "/" ROOT folder (where located /etc folder, /bin folder, /root folder) what is not reccomended
###Script body
```bash
#! /bin/bash
echo "# Create /git/YEAR/projectname.git"
echo "# git init --bare --shared"
echo "# usage ./gitnuke.sh projectname"
ls -al "/git/2021"
cd "/git/2021"
echo "Enter git directory"
mkdir "$1.git"
cd "$1.git"
echo $(git init --bare --shared)
printf \n
echo "# INIT ON YOUR COMPUTER #"
echo "git init"
echo "git add ."
echo "git commit -m 'initial commit'"
echo "git remote add origin ssh://git@SERVERIP:PORTNUM/git/2021/yourrepo.git"
echo "----IF ERROR ONLY then SET FOLLOW----"
echo "git remote set-url origin ssh://git@SERVERIP:PORTNUM/git/2021/yourrepo.git"
echo "----IF ERROR ONLY -------------------"
echo "git push origin master"
printf "git push --set-upstream origin master \n"
echo "# LATER CLONE AS FOLLOW #"
printf "git clone ssh://git@SERVERIP:PORTNUM/git/2021/yourrepo.git \n"
echo "# GITNUKE SCRIPT IN ROOT FOLDER git repo follow #"
echo "git clone ssh://git@SERVERIP:PORTNUM/git/2021/gitnuke.git"
echo $(chown git:git /git -R)
echo "Chanhe git for real user in server @SERVERIP chenge for ip address 192.168.0.2 etc : PORTNUM - if not default /git/2021/gitnuke.git"
echo "defaul location of your gits in /git/2021"
```
