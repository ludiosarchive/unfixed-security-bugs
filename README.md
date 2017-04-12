# A list of publicly known but unfixed security bugs

Please submit a pull request if you know about any other unfixed security bugs.


## tar

* [rmt filename support makes tar vulnerable to "phishing" attacks](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=290435)


## Chrome

* [CSS mix-blend-mode is bad for your browsing history](https://lcamtuf.blogspot.com/2016/08/css-mix-blend-mode-is-bad-for-keeping.html) ([demo](http://lcamtuf.coredump.cx/whack/))


## Pretty much every terminal emulator

* [Multi-line pastes from an untrusted source (e.g. browser) can automatically execute something you did not intend to copy](https://www.google.com/search?q=terminal+security+paste&ie=utf-8&oe=utf-8)


## Erlang/OTP

* [Stored XSS vulnerability in mod_dir](https://bugs.erlang.org/browse/ERL-330)


## VirtualBox

* Unlike VMware Workstation, [VirtualBox clipboard sharing gives guests continuous access to the clipboard](https://www.virtualbox.org/ticket/16508), instead of just when the VM is focused.


## Xorg

* [Any program connected to the server can sniff another program's keystrokes](http://theinvisiblethings.blogspot.com/2011/04/linux-security-circus-on-gui-isolation.html]).  Solved in Wayland.


## Twisted

* [Credentials materials are compared unsafely throughout Twisted](http://twistedmatrix.com/trac/ticket/4536), still open due to the difficulty of measuring whether the constant-time compare function actually fixes anything.

* [twisted.web has no protection against HTTP response-splitting attacks](http://twistedmatrix.com/trac/ticket/3770)

* [twisted.web server has no way to limit size of request body](http://twistedmatrix.com/trac/ticket/4898)


## alchemist-server

* [Server executes arbitrary code from remote machines](https://github.com/tonini/alchemist-server/issues/14)


## alchemist.vim

* [Bundled alchemist-server is vulnerable to remote code execution](https://github.com/slashmili/alchemist.vim/issues/85)
