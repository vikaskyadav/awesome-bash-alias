# awesome-bash-alias
A curated list of awesome Bash aliases.

Website: https://vikaskyadav.github.io/awesome-bash-alias/

__# Calculator__
```bash
alias bc="bc -l"
```

__# Clear__
```bash
alias c="clear"
```
```bash
alias cl="clear"
```
```bash
alias ckear="clear"
```
```bash
alias clr="clear"
```

__# Change Directories__
```bash
alias .="cd .."
```

```bash
alias ..="cd ../.."
```
```bash
alias ...="cd ../../.."
```
```bash
alias ....="cd ../../../.."
```
```bash
alias .....="cd ../../../../.."
```

### OR

```bash
alias ..="cd .."
```
```bash
alias ...="cd ../.."
```
```bash
alias ....="cd ../../.."
```
```bash
alias .....="cd ../../../.."
```
```bash
alias ......="cd ../../../../.."
```

```bash
alias .1="cd .."
```
```bash
alias .2="cd ../.."
```
```bash
alias .3="cd ../../.."
```
```bash
alias .4="cd ../../../.."
```
```bash
alias .5="cd ../../../../.."
```

```bash
alias ..1="cd .."
```
```bash
alias ..2="cd ../.."
```
```bash
alias ..3="cd ../../.."
```
```bash
alias ..4="cd ../../../.."
```
```bash
alias ..5="cd ../../../../.."
```

```bash
alias cd..="cd .."
```
```bash
alias cd...="cd ../.."
```
```bash
alias cd....="cd ../../.."
```
```bash
alias cd.....="cd ../../../.."
```
```bash
alias cd......="cd ../../../../.."
```

```bash
alias cd1="cd .."
```
```bash
alias cd2="cd ../.."
```
```bash
alias cd3="cd ../../.."
```
```bash
alias cd4="cd ../../../.."
```
```bash
alias cd5="cd ../../../../.."
```

__# useful Docker functions__

```bash
 dock-run()  { sudo docker run -i -t --privileged $@ ;}
```
```bash
 dock-exec() { sudo docker exec -i -t $@ /bin/bash ;}
```
```bash
 dock-log()  { sudo docker logs --tail=all -f $@ ;}
```
```bash
 dock-port() { sudo docker port $@ ;}
```
```bash
 dock-vol()  { sudo docker inspect --format '{{ .Volumes }}' $@ ;}
```
```bash
 dock-ip()   { sudo docker inspect --format '{{ .NetworkSettings.IPAddress }}' $@ ;}
```
```bash
 dock-rmc()  { sudo docker rm `sudo docker ps -qa --filter 'status=exited'` ;}
```
```bash
 dock-rmi()  { sudo docker rmi -f `sudo docker images | grep '^<none>' | awk '{print $3}'` ;}
```
```bash
 dock-stop() { sudo docker stop $(docker ps -a -q); }
```
```bash
 dock-rm()   { sudo docker rm $(docker ps -a -q); }

*dock-do() {
   if [ "$#" -ne 1 ]; then
      echo "Usage: $0 start|stop|pause|unpause|<any valid docker cmd>"
   fi

   for c in $(sudo docker ps -a | awk '{print $1}' | sed "1 d")
   do
       sudo docker $1 $c
   done
}
```

__# Kubernetes commands__

```bash
alias k="kubectl"
```
```bash
alias ka="kubectl apply -f"
```
```bash
alias kpa="kubectl patch -f"
```
```bash
alias ked="kubectl edit"
```
```bash
alias ksc="kubectl scale"
```
```bash
alias kex="kubectl exec -i -t"
```
```bash
alias kg="kubectl get"
```
```bash
alias kga="kubectl get all"
```
```bash
alias kgall="kubectl get all --all-namespaces"
```
```bash
alias kinfo="kubectl cluster-info"
```
```bash
alias kdesc="kubectl describe"
```
```bash
alias ktp="kubectl top"
```
```bash
alias klo="kubectl logs -f"
```
```bash
alias kn="kubectl get nodes"
```
```bash
alias kpv="kubectl get pv"
```
```bash
alias kpvc="kubectl get pvc"
```

__# Docker commands__

```bash
alias dl="sudo docker ps -l -q"
```
```bash
alias dps="sudo docker ps"
```
```bash
alias di="sudo docker images"
```
```bash
alias dip="sudo docker inspect --format '{{ .NetworkSettings.IPAddress }}'"
```
```bash
alias dkd="sudo docker run -d -P"
```
```bash
alias dki="sudo docker run -i -t -P"
```
```bash
alias dex="sudo docker exec -i -t"
```
```bash
alias drmf='sudo docker stop $(sudo docker ps -a -q) && sudo docker rm $(sudo docker ps -a -q)'
```

__# Estimate file space usage to maximum depth__

```bash
alias du1="du -d 1"
```

__# Git commands__

```bash
alias gs="git status"
```
```bash
alias gst="git status -sb"
```
```bash
alias gl="git log"
```
```bash
alias ga="git add"
```
```bash
alias gaa="git add -A"
```
```bash
alias gal="git add ."
```
```bash
alias gall="git add ."
```
```bash
alias gca="git commit -a"
```
```bash
alias gc="git commit -m"
```
```bash
alias gcot="git checkout"
```
```bash
alias gchekout="git checkout"
```
```bash
alias gchckout="git checkout"
```
```bash
alias gckout="git checkout"
```
```bash
alias go="git push -u origin"
```
```bash
alias gsh='git stash'
```
```bash
alias gw='git whatchanged'
```
```bash
alias gitlg="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```
```bash
alias nah="git clean -df && git checkout -- ."
```

__# History commands__

```bash
alias h="history"
```
```bash
alias h1="history 10"
```
```bash
alias h2="history 20"
```
```bash
alias h3="history 30"
```
```bash
alias hgrep='history | grep'
```

__# List commands__

```bash
alias l="ls"
```
```bash
alias l='ls -lAh'
```
```bash
alias ls="ls -a"
```
```bash
alias la="ls -a"
```
```bash
alias ll="ls -al"
```

__# Ping Commands__

```bash
alias pg="ping google.com -c 5"
```
```bash
alias pt="ping facebook.com -c 5"
```
```bash
alias ping="ping -c 5"
```
```bash
alias fastping="ping -c 100 -s.2"
```

__# Exit Command__

```bash
alias :q="exit"
```
```bash
alias ext="exit"
```
```bash
alias xt="exit"
```
```bash
alias by="exit"
```
```bash
alias bye="exit"
```
```bash
alias die="exit"
```
```bash
alias quit="exit"
```

__# Launch Simple HTTP Server__

```bash
alias serve='python -m SimpleHTTPServer'
```

__# Confirmation__

```bash
alias mv='mv -i'
```
```bash
alias cp='cp -i'
```
```bash
alias ln='ln -i'
```
```bash
alias rm='rm -I --preserve-root'
```

__# Parenting changing perms on /__

```bash
alias chown='chown --preserve-root'
```
```bash
alias chmod='chmod --preserve-root'
```
```bash
alias chgrp='chgrp --preserve-root'
```

__# Install & Update utilties__

```bash
alias sai="sudo apt install"
```
```bash
alias sai="sudo apt-get install"
```
```bash
alias sau="sudo apt update"
```
```bash
alias sau="sudo apt-get update"
```
```bash
alias update="sudo apt update"
```
```bash
alias update="yum update"
```
```bash
alias updatey="yum -y update"
```

__# System state__

```bash
alias reboot="sudo /sbin/reboot"
```
```bash
alias poweroff="sudo /sbin/poweroff"
```
```bash
alias halt="sudo /sbin/halt"
```
```bash
alias shutdown="sudo /sbin/shutdown"
```
```bash
alias flighton='sudo rfkill block all'
```
```bash
alias flightoff='sudo rfkill unblock all'
```
```bash
alias snr='sudo service network-manager restart'
```

__# Show open ports__
```bash
alias ports='sudo netstat -tulanp'
```

__# Free and Used__

```bash
alias meminfo="free -m -l -t"
```

__# Get top process eating memory__

```bash
alias psmem="ps auxf | sort -nr -k 4"
```
```bash
alias psmem10="ps auxf | sort -nr -k 4 | head -10"
```

__# Get top process eating cpu__

```bash
alias pscpu="ps auxf | sort -nr -k 3"
```
```bash
alias pscpu10="ps auxf | sort -nr -k 3 | head -10"
```

__# Get details of a process__
```bash
alias paux='ps aux | grep'
```

__# Get server cpu info__

```bash
alias cpuinfo="lscpu"
```

__# Older system use /proc/cpuinfo__

```bash
alias cpuinfo="less /proc/cpuinfo"
```

__# Get GPU ram on desktop / laptop__

```bash
alias gpumeminfo="grep -i --color memory /var/log/Xorg.0.log"
```

__# Resume wget by default__

```bash
alias wget="wget -c"
```

__# Grabs the disk usage in the current directory__

```bash
alias usage='du -ch | grep total'
```

__# Gets the total disk usage on your machine__

```bash
alias totalusage='df -hl --total | grep total'
```

__# Shows the individual partition usages without the temporary memory values__

```bash
alias partusage='df -hlT --exclude-type=tmpfs --exclude-type=devtmpfs'
```

__# Gives you what is using the most space. Both directories and files. Varies on current directory__

```bash
alias most='du -hsx * | sort -rh | head -10'
```

__# MacOs commands__

```bash
alias rp='. ~/.bash_profile'
```
```bash
alias myip='ifconfig en0 | grep inet | grep -v inet6 | cut -d ' ' -f2'
```
