GIT ENVIROMENT SETTINGS

#
PS1 > to see branches

link: https://ru.hexlet.io/blog/posts/kak-prisoedinitsya-k-rabote-nad-opensorsom-chto-takoe-ps1-i-drugie-voprosy-otvechaet-razrabotchik-heksleta-andrey-moshkov#chto-takoe-ps1-i-dlya-chego-ispolzuetsya
#
shortly:
#
GitBash:

in terminal > export PS1="💻 \[\e[1;34m\]\W\[\e[m\]\[\033[32m\]\$(__git_ps1)\[\033[00m\] $ "

if error:

in ternminal > export PS1="\W ($(git branch 2>/dev/null | grep '^*' | colrm 1 2)) $ "
#
Ubuntu:

in terminal (in .bashrc file) >

if ! shopt -oq posix; then

 if [ -f /usr/share/bash-completion/bash_completion ]; then

   . /usr/share/bash-completion/bash_completion

 elif [ -f /etc/bash_completion ]; then

   . /etc/bash_completion

 fi

fi
#
MacOS:

sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

or:

if [ -f /usr/local/share/bash-completion/bash_completion ]; then . /usr/local/share/bash-completion/bash_completion fi
#
