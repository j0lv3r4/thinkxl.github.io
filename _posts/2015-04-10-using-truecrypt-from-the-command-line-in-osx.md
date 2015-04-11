---
layout: post
title: Using TrueCrypt from the command line in OSX 
tag:
- Crypto
author: Juan Olvera
twitter: thinkxl
---

### About TrueCrypt

As you may know, on May 2014, TrueCrypt developers announced that the the project was discontinued and will no longer receive any updates and fixes. But before this happened [Kenneth White]() and [Matthew Green]() planned, crowd-sourced, and executed an [independent full-level](http://istruecryptauditedyet.com/) [security audit](http://blog.cryptographyengineering.com/2015/04/truecrypt-report.html).

Which **TL;DR** is *"The NCC audit found no evidence of deliberate backdoors, or any severe design flaws that will make the software insecure in most instances"*.

This means that it's OK to keep using TrueCrypt 7.1a.

### Installation

1. Download the **TrueCrypt 7.1a Mac OS X.dmg** file from [here](https://www.grc.com/misc/truecrypt/truecrypt.htm).
2. Open the `.dmg` file and double click the `.mpkg` installer.

### Yosemite Issue

If you are using Yosemite you will get this error and the installation blocked.

![TrueCrypt error](https://lazymind.me/images/truecrypt-install-error.png)

For some reason TrueCrypt thinks 10.10 is less than 10.4.

### Fix

1. Open the `.dmg`.
2. Copy the content inside to a different location (the `.dmg` file is read only).
3. Once you got your files inside something like `~/Downloads/TrueCrypt/`, open the `.mpkg` package contents, then the `/Contents` folder.
4. Open the `distribution.dis` file with a text editor.
5. Remove lines from 13 to 18.

![](http://i.stack.imgur.com/UEruB.png)

6. Save the file and open the `.mpkg`.

*Sources*: 

- [http://apple.stackexchange.com/questions/173879/truecrypt-7-1a-requires-mac-os-x-10-4-or-later-on-yosemite-10-10](http://apple.stackexchange.com/questions/173879/truecrypt-7-1a-requires-mac-os-x-10-4-or-later-on-yosemite-10-10)
- [https://lazymind.me/2014/10/install-truecrypt-on-mac-osx-yosemite-10-10/](https://lazymind.me/2014/10/install-truecrypt-on-mac-osx-yosemite-10-10/)
	

### Command line setup

After you install TrueCrypt you still can't use it from the Terminal, you need to put this in your `~/.bashrc` or `~/.bash_profile`:

{% highlight bash %}
alias truecrypt='/Applications/TrueCrypt.app/Contents/MacOS/Truecrypt --text'
{% endhighlight %}

Then it will be ready to use:

{% highlight bash %}
$ truecrypt

Usage: Truecrypt [--auto-mount <str>] [--backup-headers] [--background-task] [-C] [-c] [--create-keyfile] [--delete-token-keyfiles] [-d] [--display-password] [--encryption <str>] [--explore] [--export-token-keyfile] [--filesystem <str>] [-f] [--hash <str>] [-h] [--import-token-keyfiles] [-k <str>] [-l] [--list-token-keyfiles] [--load-preferences] [--mount] [-m <str>] [--new-keyfiles <str>] [--new-password <str>] [--non-interactive] [-p <str>] [--protect-hidden <str>] [--protection-keyfiles <str>] [--protection-password <str>] [--random-source <str>] [--restore-headers] [--save-preferences] [--quick] [--size <str>] [--slot <str>] [--test] [-t] [--token-lib <str>] [-v] [--version] [--volume-properties] [--volume-type <str>] [Volume path] [Mount point]
{% endhighlight %}

### Basic usage:

Mount a volume:

{% highlight bash %}
$ truecrypt <file-to-encrypt> <mount-point>
{% endhighlight %}

Unmount specific volume

{% highlight bash %}
$ truecrypt -d <volume-to-unmount>
{% endhighlight %}

Unmount all volumes:

{% highlight bash %}
$ truecrypt -d
{% endhighlight %}

You can find a more complete documentation in here:

- [https://wiki.archlinux.org/index.php/TrueCrypt](https://wiki.archlinux.org/index.php/TrueCrypt)

Related links:

- [https://www.grc.com/misc/truecrypt/truecrypt.htm](https://www.grc.com/misc/truecrypt/truecrypt.htm)
- [http://marc-abramowitz.com/archives/2011/10/17/easy-access-to-truecrypt-from-the-command-line-in-os-x/](http://marc-abramowitz.com/archives/2011/10/17/easy-access-to-truecrypt-from-the-command-line-in-os-x/)
- [http://polishlinux.org/howtos/truecrypt-howto/](http://polishlinux.org/howtos/truecrypt-howto/)
