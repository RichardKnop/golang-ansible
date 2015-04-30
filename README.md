golang-ansible
==============

Ansible role that installs Go (http://golang.org/). The 1.4.2 release for x86 64-bit Linux systems is installed by default, other platforms and version are supported by variables. 

Role Variables
--------------

```yaml
golang:
  tarball: "go1.4.2.linux-amd64.tar.gz"
  tarball_checksum: "141b8345932641483c2437bdbd65488a269282ac85f91170805c273f03dd223b"
  app_user: "go_app_user"
  apps_group: "go_apps"
```

All variables are optional. The defaults will work just fine.

By default, Go environment will be created for a user go_app_user (belonging to go_apps group).

Proper Go code structure will be created inside the golang.app_user's home directory, e.g.:

```
/home/go_app_user/go
  src
    github.com
  pkg
  bin
```

GOPATH will be set to /home/go_app_user/go.

If you overwrite golang.tarball variable, make sure to also overwrite golang.tarball_checksum to be correct. 

You can get SHA256 hash of a release like this:

```
$ shasum -a 256 go1.4.2.linux-amd64.tar.gz
```
