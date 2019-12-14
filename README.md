# How to Setup ZSH and Oh-my-zsh on Linux

Oh-my-zsh
Prerequisites
What we will do
Step 1 - Install and configure ZSH
Step 2 - Install and configure Oh-my-zsh framework
Step 3 - Change default themes
Step 4 - Enable Oh-my-zsh plugins

### References
The Z shell or zsh is an interactive UNIX shell and a powerful command line interpreter for scripting languages, including shell scripting. Zsh was developed by 'Paul Fastad' since 1990, and the name 'zsh' comes from the Yale professor Zong Shao.

The Z-Shell has become one of the most popular shells for the Linux operating system. It is rich in features and easy to configure and customize. Below are some important zsh functions:

Command auto-complete
Improved variable handling
Spelling correction
Shared command history
Kill tab completion
Environment variable easy setup
Customizable
Oh-my-zsh
Oh-my-zsh is an open source framework for managing ZSH, the Z shell. There are also other frameworks for the Z shell, such as prezto, Zgen, Antigen, etc. In this tutorial, we use 'oh-my-zsh' for our zsh configuration.

Oh-my-zsh is a community-based framework with many functions. It comes with a customizable design and has an extensive catalog of plugins aimed at system administrators and developers.

In this tutorial we show you how to install the Z-Shell or zsh under Ubuntu Linux and CentOS. Then we configure the oh-my-zsh framework for managing zsh. We will also show you how to change the zsh theme and activate plugins.

Prerequisites
Linux - Ubuntu 16.04 or CentOS 7.6
Root privileges
What we will do
Install and configure ZSH
Install and configure Oh-my-zsh framework
Change default theme
Enable oh-my-zsh plugins

## Step 1 - Install and configure ZSH
In this step, we will install the Z shell from the repository, and then configure a user to use the Z shell as the default theme. Basically, the default shell on Ubuntu and CentOS is bash, so we will configure a root user to use zsh as the default shell.

To install zsh from the repository, use the following commands.

login to root
```
$ sudo -i
```

On Ubuntu:
```
$ apt install zsh
```

On CentOS:
```
$ yum install zsh
```

After the installation is complete, change the default shell of the root user to zsh with the chsh command below.

On Ubuntu:
```
$ chsh -s /usr/bin/zsh root
```

On CentOS:
```
$ chsh -s /bin/zsh root
```

Now logout from the root user, log in again, and you will get the zsh shell.

```
$ exit
```

Check the current shell used with the command below.
```
echo $SHELL
```

The output should be zsh. Here's the result on Ubuntu.

Change shell to zsh on Ubuntu

And here's the result on CentOS.

Change shell to zsh on centOS

The Z shell zsh has been installed.

## Step 2 - Install and configure Oh-my-zsh framework
So the Z shell is now installed on the system. Next, we want to install the oh-my-zsh framework for managing the Z shell zsh. Oh-my-zsh provides an installer script for installing the framework, and we need to install some other required packages, including wget for downloading the installer script and Git for downloading oh-my-zsh shell from GitHub.

So the first step is to install wget and git on the system. Here are the commands you need to run:

On Ubuntu:
```
$ apt install wget git
```

On CentOS:
```
$ yum install wget git
```

Now download the installer script and execute it.
```
$ wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh
```

The result/output should be similar to the one shown below.

Install Oh-my-zsh

So, oh-my-zsh is installed in the home directory '~/.oh-my-zsh'.

Next, we need to create a new configuration for zsh. As with the Bash shell, which has a configuration named '.bashrc', for zsh, we need a '.zshrc' configuration file. It's available in the oh-my-zsh templates directory.

Copy the template .zshrc.zsh-template configuration file to the home directory .zshrc and apply the configuration by running the source command, as shown below.
```
$ cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
$ source ~/.zshrc
```

Oh-my-zsh is now installed on the system, and the Z shell has been configured for using the oh-my-zsh framework with default configuration.

The following result is on Ubuntu.

The Oh-my-zsh installation on Ubuntu

And here's what you'll see on CentOS.

Oh-my-zsh installation on CentOS

### Step 3 - Change default themes
The default .zshrc configuration that's provided by oh-my-zsh is using 'robbyrusell' theme. In this step, we will edit the configuration and change the default theme.

The Oh-my-zsh framework provides many themes for your zsh shell, head to the link below to take a look at the available options.
 
https://github.com/robbyrussell/oh-my-zsh/wiki/Themes

Alternatively, you can go to the 'themes' directory and see the list of available themes.
```
$ cd ~/.oh-my-zsh/themes/
$ ls -a
```

List of zsh themes

In order to change the default theme, we need to edit the .zshrc configuration file. Edit the configuration with the vim editor.
```
$ vim ~/.zshrc
```

Pick one zsh theme - let's say 'risto' theme.

Then change the 'ZSH_THEME' line 10 with 'risto' theme as below.
```
ZSH_THEME='risto'
```

Save and exit.

Now, reload the configuration .zshrc and you will see that 'risto' theme is currently used as your shell theme.
```
$ source ~/.zshrc
```

The result on Ubuntu.

reload the configuration .zshrc on Ubuntu

Result on CentOS.

reload the configuration .zshrc on CentOS

So this way, you can apply a new oh-my-zsh theme.

## Step 4 - Enable Oh-my-zsh plugins
Oh-my-zsh offers awesome plugins. There are a lot of plugins for our environment, aimed at developers, system admins, and everyone else.

Default plugins are in the 'plugins' directory.
```
$ cd ~/.oh-my-zsh/plugins/
$ ls -a
```

List available zsh plugins

In this step, we will tweak zsh using the 'oh-my-zsh' framework by enabling some plugins. In order to enable the plugins, we need to edit the .zshrc configuration file.

Edit .zshrc configuration file.
```
$ vim ~/.zshrc
```

Go to the 'plugins' line 54 and add some plugins that you want to enable inside the bracket (). For example, here's the change I made in my case:
```
plugins=(git extract web-search yum git-extras docker vagrant)
```
 
Following is the result when using the 'extract' plugin - you can extract zip and tar file using the 'extract' command.

Install the zsh extract plugin

Yum command - yum info with only 'yp' command.

yum command info

Vagrant plugin for command autocompletion.

zsh vagrant plugin

To conclude, the Z shell, as well as the oh-my-zsh framework, have been installed. In addition, oh-my-zsh default theme has been changed with some plugins enabled.
