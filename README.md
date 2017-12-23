# A list of publicly known but unfixed security bugs

Please submit a pull request if you have corrections or know about any other unfixed security bugs.


## tar

* [rmt filename support makes tar vulnerable to "phishing" attacks](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=290435)


## Chrome

* [CSS mix-blend-mode is bad for your browsing history](https://lcamtuf.blogspot.com/2016/08/css-mix-blend-mode-is-bad-for-keeping.html) ([demo](http://lcamtuf.coredump.cx/whack/))


## Pretty much every terminal emulator

* [Multi-line pastes from an untrusted source (e.g. browser) can automatically execute something you did not intend to copy](https://www.google.com/search?q=terminal+security+paste&ie=utf-8&oe=utf-8)


## sudo

* When running `sudo -u non-root-user` as root, `TIOCSTI` allows the `command` in `sudo -u non-root-user command` to [execute anything as root](http://www.openwall.com/lists/oss-security/2017/06/03/9).  [Can be fixed](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=657784#9) with `Defaults use_pty` in `sudoers`.  [More notes](https://ruderich.org/simon/notes/su-sudo-from-root-tty-hijacking).

* sudo credential caching (generally enabled by default; disabled with `Defaults timestamp_timeout=0`) allows *any process* in a TTY to do a passwordless sudo within the timeout period, not just commands that you've prefixed with `sudo` in the shell.


## VirtualBox

* Unlike VMware Workstation, [VirtualBox clipboard sharing gives guests continuous access to the clipboard](https://www.virtualbox.org/ticket/16508), instead of just when the VM is focused.


## virt-manager/spice-gtk

* Unlike VMware Workstation, [virt-manager/spice-gtk clipboard sharing gives guests continuous access to the clipboard](https://bugzilla.redhat.com/show_bug.cgi?id=1320263), instead of just when the VM is focused.  This clipboard sharing feature is *unconditionally enabled* without warning.  A compromised guest with no need for clipboard access can install `spice-vdagent` and start continuously sniffing the host clipboard.


## Xorg

* [Any program connected to the server can sniff another program's keystrokes](https://theinvisiblethings.blogspot.com/2011/04/linux-security-circus-on-gui-isolation.html).  Solved in Wayland.


## Node

* [node climbs up to look for node_modules in directories that can be written to by other users](https://github.com/nodejs/node-v0.x-archive/issues/8830)


## Erlang/OTP

* [You can crash a distributed Erlang node by making ~1M connections with an invalid security cookie](https://blog.voltone.net/post/12)

* [Check for null bytes in binaries / strings when opening files](https://bugs.erlang.org/browse/ERL-370) (to be fixed in OTP 21.0)

* [Stored XSS vulnerability in mod_dir](https://bugs.erlang.org/browse/ERL-330)

* [HTTP content injection in httpc:request](https://bugs.erlang.org/browse/ERL-456)


## Twisted

* [Credentials materials are compared unsafely throughout Twisted](http://twistedmatrix.com/trac/ticket/4536), still open due to the difficulty of measuring whether the constant-time compare function actually fixes anything.

* [twisted.web has no protection against HTTP response-splitting attacks](http://twistedmatrix.com/trac/ticket/3770)

* [twisted.web server has no way to limit size of request body](http://twistedmatrix.com/trac/ticket/4898)


## WeeChat

* [WeeChat relays allows clients to execute code on the relay](https://github.com/weechat/weechat/issues/928)


## phantomjs, libqtwebkit4, libqt5webkit5

* These packages exist in a state of permanent insecurity because they don't keep up with the ~6-week browser update cycle.  (e.g. take any one of the many WebKit security bugs fixed after the last release of these packages, which could be a ~year old.)


## Windows

* [Windows Defender's malware emulator is unsandboxed and runs with SYSTEM privileges](https://opencfp.immunityinc.com/talks/160/)

* [Various methods of automatically bypassing UAC](http://www.kernelmode.info/forum/viewtopic.php?f=11&t=3643&start=130#p30022) (see "Unfixed methods in upcoming Windows 10 RS2 release")


## Packages in your Linux distribution

* [Debian stable](https://security-tracker.debian.org/tracker/status/release/stable)
* [Debian testing](https://security-tracker.debian.org/tracker/status/release/testing)
* [Debian unstable](https://security-tracker.debian.org/tracker/status/release/unstable)
* [Ubuntu main archive](https://people.canonical.com/~ubuntu-security/cve/main.html)
* [Ubuntu universe archive](https://people.canonical.com/~ubuntu-security/cve/universe.html)
* [Ubuntu partner archive](https://people.canonical.com/~ubuntu-security/cve/partner.html)
* [Arch Linux](https://security.archlinux.org/)


## On your LineageOS device

* [CVE Tracker](https://cve.lineageos.org/devices)
