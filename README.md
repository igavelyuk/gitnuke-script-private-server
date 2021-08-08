# gitnuke-script-private-server
Git init script for private server repo

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
