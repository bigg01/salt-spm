# salt-spm


```
wget https://github.com/bigg01/salt-spm/blob/master/dist/test1-201506-2.spm?raw=true
spm local install test1-201506-2.spm
```
```
sudo spm local install test1-201506-2.spm
Package test1 already installed, not installing again
 guo    tmp  $  sudo spm local remove test1-201506-2.spm
Invalid local command 'remove'
 guo    tmp  $  sudo spm remove test1-201506-2.spm
Removing package test1-201506-2.spm
Proceed? [N/y] y
... removing
package test1-201506-2.spm not installed
 guo    tmp  $  sudo spm local remove test1-201506-2.spm
Invalid local command 'remove'
 guo    tmp  $  sudo spm local install test1-201506-2.spm
Package test1 already installed, not installing again
 guo    tmp  $  sudo spm local install test1-201506-2.spm -f
Installing package from file test1-201506-2.spm
Proceed? [N/y] y
... installing
 guo    tmp  $  tree /srv/spm
/srv/spm
├── backup
│   └── salt
│       └── myapp
│           ├── FORMULA
│           └── test.sls
├── pillar
├── reactor
└── salt

6 directories, 2 files
```
https://docs.saltstack.com/en/latest/topics/spm/packaging.html


https://docs.saltstack.com/en/latest/topics/spm/packaging.html#spm-packaging
https://docs.saltstack.com/en/latest/topics/spm/dev.html#spm-development
https://docs.saltstack.com/en/latest/topics/spm/spm_formula.html#spm-formula


```
tree  /srv/spm*
/srv/spm
├── pillar
├── reactor
└── salt
    └── myapp
        ├── FORMULA
        └── test.sls
/srv/spm_build
└── test1-201506-2.spm

4 directories, 3 files
 guo    srv  spm  salt  $  cat /srv/spm/salt/myapp/FORMULA
name: test1
os: RedHat, Debian, Ubuntu, SUSE, FreeBSD
os_family: RedHat, Debian, SUSE, FreeBSD
version: 201506
release: 2
summary: Formula for installing Apache
description: Formula for installing Apache
 guo    srv  spm  salt  $  cat /srv/spm/salt/myapp/
FORMULA   test.sls
 guo    srv  spm  salt  $  cat /srv/spm/salt/myapp/test.sls
bash:
  pkg.installed
 guo    srv  spm  salt  $  sudo spm build /srv/spm/salt/myapp/
Built package /srv/spm_build/test1-201506-2.spm
 guo    srv  spm  salt  $  cat /srv/spm/salt/myapp/test.sls
bash:
  pkg.installed
 guo    srv  spm  salt  $  file /srv/spm_build/test1-201506-2.spm
/srv/spm_build/test1-201506-2.spm: bzip2 compressed data, block size = 900k
 guo    srv  spm  salt  $  cat /srv/spm/salt/myapp/test.sls
bash:
  pkg.installed
```
