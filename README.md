innoxmpp
========

Python XMPP admin 'bots' based on the SleekXMPP library

**Whats this?**

Suppose you are away from your server or workstation, somewhere on the run having only a tablet and an instant messaging client. Wouldn't it be cool to do tasks on your computer without logging in via ssh or some other remote access program?

innoxmpp solves this problem by creating bots who have specific tasks. These bots connect themselves to a XMPP server and are then reachable via your instant messaging client from wherever you are.

Currently there is a GitBot, a bot who can perform tasks related to the distributed version control system [git](http://www.git-scm.com). It can clone repositories, perform push and pull operations and commit changes on local files.

One scenario where this comes in handy is when you are only with your tablet and you want to perform some changes on data on e.g. GitHub. Set up GitBot on a box that is reachable via WebDAV, clone your repositories there and access the files from your tablet with WebDAV (e.g. with [Textastic](http://www.textastic.com) on the iPad). When you are done with the changes, put the files back on the server and commit them to GitHub using your GitBot via your instant messenger. It's as easy as that.

Further bots and actions will be added in the future if some missing function scratches my itch.

**Requirements**

* [Python](http://www.python.org) >= 3.2.3 (Python2 is not supported, get over it)
* [SleekXMPP](http://sleekxmpp.com/)
* [DNSPython3](http://www.dnspython.com/)

**Using Packages**

The development was done with the Git versions of both SleekXMPP and DNSPython3.
Tests on Debian Sid (as of Sep 6th 2012) showed that the current packaged version
of SleekXMPP (python3-sleekxmpp: 1.0~beta5-2) throws an error when starting a bot.

    DEBUG     ==== TRANSITION disconnected -> connected
    Traceback (most recent call last):
      File "git_bot.py", line 13, in <module>
        gitBot.run()    
      File "/home/wonder/scripts/innoxmpp/bots/GenericBot.py", line 109, in run
        self.process(block=True)
      File "/usr/lib/python3/dist-packages/sleekxmpp/basexmpp.py", line 148, in process
        return XMLStream.process(self, *args, **kwargs)
    TypeError: process() got an unexpected keyword argument 'block'

Using the latest version from the (cloned) [Git repository](https://github.com/egoexpress/SleekXMPP) didn't show this behaviour.

**Getting the code**

The code of this project is available at GitHub at <https://github.com/egoexpress/innoxmpp>