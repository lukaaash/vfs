vfs
===

VFS is an experimental wrapper around [SSHFS](http://fuse.sourceforge.net/sshfs.html) written in Node.js.
It makes it possible to mount remote filesystems accessible through [SFTP over WebSockets](http://sftp.ws/)
(instead of common SFTP over SSH).

In future, it might support other kinds of virtual filesystems as well.

**Note:** At the client side, Linux with `sshfs` and Node.js is required.

## Getting started

1. Setup an [SFTP over WebSockets server](https://www.npmjs.com/package/sftp-ws/) at the remote machine (or skip this step and try `wss://nuane.com/sftp`).
2. Install `sshfs` at the client (in Debian/Ubuntu, run `apt-get install sshfs` as root).
3. Install `vfs` at the client by running `npm install vfs` (add `-g` as root to install globally).
4. Mount a remote filesystem to a local directory by running `vfs url mountpoint` (for example `vfs wss://nuane.com/sftp ~/sftp).
5. Enjoy the remote filesystem! :-)

## Missing features

- Add the ability to easily start the filesystem client in the background.
- Make it possible to pass SSHFS and FUSE options from command line.
- More authentication options (only `Basic` authentication is supported at the moment, which is insufficient).
