# awesome-bash-alias
A curated list of awesome Bash aliases.

Website: https://vikaskyadav.github.io/awesome-bash-alias/

__# Calculator__
* alias bc="bc -l"

__# Clear__
* alias c="clear"
* alias cl="clear"
* alias ckear="clear"
* alias clr="clear"

__# Change Directories__
* alias .="cd .."
* alias ..="cd ../.."
* alias ...="cd ../../.."
* alias ....="cd ../../../.."
* alias .....="cd ../../../../.."

### OR

* alias ..="cd .."
* alias ...="cd ../.."
* alias ....="cd ../../.."
* alias .....="cd ../../../.."
* alias ......="cd ../../../../.."

* alias .1="cd .."
* alias .2="cd ../.."
* alias .3="cd ../../.."
* alias .4="cd ../../../.."
* alias .5="cd ../../../../.."

* alias ..1="cd .."
* alias ..2="cd ../.."
* alias ..3="cd ../../.."
* alias ..4="cd ../../../.."
* alias ..5="cd ../../../../.."

* alias cd..="cd .."
* alias cd...="cd ../.."
* alias cd....="cd ../../.."
* alias cd.....="cd ../../../.."
* alias cd......="cd ../../../../.."

* alias cd1="cd .."
* alias cd2="cd ../.."
* alias cd3="cd ../../.."
* alias cd4="cd ../../../.."
* alias cd5="cd ../../../../.."

__# useful Docker functions__

* dock-run()  { sudo docker run -i -t --privileged $@ ;}
* dock-exec() { sudo docker exec -i -t $@ /bin/bash ;}
* dock-log()  { sudo docker logs --tail=all -f $@ ;}
* dock-port() { sudo docker port $@ ;}
* dock-vol()  { sudo docker inspect --format '{{ .Volumes }}' $@ ;}
* dock-ip()   { sudo docker inspect --format '{{ .NetworkSettings.IPAddress }}' $@ ;}
* dock-rmc()  { sudo docker rm `sudo docker ps -qa --filter 'status=exited'` ;}
* dock-rmi()  { sudo docker rmi -f `sudo docker images | grep '^<none>' | awk '{print $3}'` ;}
* dock-stop() { sudo docker stop $(docker ps -a -q); }
* dock-rm()   { sudo docker rm $(docker ps -a -q); }

*dock-do() {
   if [ "$#" -ne 1 ]; then
      echo "Usage: $0 start|stop|pause|unpause|<any valid docker cmd>"
   fi

   for c in $(sudo docker ps -a | awk '{print $1}' | sed "1 d")
   do
       sudo docker $1 $c
   done
}

__# Kubernetes commands__

* alias k="kubectl"
* alias ka="kubectl apply -f"
* alias kpa="kubectl patch -f"
* alias ked="kubectl edit"
* alias ksc="kubectl scale"
* alias kex="kubectl exec -i -t"
* alias kg="kubectl get"
* alias kga="kubectl get all"
* alias kgall="kubectl get all --all-namespaces"
* alias kinfo="kubectl cluster-info"
* alias kdesc="kubectl describe"
* alias ktp="kubectl top"
* alias klo="kubectl logs -f"
* alias kn="kubectl get nodes"
* alias kpv="kubectl get pv"
* alias kpvc="kubectl get pvc"

__# Docker commands__

* alias dl="sudo docker ps -l -q"
* alias dps="sudo docker ps"
* alias di="sudo docker images"
* alias dip="sudo docker inspect --format '{{ .NetworkSettings.IPAddress }}'"
* alias dkd="sudo docker run -d -P"
* alias dki="sudo docker run -i -t -P"
* alias dex="sudo docker exec -i -t"
* alias drmf="sudo docker stop $(sudo docker ps -a -q) && sudo docker rm $(sudo docker ps -a -q)"

__# Estimate file space usage to maximum depth__

* alias du1="du -d 1"

__# Git commands__

* alias gs="git status"
* alias gst="git status -sb"
* alias gl="git log"
* alias ga="git add"
* alias gaa="git add -A"
* alias gal="git add ."
* alias gall="git add ."
* alias gca="git commit -a"
* alias gc="git commit -m"
* alias gcot="git checkout"
* alias gchekout="git checkout"
* alias gchckout="git checkout"
* alias gckout="git checkout"
* alias go="git push -u origin"
* alias gsh='git stash'
* alias gw='git whatchanged'
* alias gitlg="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
* alias nah="git clean -df && git checkout -- ."

__# History commands__

* alias h="history"
* alias h1="history 10"
* alias h2="history 20"
* alias h3="history 30"
* alias hgrep='history | grep'

__# List commands__

* alias l="ls"
* alias l='ls -lAh'
* alias ls="ls -a"
* alias la="ls -a"
* alias ll="ls -al"

__# Ping Commands__

* alias pg="ping google.com -c 5"
* alias pt="ping facebook.com -c 5"
* alias ping="ping -c 5"
* alias fastping="ping -c 100 -s.2"

__# Exit Command__

* alias :q="exit"
* alias ext="exit"
* alias xt="exit"
* alias by="exit"
* alias bye="exit"
* alias die="exit"
* alias quit="exit"

__# Launch Simple HTTP Server__

* alias serve='python -m SimpleHTTPServer'

__# Confirmation__

* alias mv='mv -i'
* alias cp='cp -i'
* alias ln='ln -i'
* alias rm='rm -I --preserve-root'

__# Parenting changing perms on /__

* alias chown='chown --preserve-root'
* alias chmod='chmod --preserve-root'
* alias chgrp='chgrp --preserve-root'

__# Install & Update utilties__

* alias sai="sudo apt install"
* alias sai="sudo apt-get install"
* alias sau="sudo apt update"
* alias sau="sudo apt-get update"
* alias update="sudo apt update"
* alias update="yum update"
* alias updatey="yum -y update"

__# System state__

* alias reboot="sudo /sbin/reboot"
* alias poweroff="sudo /sbin/poweroff"
* alias halt="sudo /sbin/halt"
* alias shutdown="sudo /sbin/shutdown"
* alias flighton='sudo rfkill block all'
* alias flightoff='sudo rfkill unblock all'
* alias snr='sudo service network-manager restart'

__# Show open ports__
* alias ports='sudo netstat -tulanp'

__# Free and Used__

* alias meminfo="free -m -l -t"

__# Get top process eating memory__

* alias psmem="ps auxf | sort -nr -k 4"
* alias psmem10="ps auxf | sort -nr -k 4 | head -10"

__# Get top process eating cpu__

* alias pscpu="ps auxf | sort -nr -k 3"
* alias pscpu10="ps auxf | sort -nr -k 3 | head -10"

__# Get details of a process__
* alias paux='ps aux | grep'

__# Get server cpu info__

* alias cpuinfo="lscpu"

__# Older system use /proc/cpuinfo__

* alias cpuinfo="less /proc/cpuinfo"

__# Get GPU ram on desktop / laptop__

* alias gpumeminfo="grep -i --color memory /var/log/Xorg.0.log"

__# Resume wget by default__

* alias wget="wget -c"

__# Grabs the disk usage in the current directory__

* alias usage='du -ch | grep total'

__# Gets the total disk usage on your machine__

* alias totalusage='df -hl --total | grep total'

__# Shows the individual partition usages without the temporary memory values__

* alias partusage='df -hlT --exclude-type=tmpfs --exclude-type=devtmpfs'

__# Gives you what is using the most space. Both directories and files. Varies on current directory__

* alias most='du -hsx * | sort -rh | head -10'

__# MacOs commands__

* alias rp='. ~/.bash_profile'
* alias myip='ifconfig en0 | grep inet | grep -v inet6 | cut -d ' ' -f2'
