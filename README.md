# KIII-HW2

## Chapter 3

### docker info
```
$ docker info
Client:
 Context:    default
 Debug Mode: false
 Plugins:
  buildx: Docker Buildx (Docker Inc., v0.9.1)
  compose: Docker Compose (Docker Inc., v2.13.0)
  dev: Docker Dev Environments (Docker Inc., v0.0.5)
  extension: Manages Docker extensions (Docker Inc., v0.2.16)
  sbom: View the packaged-based Software Bill Of Materials (SBOM) for an image (Anchore Inc., 0.6.0)
  scan: Docker Scan (Docker Inc., v0.22.0)

Server:
 Containers: 5
  Running: 0
  Paused: 0
  Stopped: 5
 Images: 3
 Server Version: 20.10.21
 Storage Driver: overlay2
  Backing Filesystem: extfs
  Supports d_type: true
  Native Overlay Diff: true
  userxattr: false
 Logging Driver: json-file
 Cgroup Driver: cgroupfs
 Cgroup Version: 1
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local logentries splunk syslog
 Swarm: inactive
 Runtimes: io.containerd.runc.v2 io.containerd.runtime.v1.linux runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: 770bd0108c32f3fb5c73ae1264f7e503fe7b2661
 runc version: v1.1.4-0-g5fd4c4d
 init version: de40ad0
 Security Options:
  seccomp
   Profile: default
 Kernel Version: 5.15.90.1-microsoft-standard-WSL2
 Operating System: Docker Desktop
 OSType: linux
 Architecture: x86_64
 CPUs: 6
 Total Memory: 3.795GiB
 Name: docker-desktop
 ID: CJP3:DB5E:X55J:2FW5:EVTJ:D4VR:ZXBO:BAIX:XFSJ:MN2G:7GON:VZOA
 Docker Root Dir: /var/lib/docker
 Debug Mode: false
 HTTP Proxy: http.docker.internal:3128
 HTTPS Proxy: http.docker.internal:3128
 No Proxy: hubproxy.docker.internal
 Registry: https://index.docker.io/v1/
 Labels:
 Experimental: false
 Insecure Registries:
  hubproxy.docker.internal:5000
  127.0.0.0/8
 Live Restore Enabled: false

WARNING: No blkio throttle.read_bps_device support
WARNING: No blkio throttle.write_bps_device support
WARNING: No blkio throttle.read_iops_device support
WARNING: No blkio throttle.write_iops_device support
```
### docker run -i -t ubuntu /bin/bash

```
$ docker run -i -t ubuntu /bin/bash
Unable to find image 'ubuntu:latest' locally
latest: Pulling from library/ubuntu
76769433fd8a: Pull complete
Digest: sha256:2adf22367284330af9f832ffefb717c78239f6251d9d0f58de50b86229ed1427
Status: Downloaded newer image for ubuntu:latest
root@b5e6f9280dd5:/#
```

### Ubuntu internal commands
```
root@b5e6f9280dd5:/# hostname
b5e6f9280dd5
```

```
root@b5e6f9280dd5:/# cat /etc/hosts
127.0.0.1       localhost
::1     localhost ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters
172.17.0.2      b5e6f9280dd5
```

```
root@b5e6f9280dd5:/# hostname -I
172.17.0.2
```

```
root@b5e6f9280dd5:/# ps -aux
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.0  0.0   4628  3780 pts/0    Ss   15:43   0:00 /bin/bash
root        12  0.0  0.0   7060  1576 pts/0    R+   15:50   0:00 ps -aux
```
```
root@b5e6f9280dd5:/# apt-get update; apt-get install vim
Get:1 http://archive.ubuntu.com/ubuntu jammy InRelease [270 kB]
Get:2 http://security.ubuntu.com/ubuntu jammy-security InRelease [110 kB]
Get:3 http://archive.ubuntu.com/ubuntu jammy-updates InRelease [119 kB]
Get:4 http://security.ubuntu.com/ubuntu jammy-security/universe amd64 Packages [889 kB]
Get:5 http://archive.ubuntu.com/ubuntu jammy-backports InRelease [107 kB]
Get:6 http://archive.ubuntu.com/ubuntu jammy/multiverse amd64 Packages [266 kB]
Get:7 http://archive.ubuntu.com/ubuntu jammy/restricted amd64 Packages [164 kB]
Get:8 http://archive.ubuntu.com/ubuntu jammy/universe amd64 Packages [17.5 MB]
Get:9 http://security.ubuntu.com/ubuntu jammy-security/multiverse amd64 Packages [5557 B]
Get:10 http://security.ubuntu.com/ubuntu jammy-security/main amd64 Packages [860 kB]
Get:11 http://security.ubuntu.com/ubuntu jammy-security/restricted amd64 Packages [823 kB]
Get:12 http://archive.ubuntu.com/ubuntu jammy/main amd64 Packages [1792 kB]
Get:13 http://archive.ubuntu.com/ubuntu jammy-updates/universe amd64 Packages [1127 kB]
Get:14 http://archive.ubuntu.com/ubuntu jammy-updates/restricted amd64 Packages [880 kB]
Get:15 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 Packages [1191 kB]
Get:16 http://archive.ubuntu.com/ubuntu jammy-updates/multiverse amd64 Packages [10.9 kB]
Get:17 http://archive.ubuntu.com/ubuntu jammy-backports/universe amd64 Packages [22.4 kB]
Get:18 http://archive.ubuntu.com/ubuntu jammy-backports/main amd64 Packages [49.0 kB]
Fetched 26.2 MB in 7s (3513 kB/s)
Reading package lists... Done
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  libexpat1 libgpm2 libmpdec3 libpython3.10 libpython3.10-minimal libpython3.10-stdlib libreadline8 libsodium23
  libsqlite3-0 media-types readline-common vim-common vim-runtime xxd
Suggested packages:
  gpm readline-doc ctags vim-doc vim-scripts
The following NEW packages will be installed:
  libexpat1 libgpm2 libmpdec3 libpython3.10 libpython3.10-minimal libpython3.10-stdlib libreadline8 libsodium23
  libsqlite3-0 media-types readline-common vim vim-common vim-runtime xxd
0 upgraded, 15 newly installed, 0 to remove and 2 not upgraded.
Need to get 14.5 MB of archives.
After this operation, 61.1 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libexpat1 amd64 2.4.7-1ubuntu0.2 [91.0 kB]
Get:2 http://archive.ubuntu.com/ubuntu jammy/main amd64 libmpdec3 amd64 2.5.1-2build2 [86.8 kB]
Get:3 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libpython3.10-minimal amd64 3.10.6-1~22.04.2 [810 kB]
Get:4 http://archive.ubuntu.com/ubuntu jammy/main amd64 media-types all 7.0.0 [25.5 kB]
Get:5 http://archive.ubuntu.com/ubuntu jammy/main amd64 readline-common all 8.1.2-1 [53.5 kB]
Get:6 http://archive.ubuntu.com/ubuntu jammy/main amd64 libreadline8 amd64 8.1.2-1 [153 kB]
Get:7 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libsqlite3-0 amd64 3.37.2-2ubuntu0.1 [641 kB]
Get:8 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libpython3.10-stdlib amd64 3.10.6-1~22.04.2 [1832 kB]
Get:9 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 xxd amd64 2:8.2.3995-1ubuntu2.3 [51.2 kB]
Get:10 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 vim-common all 2:8.2.3995-1ubuntu2.3 [81.5 kB]
Get:11 http://archive.ubuntu.com/ubuntu jammy/main amd64 libgpm2 amd64 1.20.7-10build1 [15.3 kB]
Get:12 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 libpython3.10 amd64 3.10.6-1~22.04.2 [1955 kB]
Get:13 http://archive.ubuntu.com/ubuntu jammy/main amd64 libsodium23 amd64 1.0.18-1build2 [164 kB]
Get:14 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 vim-runtime all 2:8.2.3995-1ubuntu2.3 [6825 kB]
Get:15 http://archive.ubuntu.com/ubuntu jammy-updates/main amd64 vim amd64 2:8.2.3995-1ubuntu2.3 [1727 kB]
Fetched 14.5 MB in 4s (3885 kB/s)
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package libexpat1:amd64.
(Reading database ... 4395 files and directories currently installed.)
Preparing to unpack .../00-libexpat1_2.4.7-1ubuntu0.2_amd64.deb ...
Unpacking libexpat1:amd64 (2.4.7-1ubuntu0.2) ...
Selecting previously unselected package libmpdec3:amd64.
Preparing to unpack .../01-libmpdec3_2.5.1-2build2_amd64.deb ...
Unpacking libmpdec3:amd64 (2.5.1-2build2) ...
Selecting previously unselected package libpython3.10-minimal:amd64.
Preparing to unpack .../02-libpython3.10-minimal_3.10.6-1~22.04.2_amd64.deb ...
Unpacking libpython3.10-minimal:amd64 (3.10.6-1~22.04.2) ...
Selecting previously unselected package media-types.
Preparing to unpack .../03-media-types_7.0.0_all.deb ...
Unpacking media-types (7.0.0) ...
Selecting previously unselected package readline-common.
Preparing to unpack .../04-readline-common_8.1.2-1_all.deb ...
Unpacking readline-common (8.1.2-1) ...
Selecting previously unselected package libreadline8:amd64.
Preparing to unpack .../05-libreadline8_8.1.2-1_amd64.deb ...
Unpacking libreadline8:amd64 (8.1.2-1) ...
Selecting previously unselected package libsqlite3-0:amd64.
Preparing to unpack .../06-libsqlite3-0_3.37.2-2ubuntu0.1_amd64.deb ...
Unpacking libsqlite3-0:amd64 (3.37.2-2ubuntu0.1) ...
Selecting previously unselected package libpython3.10-stdlib:amd64.
Preparing to unpack .../07-libpython3.10-stdlib_3.10.6-1~22.04.2_amd64.deb ...
Unpacking libpython3.10-stdlib:amd64 (3.10.6-1~22.04.2) ...
Selecting previously unselected package xxd.
Preparing to unpack .../08-xxd_2%3a8.2.3995-1ubuntu2.3_amd64.deb ...
Unpacking xxd (2:8.2.3995-1ubuntu2.3) ...
Selecting previously unselected package vim-common.
Preparing to unpack .../09-vim-common_2%3a8.2.3995-1ubuntu2.3_all.deb ...
Unpacking vim-common (2:8.2.3995-1ubuntu2.3) ...
Selecting previously unselected package libgpm2:amd64.
Preparing to unpack .../10-libgpm2_1.20.7-10build1_amd64.deb ...
Unpacking libgpm2:amd64 (1.20.7-10build1) ...
Selecting previously unselected package libpython3.10:amd64.
Preparing to unpack .../11-libpython3.10_3.10.6-1~22.04.2_amd64.deb ...
Unpacking libpython3.10:amd64 (3.10.6-1~22.04.2) ...
Selecting previously unselected package libsodium23:amd64.
Preparing to unpack .../12-libsodium23_1.0.18-1build2_amd64.deb ...
Unpacking libsodium23:amd64 (1.0.18-1build2) ...
Selecting previously unselected package vim-runtime.
Preparing to unpack .../13-vim-runtime_2%3a8.2.3995-1ubuntu2.3_all.deb ...
Adding 'diversion of /usr/share/vim/vim82/doc/help.txt to /usr/share/vim/vim82/doc/help.txt.vim-tiny by vim-runtime'
Adding 'diversion of /usr/share/vim/vim82/doc/tags to /usr/share/vim/vim82/doc/tags.vim-tiny by vim-runtime'
Unpacking vim-runtime (2:8.2.3995-1ubuntu2.3) ...
Selecting previously unselected package vim.
Preparing to unpack .../14-vim_2%3a8.2.3995-1ubuntu2.3_amd64.deb ...
Unpacking vim (2:8.2.3995-1ubuntu2.3) ...
Setting up libexpat1:amd64 (2.4.7-1ubuntu0.2) ...
Setting up media-types (7.0.0) ...
Setting up libsodium23:amd64 (1.0.18-1build2) ...
Setting up libgpm2:amd64 (1.20.7-10build1) ...
Setting up libsqlite3-0:amd64 (3.37.2-2ubuntu0.1) ...
Setting up xxd (2:8.2.3995-1ubuntu2.3) ...
Setting up vim-common (2:8.2.3995-1ubuntu2.3) ...
Setting up libpython3.10-minimal:amd64 (3.10.6-1~22.04.2) ...
Setting up libmpdec3:amd64 (2.5.1-2build2) ...
Setting up vim-runtime (2:8.2.3995-1ubuntu2.3) ...
Setting up readline-common (8.1.2-1) ...
Setting up libreadline8:amd64 (8.1.2-1) ...
Setting up libpython3.10-stdlib:amd64 (3.10.6-1~22.04.2) ...
Setting up libpython3.10:amd64 (3.10.6-1~22.04.2) ...
Setting up vim (2:8.2.3995-1ubuntu2.3) ...
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vim (vim) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vimdiff (vimdiff) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/rvim (rvim) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/rview (rview) in auto mode
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/vi (vi) in auto mode
update-alternatives: warning: skip creation of /usr/share/man/da/man1/vi.1.gz because associated file /usr/share/man/da/man1/vim.1.gz (of link group vi) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/de/man1/vi.1.gz because associated file /usr/share/man/de/man1/vim.1.gz (of link group vi) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/fr/man1/vi.1.gz because associated file /usr/share/man/fr/man1/vim.1.gz (of link group vi) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/it/man1/vi.1.gz because associated file /usr/share/man/it/man1/vim.1.gz (of link group vi) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ja/man1/vi.1.gz because associated file /usr/share/man/ja/man1/vim.1.gz (of link group vi) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/pl/man1/vi.1.gz because associated file /usr/share/man/pl/man1/vim.1.gz (of link group vi) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ru/man1/vi.1.gz because associated file /usr/share/man/ru/man1/vim.1.gz (of link group vi) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/vi.1.gz because associated file /usr/share/man/man1/vim.1.gz (of link group vi) doesn't exist
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/view (view) in auto mode
update-alternatives: warning: skip creation of /usr/share/man/da/man1/view.1.gz because associated file /usr/share/man/da/man1/vim.1.gz (of link group view) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/de/man1/view.1.gz because associated file /usr/share/man/de/man1/vim.1.gz (of link group view) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/fr/man1/view.1.gz because associated file /usr/share/man/fr/man1/vim.1.gz (of link group view) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/it/man1/view.1.gz because associated file /usr/share/man/it/man1/vim.1.gz (of link group view) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ja/man1/view.1.gz because associated file /usr/share/man/ja/man1/vim.1.gz (of link group view) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/pl/man1/view.1.gz because associated file /usr/share/man/pl/man1/vim.1.gz (of link group view) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ru/man1/view.1.gz because associated file /usr/share/man/ru/man1/vim.1.gz (of link group view) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/view.1.gz because associated file /usr/share/man/man1/vim.1.gz (of link group view) doesn't exist
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/ex (ex) in auto mode
update-alternatives: warning: skip creation of /usr/share/man/da/man1/ex.1.gz because associated file /usr/share/man/da/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/de/man1/ex.1.gz because associated file /usr/share/man/de/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/fr/man1/ex.1.gz because associated file /usr/share/man/fr/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/it/man1/ex.1.gz because associated file /usr/share/man/it/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ja/man1/ex.1.gz because associated file /usr/share/man/ja/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/pl/man1/ex.1.gz because associated file /usr/share/man/pl/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ru/man1/ex.1.gz because associated file /usr/share/man/ru/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/ex.1.gz because associated file /usr/share/man/man1/vim.1.gz (of link group ex) doesn't exist
update-alternatives: using /usr/bin/vim.basic to provide /usr/bin/editor (editor) in auto mode
update-alternatives: warning: skip creation of /usr/share/man/da/man1/editor.1.gz because associated file /usr/share/man/da/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/de/man1/editor.1.gz because associated file /usr/share/man/de/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/fr/man1/editor.1.gz because associated file /usr/share/man/fr/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/it/man1/editor.1.gz because associated file /usr/share/man/it/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ja/man1/editor.1.gz because associated file /usr/share/man/ja/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/pl/man1/editor.1.gz because associated file /usr/share/man/pl/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/ru/man1/editor.1.gz because associated file /usr/share/man/ru/man1/vim.1.gz (of link group editor) doesn't exist
update-alternatives: warning: skip creation of /usr/share/man/man1/editor.1.gz because associated file /usr/share/man/man1/vim.1.gz (of link group editor) doesn't exist
Processing triggers for libc-bin (2.35-0ubuntu3.1) ...
```
```
root@b5e6f9280dd5:/# exit
exit
```

### docker ps -a

```
$ docker ps -a
CONTAINER ID   IMAGE                           COMMAND                  CREATED         STATUS                      PORTS                                  NAMES
b5e6f9280dd5   ubuntu                          "/bin/bash"              9 minutes ago   Exited (0) 46 seconds ago                                          clever_kepler
016f2c53b0be   wurstmeister/kafka:2.11-2.0.0   "start-kafka.sh"         5 weeks ago     Exited (255) 2 days ago     0.0.0.0:9092->9092/tcp, 9093/tcp       e-kafka-1
54d2e38c991d   wurstmeister/zookeeper:3.4.6    "/bin/sh -c '/usr/sb…"   5 weeks ago     Exited (255) 2 days ago     22/tcp, 2181/tcp, 2888/tcp, 3888/tcp   e-zookeeper-1
c97b8b3af058   wurstmeister/kafka:2.11-2.0.0   "start-kafka.sh"         5 weeks ago     Exited (1) 5 weeks ago                                             bold_banach
```

### docker run --name bob_the_container -i -t ubuntu /bin/bash
```
$ docker run --name bob_the_container -i -t ubuntu /bin/bash
root@8d3c1aee8a10:/# exit
exit
```
### docker start bob_the_container
```
$ docker start bob_the_container
bob_the_container
```
### docker ps
```
$ docker ps
CONTAINER ID   IMAGE     COMMAND       CREATED         STATUS              PORTS     NAMES
8d3c1aee8a10   ubuntu    "/bin/bash"   3 minutes ago   Up About a minute             bob_the_container
```
### $ docker attach bob_the_container
```
$ docker attach bob_the_container
root@8d3c1aee8a10:/# exit
exit
```
### docker run --name daemon_dave -d ubuntu /bin/sh -c "while true; do echo hello world; sleep 1; done"
```
$ docker run --name daemon_dave -d ubuntu /bin/sh -c "while true; do echo hello world; sleep 1; done"
338d0cd53a162f9925ec9e147289989741224a068835b9d2b2f1fa874b778b72
```
### docker ps
```
$ docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS              PORTS     NAMES
338d0cd53a16   ubuntu    "/bin/sh -c 'while t…"   About a minute ago   Up About a minute             daemon_dave
```
### docker logs daemon_dave
```
$ docker logs daemon_dave
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
```
### docker logs -f daemon_dave
```
$ docker logs -f daemon_dave
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
hello world
```
### docker logs -ft daemon_dave
```
$ docker logs -ft daemon_dave
2023-03-08T16:17:50.596569322Z hello world
2023-03-08T16:17:51.597536286Z hello world
2023-03-08T16:17:52.599291550Z hello world
2023-03-08T16:17:53.602496690Z hello world
2023-03-08T16:17:54.605742405Z hello world
2023-03-08T16:17:55.608532120Z hello world
2023-03-08T16:17:56.611476935Z hello world
2023-03-08T16:17:57.614651450Z hello world
2023-03-08T16:17:58.617568765Z hello world
2023-03-08T16:17:59.619811779Z hello world
2023-03-08T16:18:00.621623292Z hello world
2023-03-08T16:18:01.624745754Z hello world
2023-03-08T16:18:02.626740594Z hello world
2023-03-08T16:18:03.628574333Z hello world
2023-03-08T16:18:04.631489075Z hello world
2023-03-08T16:18:05.634345617Z hello world
2023-03-08T16:18:06.637293859Z hello world
2023-03-08T16:18:07.640146601Z hello world
2023-03-08T16:18:08.643113434Z hello world
2023-03-08T16:18:09.646152933Z hello world
2023-03-08T16:18:10.649015518Z hello world
2023-03-08T16:18:11.652041102Z hello world
2023-03-08T16:18:12.655112086Z hello world
2023-03-08T16:18:13.658124671Z hello world
2023-03-08T16:18:14.661024755Z hello world
2023-03-08T16:18:15.664072939Z hello world
2023-03-08T16:18:16.667001081Z hello world
2023-03-08T16:18:17.670036969Z hello world
2023-03-08T16:18:18.673021560Z hello world
2023-03-08T16:18:19.676075450Z hello world
2023-03-08T16:18:20.679015841Z hello world
2023-03-08T16:18:21.681942732Z hello world
2023-03-08T16:18:22.684879323Z hello world
2023-03-08T16:18:23.687613413Z hello world
2023-03-08T16:18:24.689638602Z hello world
2023-03-08T16:18:25.691240020Z hello world
2023-03-08T16:18:26.692948732Z hello world
2023-03-08T16:18:27.693879843Z hello world
2023-03-08T16:18:28.694800654Z hello world
2023-03-08T16:18:29.696688066Z hello world
2023-03-08T16:18:30.699554479Z hello world
2023-03-08T16:18:31.701561892Z hello world
2023-03-08T16:18:32.702808203Z hello world
2023-03-08T16:18:33.704044589Z hello world
2023-03-08T16:18:34.706125409Z hello world
2023-03-08T16:18:35.708593229Z hello world
2023-03-08T16:18:36.711026349Z hello world
2023-03-08T16:18:37.713991869Z hello world
2023-03-08T16:18:38.715891853Z hello world
2023-03-08T16:18:39.717769373Z hello world
2023-03-08T16:18:40.720067486Z hello world
2023-03-08T16:18:41.721305160Z hello world
2023-03-08T16:18:42.723070120Z hello world
2023-03-08T16:18:43.724641181Z hello world
2023-03-08T16:18:44.726629042Z hello world
2023-03-08T16:18:45.729447303Z hello world
2023-03-08T16:18:46.731811265Z hello world
2023-03-08T16:18:47.733971226Z hello world
2023-03-08T16:18:48.736817888Z hello world
2023-03-08T16:18:49.738991571Z hello world
2023-03-08T16:18:50.739955970Z hello world
2023-03-08T16:18:51.742111178Z hello world
2023-03-08T16:18:52.744897891Z hello world
2023-03-08T16:18:53.747052599Z hello world
2023-03-08T16:18:54.749189904Z hello world
2023-03-08T16:18:55.752004486Z hello world
2023-03-08T16:18:56.753873168Z hello world
2023-03-08T16:18:57.756861758Z hello world
2023-03-08T16:18:58.759051211Z hello world
2023-03-08T16:18:59.760102156Z hello world
2023-03-08T16:19:00.762116907Z hello world
2023-03-08T16:19:01.765007664Z hello world
2023-03-08T16:19:02.768147023Z hello world
2023-03-08T16:19:03.771239837Z hello world
2023-03-08T16:19:04.774268965Z hello world
2023-03-08T16:19:05.777189535Z hello world
2023-03-08T16:19:06.780134148Z hello world
2023-03-08T16:19:07.783247761Z hello world
2023-03-08T16:19:08.785220353Z hello world
2023-03-08T16:19:09.786318262Z hello world
2023-03-08T16:19:10.788316773Z hello world
2023-03-08T16:19:11.791230185Z hello world
2023-03-08T16:19:12.794226498Z hello world
2023-03-08T16:19:13.796236366Z hello world
2023-03-08T16:19:14.798181161Z hello world
2023-03-08T16:19:15.801102659Z hello world
2023-03-08T16:19:16.804386958Z hello world
2023-03-08T16:19:17.807371156Z hello world
2023-03-08T16:19:18.809436252Z hello world
2023-03-08T16:19:19.810396445Z hello world
2023-03-08T16:19:20.811493338Z hello world
2023-03-08T16:19:21.812619837Z hello world
2023-03-08T16:19:22.813509675Z hello world
2023-03-08T16:19:23.814405213Z hello world
2023-03-08T16:19:24.815300251Z hello world
2023-03-08T16:19:25.817063992Z hello world
2023-03-08T16:19:26.819607234Z hello world
2023-03-08T16:19:27.821479775Z hello world
2023-03-08T16:19:28.822416613Z hello world
2023-03-08T16:19:29.823507317Z hello world
2023-03-08T16:19:30.825402265Z hello world
2023-03-08T16:19:31.827415413Z hello world
2023-03-08T16:19:32.829404261Z hello world
2023-03-08T16:19:33.831350609Z hello world
2023-03-08T16:19:34.832279355Z hello world
2023-03-08T16:19:35.834329303Z hello world
2023-03-08T16:19:36.837211353Z hello world
2023-03-08T16:19:37.839117495Z hello world
2023-03-08T16:19:38.839124368Z hello world
2023-03-08T16:19:39.841221626Z hello world
2023-03-08T16:19:40.843949982Z hello world
2023-03-08T16:19:41.846652039Z hello world
2023-03-08T16:19:42.849766613Z hello world
2023-03-08T16:19:43.852262469Z hello world
2023-03-08T16:19:44.854122224Z hello world
2023-03-08T16:19:45.857355652Z hello world
2023-03-08T16:19:46.859487828Z hello world
2023-03-08T16:19:47.861450978Z hello world
2023-03-08T16:19:48.863487440Z hello world
2023-03-08T16:19:49.865422485Z hello world
2023-03-08T16:19:50.868228381Z hello world
2023-03-08T16:19:51.871111146Z hello world
2023-03-08T16:19:52.874020211Z hello world
2023-03-08T16:19:53.875977302Z hello world
2023-03-08T16:19:54.877141632Z hello world
2023-03-08T16:19:55.878312762Z hello world
2023-03-08T16:19:56.880477192Z hello world
2023-03-08T16:19:57.882644423Z hello world
2023-03-08T16:19:58.883554218Z hello world
2023-03-08T16:19:59.885248415Z hello world
2023-03-08T16:20:00.886902712Z hello world
2023-03-08T16:20:01.888037405Z hello world
2023-03-08T16:20:02.889193592Z hello world
2023-03-08T16:20:03.890030677Z hello world
2023-03-08T16:20:04.890994263Z hello world
2023-03-08T16:20:05.892969354Z hello world
2023-03-08T16:20:06.896079553Z hello world
2023-03-08T16:20:07.899072051Z hello world
2023-03-08T16:20:08.900601697Z hello world
2023-03-08T16:20:09.901910807Z hello world
2023-03-08T16:20:10.904357494Z hello world
2023-03-08T16:20:11.907258884Z hello world
2023-03-08T16:20:12.910695876Z hello world
2023-03-08T16:20:13.912922662Z hello world
2023-03-08T16:20:14.914077045Z hello world
2023-03-08T16:20:15.915927031Z hello world
2023-03-08T16:20:16.918741120Z hello world
2023-03-08T16:20:17.921693084Z hello world
2023-03-08T16:20:18.923687774Z hello world
2023-03-08T16:20:19.925532659Z hello world
2023-03-08T16:20:20.928245372Z hello world
2023-03-08T16:20:21.931263096Z hello world
2023-03-08T16:20:22.934218117Z hello world
2023-03-08T16:20:23.936236008Z hello world
2023-03-08T16:20:24.937245866Z hello world
2023-03-08T16:20:25.939156249Z hello world
2023-03-08T16:20:26.941286577Z hello world
2023-03-08T16:20:27.942215585Z hello world
2023-03-08T16:20:28.943290495Z hello world
2023-03-08T16:20:29.945323622Z hello world
2023-03-08T16:20:30.947366149Z hello world
2023-03-08T16:20:31.948640863Z hello world
2023-03-08T16:20:32.951185698Z hello world
2023-03-08T16:20:33.953298828Z hello world
2023-03-08T16:20:34.954378550Z hello world
2023-03-08T16:20:35.955379371Z hello world
2023-03-08T16:20:36.957340612Z hello world
2023-03-08T16:20:37.960111971Z hello world
2023-03-08T16:20:38.961931533Z hello world
2023-03-08T16:20:39.962792850Z hello world
2023-03-08T16:20:40.963574966Z hello world
2023-03-08T16:20:41.965304526Z hello world
2023-03-08T16:20:42.968123358Z hello world
2023-03-08T16:20:43.970162772Z hello world
2023-03-08T16:20:44.971460768Z hello world
2023-03-08T16:20:45.973421280Z hello world
2023-03-08T16:20:46.976291813Z hello world
2023-03-08T16:20:47.979247048Z hello world
2023-03-08T16:20:48.981236260Z hello world
2023-03-08T16:20:49.983343355Z hello world
2023-03-08T16:20:50.986080521Z hello world
2023-03-08T16:20:51.988974286Z hello world
2023-03-08T16:20:52.991172459Z hello world
2023-03-08T16:20:53.992362943Z hello world
2023-03-08T16:20:54.994233119Z hello world
2023-03-08T16:20:55.997184383Z hello world
2023-03-08T16:20:57.000239005Z hello world
2023-03-08T16:20:58.003132286Z hello world
2023-03-08T16:20:59.005220782Z hello world
2023-03-08T16:21:00.007127174Z hello world
2023-03-08T16:21:01.009961880Z hello world
2023-03-08T16:21:02.012900189Z hello world
2023-03-08T16:21:03.016109401Z hello world
2023-03-08T16:21:04.017965592Z hello world
2023-03-08T16:21:05.019995787Z hello world
2023-03-08T16:21:06.022376569Z hello world
2023-03-08T16:21:07.024608544Z hello world
2023-03-08T16:21:08.026614917Z hello world
2023-03-08T16:21:09.027220866Z hello world
2023-03-08T16:21:10.029160137Z hello world
2023-03-08T16:21:11.031447013Z hello world
2023-03-08T16:21:12.032432171Z hello world
2023-03-08T16:21:13.034425643Z hello world
2023-03-08T16:21:14.036485401Z hello world
2023-03-08T16:21:15.038241291Z hello world
2023-03-08T16:21:16.040814695Z hello world
2023-03-08T16:21:17.043288298Z hello world
2023-03-08T16:21:18.045391894Z hello world
2023-03-08T16:21:19.046326870Z hello world
2023-03-08T16:21:20.047201444Z hello world
2023-03-08T16:21:21.048181120Z hello world
2023-03-08T16:21:22.049285956Z hello world
2023-03-08T16:21:23.051472899Z hello world
2023-03-08T16:21:24.053763244Z hello world
2023-03-08T16:21:25.054694967Z hello world
2023-03-08T16:21:26.056588405Z hello world
2023-03-08T16:21:27.059144253Z hello world
2023-03-08T16:21:28.061575900Z hello world
2023-03-08T16:21:29.063607340Z hello world
2023-03-08T16:21:30.065521063Z hello world
2023-03-08T16:21:31.067485870Z hello world
2023-03-08T16:21:32.069371175Z hello world
2023-03-08T16:21:33.072379397Z hello world
2023-03-08T16:21:34.074149700Z hello world
2023-03-08T16:21:35.075979305Z hello world
2023-03-08T16:21:36.078858525Z hello world
2023-03-08T16:21:37.081039034Z hello world
2023-03-08T16:21:38.082822863Z hello world
2023-03-08T16:21:39.083957977Z hello world
2023-03-08T16:21:40.085954816Z hello world
2023-03-08T16:21:41.087981856Z hello world
2023-03-08T16:21:42.089841094Z hello world
2023-03-08T16:21:43.092868843Z hello world
2023-03-08T16:21:44.094779982Z hello world
2023-03-08T16:21:45.095756912Z hello world
2023-03-08T16:21:46.097572177Z hello world
2023-03-08T16:21:47.100618408Z hello world
2023-03-08T16:21:48.102800924Z hello world
2023-03-08T16:21:49.103809718Z hello world
2023-03-08T16:21:50.104795711Z hello world
2023-03-08T16:21:51.106716022Z hello world
2023-03-08T16:21:52.109800954Z hello world
2023-03-08T16:21:53.112700382Z hello world
2023-03-08T16:21:54.115035271Z hello world
2023-03-08T16:21:55.116609050Z hello world
2023-03-08T16:21:56.119415949Z hello world
2023-03-08T16:21:57.122277952Z hello world
2023-03-08T16:21:58.125160858Z hello world
2023-03-08T16:21:59.127099943Z hello world
2023-03-08T16:22:00.128864967Z hello world
2023-03-08T16:22:01.131735309Z hello world
2023-03-08T16:22:02.134539535Z hello world
2023-03-08T16:22:03.137431470Z hello world
2023-03-08T16:22:04.139717997Z hello world
2023-03-08T16:22:05.141759120Z hello world
2023-03-08T16:22:06.144651156Z hello world
2023-03-08T16:22:07.147692893Z hello world
2023-03-08T16:22:08.149812018Z hello world
2023-03-08T16:22:09.150642793Z hello world
```
### docker top daemon_dave
```
$ docker top daemon_dave
UID                 PID                 PPID                C                   STIME               TTY                 TIME                CMD
root                2697                2678                0                   16:17               ?                   00:00:00            /bin/sh -c while true; do echo hello world; sleep 1; done
root                3051                2697                0                   16:23               ?                   00:00:00            sleep 1
```

### docker stats daemon_dave

```
$ docker stats daemon_dave
CONTAINER ID   NAME          CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
338d0cd53a16   daemon_dave   0.01%     712KiB / 3.795GiB   0.02%     1.16kB / 0B   0B / 0B     2
CONTAINER ID   NAME          CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
338d0cd53a16   daemon_dave   0.29%     564KiB / 3.795GiB   0.01%     1.16kB / 0B   0B / 0B     2
CONTAINER ID   NAME          CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
338d0cd53a16   daemon_dave   0.29%     564KiB / 3.795GiB   0.01%     1.16kB / 0B   0B / 0B     2
CONTAINER ID   NAME          CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
338d0cd53a16   daemon_dave   0.07%     684KiB / 3.795GiB   0.02%     1.16kB / 0B   0B / 0B     2
CONTAINER ID   NAME          CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
338d0cd53a16   daemon_dave   0.07%     684KiB / 3.795GiB   0.02%     1.16kB / 0B   0B / 0B     2
CONTAINER ID   NAME          CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
338d0cd53a16   daemon_dave   0.11%     572KiB / 3.795GiB   0.01%     1.16kB / 0B   0B / 0B     2
CONTAINER ID   NAME          CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
338d0cd53a16   daemon_dave   0.11%     572KiB / 3.795GiB   0.01%     1.16kB / 0B   0B / 0B     2
CONTAINER ID   NAME          CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
338d0cd53a16   daemon_dave   0.07%     576KiB / 3.795GiB   0.01%     1.16kB / 0B   0B / 0B     2
CONTAINER ID   NAME          CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
338d0cd53a16   daemon_dave   0.07%     576KiB / 3.795GiB   0.01%     1.16kB / 0B   0B / 0B     2
CONTAINER ID   NAME          CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
338d0cd53a16   daemon_dave   0.08%     576KiB / 3.795GiB   0.01%     1.16kB / 0B   0B / 0B     2
CONTAINER ID   NAME          CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
338d0cd53a16   daemon_dave   0.08%     576KiB / 3.795GiB   0.01%     1.16kB / 0B   0B / 0B     2
CONTAINER ID   NAME          CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
338d0cd53a16   daemon_dave   0.07%     580KiB / 3.795GiB   0.01%     1.16kB / 0B   0B / 0B     2
CONTAINER ID   NAME          CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
338d0cd53a16   daemon_dave   0.07%     580KiB / 3.795GiB   0.01%     1.16kB / 0B   0B / 0B     2
CONTAINER ID   NAME          CPU %     MEM USAGE / LIMIT   MEM %     NET I/O       BLOCK I/O   PIDS
338d0cd53a16   daemon_dave   0.07%     580KiB / 3.795GiB   0.01%     1.16kB / 0B   0B / 0B     2
```

### docker exec -t -i daemon_dave /bin/bash
```
$ docker exec -t -i daemon_dave /bin/bash
root@338d0cd53a16:/#
```

### docker stop daemon_dave
```
$ docker stop daemon_dave
daemon_dave
```
### docker ps
```
$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
```

### docker inspect daemon_dave
```
$ docker inspect daemon_dave
[
    {
        "Id": "338d0cd53a162f9925ec9e147289989741224a068835b9d2b2f1fa874b778b72",
        "Created": "2023-03-08T16:17:48.17910729Z",
        "Path": "/bin/sh",
        "Args": [
            "-c",
            "while true; do echo hello world; sleep 1; done"
        ],
        "State": {
            "Status": "exited",
            "Running": false,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 0,
            "ExitCode": 137,
            "Error": "",
            "StartedAt": "2023-03-08T16:17:50.597330722Z",
            "FinishedAt": "2023-03-08T16:28:15.191818471Z"
        },
        "Image": "sha256:74f2314a03de34a0a2d552b805411fc9553a02ea71c1291b815b2f645f565683",
        "ResolvConfPath": "/var/lib/docker/containers/338d0cd53a162f9925ec9e147289989741224a068835b9d2b2f1fa874b778b72/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/338d0cd53a162f9925ec9e147289989741224a068835b9d2b2f1fa874b778b72/hostname",
        "HostsPath": "/var/lib/docker/containers/338d0cd53a162f9925ec9e147289989741224a068835b9d2b2f1fa874b778b72/hosts",
        "LogPath": "/var/lib/docker/containers/338d0cd53a162f9925ec9e147289989741224a068835b9d2b2f1fa874b778b72/338d0cd53a162f9925ec9e147289989741224a068835b9d2b2f1fa874b778b72-json.log",
        "Name": "/daemon_dave",
        "RestartCount": 0,
        "Driver": "overlay2",
        "Platform": "linux",
        "MountLabel": "",
        "ProcessLabel": "",
        "AppArmorProfile": "",
        "ExecIDs": null,
        "HostConfig": {
            "Binds": null,
            "ContainerIDFile": "",
            "LogConfig": {
                "Type": "json-file",
                "Config": {}
            },
            "NetworkMode": "default",
            "PortBindings": {},
            "RestartPolicy": {
                "Name": "no",
                "MaximumRetryCount": 0
            },
            "AutoRemove": false,
            "VolumeDriver": "",
            "VolumesFrom": null,
            "CapAdd": null,
            "CapDrop": null,
            "CgroupnsMode": "host",
            "Dns": [],
            "DnsOptions": [],
            "DnsSearch": [],
            "ExtraHosts": null,
            "GroupAdd": null,
            "IpcMode": "private",
            "Cgroup": "",
            "Links": null,
            "OomScoreAdj": 0,
            "PidMode": "",
            "Privileged": false,
            "PublishAllPorts": false,
            "ReadonlyRootfs": false,
            "SecurityOpt": null,
            "UTSMode": "",
            "UsernsMode": "",
            "ShmSize": 67108864,
            "Runtime": "runc",
            "ConsoleSize": [
                0,
                0
            ],
            "Isolation": "",
            "CpuShares": 0,
            "Memory": 0,
            "NanoCpus": 0,
            "CgroupParent": "",
            "BlkioWeight": 0,
            "BlkioWeightDevice": [],
            "BlkioDeviceReadBps": null,
            "BlkioDeviceWriteBps": null,
            "BlkioDeviceReadIOps": null,
            "BlkioDeviceWriteIOps": null,
            "CpuPeriod": 0,
            "CpuQuota": 0,
            "CpuRealtimePeriod": 0,
            "CpuRealtimeRuntime": 0,
            "CpusetCpus": "",
            "CpusetMems": "",
            "Devices": [],
            "DeviceCgroupRules": null,
            "DeviceRequests": null,
            "KernelMemory": 0,
            "KernelMemoryTCP": 0,
            "MemoryReservation": 0,
            "MemorySwap": 0,
            "MemorySwappiness": null,
            "OomKillDisable": false,
            "PidsLimit": null,
            "Ulimits": null,
            "CpuCount": 0,
            "CpuPercent": 0,
            "IOMaximumIOps": 0,
            "IOMaximumBandwidth": 0,
            "MaskedPaths": [
                "/proc/asound",
                "/proc/acpi",
                "/proc/kcore",
                "/proc/keys",
                "/proc/latency_stats",
                "/proc/timer_list",
                "/proc/timer_stats",
                "/proc/sched_debug",
                "/proc/scsi",
                "/sys/firmware"
            ],
            "ReadonlyPaths": [
                "/proc/bus",
                "/proc/fs",
                "/proc/irq",
                "/proc/sys",
                "/proc/sysrq-trigger"
            ]
        },
        "GraphDriver": {
            "Data": {
                "LowerDir": "/var/lib/docker/overlay2/32f9643868ecbce886c64cfef89cd4b1cef7c3abd5eabcabcc5074762ba5ebd7-init/diff:/var/lib/docker/overlay2/e78750c42120b7d0e7799a524b8beafa1b880cfeb663060ba356dd5f1a6b363f/diff",
                "MergedDir": "/var/lib/docker/overlay2/32f9643868ecbce886c64cfef89cd4b1cef7c3abd5eabcabcc5074762ba5ebd7/merged",
                "UpperDir": "/var/lib/docker/overlay2/32f9643868ecbce886c64cfef89cd4b1cef7c3abd5eabcabcc5074762ba5ebd7/diff",
                "WorkDir": "/var/lib/docker/overlay2/32f9643868ecbce886c64cfef89cd4b1cef7c3abd5eabcabcc5074762ba5ebd7/work"
            },
            "Name": "overlay2"
        },
        "Mounts": [],
        "Config": {
            "Hostname": "338d0cd53a16",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
            ],
            "Cmd": [
                "/bin/sh",
                "-c",
                "while true; do echo hello world; sleep 1; done"
            ],
            "Image": "ubuntu",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": null,
            "OnBuild": null,
            "Labels": {
                "desktop.docker.io/wsl-distro": "Ubuntu",
                "org.opencontainers.image.ref.name": "ubuntu",
                "org.opencontainers.image.version": "22.04"
            }
        },
        "NetworkSettings": {
            "Bridge": "",
            "SandboxID": "c2f2f46684c0c4ed70258eef5af983aff91569323ea16ce4d65cd46716f0fd82",
            "HairpinMode": false,
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "Ports": {},
            "SandboxKey": "/var/run/docker/netns/c2f2f46684c0",
            "SecondaryIPAddresses": null,
            "SecondaryIPv6Addresses": null,
            "EndpointID": "",
            "Gateway": "",
            "GlobalIPv6Address": "",
            "GlobalIPv6PrefixLen": 0,
            "IPAddress": "",
            "IPPrefixLen": 0,
            "IPv6Gateway": "",
            "MacAddress": "",
            "Networks": {
                "bridge": {
                    "IPAMConfig": null,
                    "Links": null,
                    "Aliases": null,
                    "NetworkID": "51abe6d59aaaea4c8f5eeb630b9e27d492d961195f1751ba37a445e2c25836d6",
                    "EndpointID": "",
                    "Gateway": "",
                    "IPAddress": "",
                    "IPPrefixLen": 0,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "MacAddress": "",
                    "DriverOpts": null
                }
            }
        }
    }
]
```

### docker rm daemon_dave
```
$ docker rm daemon_dave
daemon_dave
```
### docker ps -a
```
$ docker ps -a
CONTAINER ID   IMAGE                           COMMAND                  CREATED          STATUS                      PORTS                                  NAMES
8d3c1aee8a10   ubuntu                          "/bin/bash"              36 minutes ago   Exited (0) 31 minutes ago                                          bob_the_container
b5e6f9280dd5   ubuntu                          "/bin/bash"              47 minutes ago   Exited (0) 38 minutes ago                                          clever_kepler
016f2c53b0be   wurstmeister/kafka:2.11-2.0.0   "start-kafka.sh"         5 weeks ago      Exited (255) 2 days ago     0.0.0.0:9092->9092/tcp, 9093/tcp       e-kafka-1
54d2e38c991d   wurstmeister/zookeeper:3.4.6    "/bin/sh -c '/usr/sb…"   5 weeks ago      Exited (255) 2 days ago     22/tcp, 2181/tcp, 2888/tcp, 3888/tcp   e-zookeeper-1
c97b8b3af058   wurstmeister/kafka:2.11-2.0.0   "start-kafka.sh"         5 weeks ago      Exited (1) 5 weeks ago                                             bold_banach
```

## Chapter 4

### docker images

```
$ docker images
REPOSITORY               TAG          IMAGE ID       CREATED       SIZE
ubuntu                   latest       74f2314a03de   7 days ago    77.8MB
wurstmeister/kafka       2.11-2.0.0   568143d73a6b   4 years ago   339MB
wurstmeister/zookeeper   3.4.6        6fe5551964f5   7 years ago   451MB
```

### docker pull ubuntu:18.04

```
$ docker pull ubuntu:18.04
18.04: Pulling from library/ubuntu
58289280d3c7: Pull complete
Digest: sha256:1e32b9c52e8f22769df41e8f61066c77b2b35b0a423c4161c0e48eca2fd24f75
Status: Downloaded newer image for ubuntu:18.04
docker.io/library/ubuntu:18.04
```

### docker images

```
$ docker images
REPOSITORY               TAG          IMAGE ID       CREATED       SIZE
ubuntu                   latest       74f2314a03de   7 days ago    77.8MB
ubuntu                   18.04        b89fba62bc15   7 days ago    63.1MB
wurstmeister/kafka       2.11-2.0.0   568143d73a6b   4 years ago   339MB
wurstmeister/zookeeper   3.4.6        6fe5551964f5   7 years ago   451MB
```
### docker run -t -i --name new_container ubuntu:18.04 /bin/bash

```
$ docker run -t -i --name new_container ubuntu:18.04 /bin/bash
root@c032dea298f8:/# exit
exit
```

### docker images ubuntu

```
$ docker images ubuntu
REPOSITORY   TAG       IMAGE ID       CREATED      SIZE
ubuntu       latest    74f2314a03de   7 days ago   77.8MB
ubuntu       18.04     b89fba62bc15   7 days ago   63.1MB
```

### docker search pyspark

```
$ docker search pyspark
NAME                               DESCRIPTION                                     STARS     OFFICIAL   AUTOMATED
jupyter/pyspark-notebook           Python and Spark Jupyter Notebook Stack from…   263
godatadriven/pyspark               Apache PySpark                                  13                   [OK]
masroorhasan/pyspark               Docker container for running PySpark on Ubun…   2
ingkle/pyspark                     Pyspark for k8s with graalvm:java17-22.3.0 a…   1
clipper/pyspark-container          Container for deploying PySpark models to Cl…   1                    [OK]
beomi/pyspark-notebook-nlp         Jupyter + PySpark + Tensorflow/PyTorch(cpu) …   1
robertlgtucker/pyspark-java8       Pyspark with Java8                              1
hsci/pyspark-notebook-openshift    Version of the Jupyter pyspark-notebook that…   1
korniichuk/pyspark                 Apache PySpark                                  1                    [OK]
pysparkutils/jupyter-pyspark       Jupyter notebook configured to work with Pys…   1
yadist/pyspark                                                                     0
dnamlin/pyspark                                                                    0
alexcoppe/pyspark                  Docker image to play around with PySpark.       0                    [OK]
damei1807/pyspark-notebook                                                         0
mklabsio/pyspark                   Convenient PySpark image for running unit/in…   0
protonai/pyspark                   Base image for PySpark                          0
anantpukale/pyspark-notebook                                                       0
dboren/pyspark                                                                     0
lrdevops/pyspark                   centos7 based build image for pyspark 2.4 on…   0
cosmobot/pyspark                   Tag-locked image for running Pyspark on for …   0
kipparker/pyspark-emr-unit-tests   Suitable for CI tests requiring EMR compatib…   0
tfgco/pyspark-gitlab-ci                                                            0
devopsdymyr/pyspark                                                                0
octoenergy/pyspark                 Base image for testing pyspark applications     0
tjsongzw/pyspark
```

### mkdir static_web
```
$ mkdir static_web
```
### cd static_web
```
$ cd static_web
```
### nano Dockerfile
```
$ nano Dockerfile
```
### cat Dockerfile
```
$ cat Dockerfile
```
```docker 
# Version: 0.0.1
FROM ubuntu:18.04
RUN apt-get update; apt-get install -y nginx
RUN echo 'Hi, I am in your container' \
>/var/www/html/index.html
EXPOSE 80
```

### docker build -t "static_web" . 
```
$ docker build -t "static_web" .
[+] Building 26.5s (7/7) FINISHED
 => [internal] load build definition from Dockerfile                                                            0.0s
 => => transferring dockerfile: 201B                                                                            0.0s
 => [internal] load .dockerignore                                                                               0.0s
 => => transferring context: 2B                                                                                 0.0s
 => [internal] load metadata for docker.io/library/ubuntu:18.04                                                 0.0s
 => [1/3] FROM docker.io/library/ubuntu:18.04                                                                   0.1s
 => [2/3] RUN apt-get update; apt-get install -y nginx                                                         23.0s
 => [3/3] RUN echo 'Hi, I am in your container' >/var/www/html/index.html                                       2.4s
 => exporting to image                                                                                          0.7s
 => => exporting layers                                                                                         0.6s
 => => writing image sha256:b75e274d9a6823adc52e9603332b6847480ca45690cef7c416a2ae813d5756a7                    0.0s
 => => naming to docker.io/library/static_web                                                                   0.0s

Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them
```
### docker images
```
$ docker images
REPOSITORY               TAG          IMAGE ID       CREATED         SIZE
static_web               latest       b75e274d9a68   3 minutes ago   168MB
ubuntu                   latest       74f2314a03de   7 days ago      77.8MB
ubuntu                   18.04        b89fba62bc15   7 days ago      63.1MB
wurstmeister/kafka       2.11-2.0.0   568143d73a6b   4 years ago     339MB
wurstmeister/zookeeper   3.4.6        6fe5551964f5   7 years ago     451MB
```

### docker history static_web

```
$ docker history static_web
IMAGE          CREATED          CREATED BY                                      SIZE      COMMENT
b75e274d9a68   45 minutes ago   EXPOSE map[80/tcp:{}]                           0B        buildkit.dockerfile.v0
<missing>      45 minutes ago   RUN /bin/sh -c echo 'Hi, I am in your contai…   27B       buildkit.dockerfile.v0
<missing>      45 minutes ago   RUN /bin/sh -c apt-get update; apt-get insta…   105MB     buildkit.dockerfile.v0
<missing>      7 days ago       /bin/sh -c #(nop)  CMD ["/bin/bash"]            0B
<missing>      7 days ago       /bin/sh -c #(nop) ADD file:66eb2ef5574cdf80b…   63.1MB
<missing>      7 days ago       /bin/sh -c #(nop)  LABEL org.opencontainers.…   0B
<missing>      7 days ago       /bin/sh -c #(nop)  LABEL org.opencontainers.…   0B
<missing>      7 days ago       /bin/sh -c #(nop)  ARG LAUNCHPAD_BUILD_ARCH     0B
<missing>      7 days ago       /bin/sh -c #(nop)  ARG RELEASE                  0B
```
### docker run -d -p 80 --name static_web static_web nginx -g "daemon off;"
```
$ docker run -d -p 80 --name static_web static_web nginx -g "daemon off;"
8ecbabf9ec8ad68c0bd1138ddfc318cadeb57387522432367d85bbebb3eb9638
```
### docker ps
```
$ docker ps
CONTAINER ID   IMAGE        COMMAND                  CREATED              STATUS              PORTS                   NAMES
8ecbabf9ec8a   static_web   "nginx -g 'daemon of…"   About a minute ago   Up About a minute   0.0.0.0:62488->80/tcp   static_web
```
### docker port static_web 80
```
$ docker port static_web 80
0.0.0.0:62488
```
### curl localhost:62488
```
$ curl localhost:62488
Hi, I am in your container
```

## Dockerfile instructions

### CMD
```
$ cat Dockerfile
# Version: 0.0.1
FROM ubuntu:18.04
RUN apt-get update; apt-get install -y nginx
RUN echo 'Hi, I am in your container' \
>/var/www/html/index.html
EXPOSE 80
CMD ["/bin/bash", "-l"]

```
```
$ docker build -t="gigo123/static_web" .                                            
[+] Building 0.5s (7/7) FINISHED                                                                                      
=> [internal] load .dockerignore                                                                              
0.1s  => => transferring context: 2B                                                                                 
0.1s  => [internal] load build definition from Dockerfile                                                            
0.2s  => => transferring dockerfile: 225B                                                                            
0.1s  => [internal] load metadata for docker.io/library/ubuntu:18.04                                                 
0.0s  => [1/3] FROM docker.io/library/ubuntu:18.04                                                                   
0.0s  => CACHED [2/3] RUN apt-get update; apt-get install -y nginx                                                   
0.0s  => CACHED [3/3] RUN echo 'Hi, I am in your container' >/var/www/html/index.html                                
0.0s  => exporting to image                                                                                          
0.2s  => => exporting layers                                                                                         
0.0s  => => writing image sha256:28c139591f31f021b4656881e7d66ede76eedba2036218f8437bc9436427ff91                    
0.1s  => => naming to docker.io/gigo123/static_web                                                                   
0.0s                                                                                                                      
Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them                    
$ docker run -i -t gigo123/static_web
root@1b092e80ebdd:/# pwd
/
root@1b092e80ebdd:/# exit
logout

$ docker ps -a
CONTAINER ID   IMAGE                           COMMAND                  CREATED          STATUS                     PORTS                                  NAMES
1b092e80ebdd   gigo123/static_web              "/bin/bash -l"           15 seconds ago   Exited (0) 5 seconds ago                                          infallible_moore
c032dea298f8   ubuntu:18.04                    "/bin/bash"              4 days ago       Exited (0) 4 days ago                                             new_container
8d3c1aee8a10   ubuntu                          "/bin/bash"              4 days ago       Exited (0) 4 days ago                                             bob_the_container
b5e6f9280dd5   ubuntu                          "/bin/bash"              4 days ago       Exited (0) 4 days ago                                             clever_kepler
016f2c53b0be   wurstmeister/kafka:2.11-2.0.0   "start-kafka.sh"         6 weeks ago      Exited (255) 6 days ago    0.0.0.0:9092->9092/tcp, 9093/tcp       e-kafka-1
54d2e38c991d   wurstmeister/zookeeper:3.4.6    "/bin/sh -c '/usr/sb…"   6 weeks ago      Exited (255) 6 days ago    22/tcp, 2181/tcp, 2888/tcp, 3888/tcp   e-zookeeper-1
c97b8b3af058   wurstmeister/kafka:2.11-2.0.0   "start-kafka.sh"         6 weeks ago      Exited (1) 5 weeks ago                                            bold_banach
```
### ENTRYPOINT
```
$ cat Dockerfile
# Version: 0.0.1
FROM ubuntu:18.04
RUN apt-get update; apt-get install -y nginx
RUN echo 'Hi, I am in your container' \
>/var/www/html/index.html
EXPOSE 80
ENTRYPOINT ["/usr/sbin/nginx"]

$ docker build -t="gigo123/static_web" .
[+] Building 0.2s (7/7) FINISHED
 => [internal] load build definition from Dockerfile                                                            0.0s
 => => transferring dockerfile: 254B                                                                            0.0s
 => [internal] load .dockerignore                                                                               0.0s
 => => transferring context: 2B                                                                                 0.0s
 => [internal] load metadata for docker.io/library/ubuntu:18.04                                                 0.0s
 => [1/3] FROM docker.io/library/ubuntu:18.04                                                                   0.0s
 => CACHED [2/3] RUN apt-get update; apt-get install -y nginx                                                   0.0s
 => CACHED [3/3] RUN echo 'Hi, I am in your container' >/var/www/html/index.html                                0.0s
 => exporting to image                                                                                          0.0s
 => => exporting layers                                                                                         0.0s
 => => writing image sha256:eb59899781a72c6faab6cae70a34a8c1d64e88dbe8002536ebfd432c04b84f68                    0.0s
 => => naming to docker.io/gigo123/static_web                                                                   0.0s
 $ docker run -i -t gigo123/static_web
 $ docker ps
CONTAINER ID   IMAGE                COMMAND                  CREATED         STATUS         PORTS     NAMES
bfbc0645365d   gigo123/static_web   "/usr/sbin/nginx -g …"   2 minutes ago   Up 2 minutes   80/tcp    happy_curran
```
### WORKDIR
```
$ cat Dockerfile
# Version: 0.0.1
FROM ubuntu:18.04
RUN apt-get update; apt-get install -y nginx
RUN echo 'Hi, I am in your container' \
>/var/www/html/index.html
EXPOSE 80
WORKDIR /bin/

$ docker build -t="gigo123/static_web" .
[+] Building 1.1s (9/9) FINISHED
 => [internal] load build definition from Dockerfile                                                            0.0s
 => => transferring dockerfile: 227B                                                                            0.0s
 => [internal] load .dockerignore                                                                               0.0s
 => => transferring context: 2B                                                                                 0.0s
 => [internal] load metadata for docker.io/library/ubuntu:18.04                                                 0.0s
 => [1/5] FROM docker.io/library/ubuntu:18.04                                                                   0.0s
 => CACHED [2/5] RUN apt-get update; apt-get install -y nginx                                                   0.0s
 => CACHED [3/5] RUN echo 'Hi, I am in your container' >/var/www/html/index.html                                0.0s
 => [4/5] WORKDIR /bin/                                                                                         0.1s
 => [5/5] RUN ls -l                                                                                             0.6s
 => exporting to image                                                                                          0.3s
 => => exporting layers                                                                                         0.2s
 => => writing image sha256:fda7623e574bcdbf4fd4164588680a15c6b409c8cbcf05ec30b787555ec88a40                    0.0s
 => => naming to docker.io/gigo123/static_web                                                                   0.0s
o
Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them

$ docker run -i -t gigo123/static_web
root@bc5655ba4dce:/bin#

```
### ENV
```
$ cat Dockerfile
# Version: 0.0.1
ENV WORKING_DIRECTORY = /bin/
FROM ubuntu:18.04
RUN apt-get update; apt-get install -y nginx
RUN echo 'Hi, I am in your container' \
>/var/www/html/index.html
EXPOSE 80
WORKDIR WORKING_DIRECTORY

$ docker build -t="gigo123/static_web" .
[+] Building 0.1s (2/2) FINISHED
 => [internal] load build definition from Dockerfile                                                            0.0s
 => => transferring dockerfile: 259B                                                                            0.0s
 => [internal] load .dockerignore                                                                               0.0s
 => => transferring context: 2B                                                                                 0.0s
failed to solve with frontend dockerfile.v0: failed to create LLB definition: no build stage in current context

$ docker run -i -t gigo123/static_web
root@46f0569f47f7:/bin#

```
### ADD
```
$ cat Dockerfile
# Version: 0.0.1
FROM ubuntu:18.04
RUN apt-get update; apt-get install -y nginx
RUN echo 'Hi, I am in your container' \
>/var/www/html/index.html
EXPOSE 80
ADD sample_text.txt /sample_text.txt

$ docker build -t="gigo123/static_web" .
[+] Building 0.4s (9/9) FINISHED
 => [internal] load build definition from Dockerfile                                                            0.0s
 => => transferring dockerfile: 240B                                                                            0.0s
 => [internal] load .dockerignore                                                                               0.0s
 => => transferring context: 2B                                                                                 0.0s
 => [internal] load metadata for docker.io/library/ubuntu:18.04                                                 0.0s
 => [1/4] FROM docker.io/library/ubuntu:18.04                                                                   0.0s
 => [internal] load build context                                                                               0.0s
 => => transferring context: 55B                                                                                0.0s
 => CACHED [2/4] RUN apt-get update; apt-get install -y nginx                                                   0.0s
 => CACHED [3/4] RUN echo 'Hi, I am in your container' >/var/www/html/index.html                                0.0s
 => [4/4] ADD sample_text.txt /sample_text.txt                                                                  0.1s
 => exporting to image                                                                                          0.1s
 => => exporting layers                                                                                         0.0s
 => => writing image sha256:172a51a2cb99d8c91957d59d8eabd776ceff20154109f4df5bace03e8055cd74                    0.0s
 => => naming to docker.io/gigo123/static_web                                                                   0.0s

Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them

b$ docker run -i -t gigo123/static_web
root@e090e24a2d4c:/# ls -l
total 80
drwxr-xr-x   1 root root 4096 Mar  9 13:59 bin
drwxr-xr-x   2 root root 4096 Apr 24  2018 boot
drwxr-xr-x   5 root root  360 Mar 12 21:36 dev
drwxr-xr-x   1 root root 4096 Mar 12 21:36 etc
drwxr-xr-x   2 root root 4096 Apr 24  2018 home
drwxr-xr-x   1 root root 4096 May 23  2017 lib
drwxr-xr-x   2 root root 4096 Mar  1 02:04 lib64
drwxr-xr-x   2 root root 4096 Mar  1 02:03 media
drwxr-xr-x   2 root root 4096 Mar  1 02:03 mnt
drwxr-xr-x   2 root root 4096 Mar  1 02:03 opt
dr-xr-xr-x 283 root root    0 Mar 12 21:36 proc
drwx------   2 root root 4096 Mar  1 02:04 root
drwxr-xr-x   5 root root 4096 Mar  1 02:04 run
-rw-r--r--   1 root root   13 Mar 12 21:29 sample_text.txt
drwxr-xr-x   1 root root 4096 Mar  9 13:59 sbin
drwxr-xr-x   2 root root 4096 Mar  1 02:03 srv
dr-xr-xr-x  11 root root    0 Mar 12 21:36 sys
drwxrwxrwt   1 root root 4096 Mar  9 13:59 tmp
drwxr-xr-x   1 root root 4096 Mar  1 02:03 usr
drwxr-xr-x   1 root root 4096 Mar  9 13:59 var
root@e090e24a2d4c:/# exit
exit

```
### COPY
```
$ cat Dockerfile
# Version: 0.0.1
FROM ubuntu:18.04
RUN apt-get update; apt-get install -y nginx
RUN echo 'Hi, I am in your container' \
>/var/www/html/index.html
EXPOSE 80
COPY copy_text.txt /copy_text.txt
$ docker build -t="gigo123/static_web" .
[+] Building 0.6s (9/9) FINISHED
 => [internal] load build definition from Dockerfile                                                            0.0s
 => => transferring dockerfile: 237B                                                                            0.0s
 => [internal] load .dockerignore                                                                               0.0s
 => => transferring context: 2B                                                                                 0.0s
 => [internal] load metadata for docker.io/library/ubuntu:18.04                                                 0.0s
 => [1/4] FROM docker.io/library/ubuntu:18.04                                                                   0.0s
 => [internal] load build context                                                                               0.0s
 => => transferring context: 50B                                                                                0.0s
 => CACHED [2/4] RUN apt-get update; apt-get install -y nginx                                                   0.0s
 => CACHED [3/4] RUN echo 'Hi, I am in your container' >/var/www/html/index.html                                0.0s
 => [4/4] COPY copy_text.txt /copy_text.txt                                                                     0.2s
 => exporting to image                                                                                          0.1s
 => => exporting layers                                                                                         0.1s
 => => writing image sha256:40a9324a13128bc6564d9f110851cf0104b24b1a686b83311a2ebcc31c9b7b22                    0.0s
 => => naming to docker.io/gigo123/static_web                                                                   0.0s

Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them

$ docker run -i -t gigo123/static_web
root@f1f8de9f5c97:/# ls -l
total 80
drwxr-xr-x   1 root root 4096 Mar  9 13:59 bin
drwxr-xr-x   2 root root 4096 Apr 24  2018 boot
-rw-r--r--   1 root root   10 Mar 12 21:57 copy_text.txt
drwxr-xr-x   5 root root  360 Mar 12 21:58 dev
drwxr-xr-x   1 root root 4096 Mar 12 21:58 etc
drwxr-xr-x   2 root root 4096 Apr 24  2018 home
drwxr-xr-x   1 root root 4096 May 23  2017 lib
drwxr-xr-x   2 root root 4096 Mar  1 02:04 lib64
drwxr-xr-x   2 root root 4096 Mar  1 02:03 media
drwxr-xr-x   2 root root 4096 Mar  1 02:03 mnt
drwxr-xr-x   2 root root 4096 Mar  1 02:03 opt
dr-xr-xr-x 265 root root    0 Mar 12 21:58 proc
drwx------   2 root root 4096 Mar  1 02:04 root
drwxr-xr-x   5 root root 4096 Mar  1 02:04 run
drwxr-xr-x   1 root root 4096 Mar  9 13:59 sbin
drwxr-xr-x   2 root root 4096 Mar  1 02:03 srv
dr-xr-xr-x  11 root root    0 Mar 12 21:58 sys
drwxrwxrwt   1 root root 4096 Mar  9 13:59 tmp
drwxr-xr-x   1 root root 4096 Mar  1 02:03 usr
drwxr-xr-x   1 root root 4096 Mar  9 13:59 var

```
### ARG
```
$ cat Dockerfile
# Version: 0.0.1
FROM ubuntu:18.04
RUN apt-get update; apt-get install -y nginx
RUN echo 'Hi, I am in your container' \
>/var/www/html/index.html
EXPOSE 80
ARG WORK_DIR
WORKDIR ${WORK_DIR}
$ docker build --build-arg WORK_DIR=/bin/ -t="gigo123/static_web" .
[+] Building 0.2s (8/8) FINISHED
 => [internal] load build definition from Dockerfile                                                            0.0s
 => => transferring dockerfile: 234B                                                                            0.0s
 => [internal] load .dockerignore                                                                               0.0s
 => => transferring context: 2B                                                                                 0.0s
 => [internal] load metadata for docker.io/library/ubuntu:18.04                                                 0.0s
 => [1/4] FROM docker.io/library/ubuntu:18.04                                                                   0.0s
 => CACHED [2/4] RUN apt-get update; apt-get install -y nginx                                                   0.0s
 => CACHED [3/4] RUN echo 'Hi, I am in your container' >/var/www/html/index.html                                0.0s
 => CACHED [4/4] WORKDIR /bin/                                                                                  0.0s
 => exporting to image                                                                                          0.0s
 => => exporting layers                                                                                         0.0s
 => => writing image sha256:d5e6d18fb95f9c185de484135a6dc00b9b31ca9aac13320cc382fd582d93b279                    0.0s
 => => naming to docker.io/gigo123/static_web                                                                   0.0s

Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them
$ docker run -i -t gigo123/static_web
root@0e6d2d7714f5:/bin# exit
exit
```


### docker build --no-cache -t"gigo123/static_web" .
```
$ docker build --no-cache -t"gigo123/static_web" .

[+] Building 107.0s (7/7) FINISHED                                                                                    
=> [internal] load build definition from Dockerfile                                                            
0.0s  => => transferring dockerfile: 38B                                                                             
0.0s  => [internal] load .dockerignore                                                                               
0.0s  => => transferring context: 2B                                                                                 
0.0s  => [internal] load metadata for docker.io/library/ubuntu:18.04                                                 
0.0s  => CACHED [1/3] FROM docker.io/library/ubuntu:18.04                                                            
0.0s  => [2/3] RUN apt-get update; apt-get install -y nginx                                                        
105.8s  => [3/3] RUN echo 'Hi, I am in your container' >/var/www/html/index.html                                       
0.5s  => exporting to image                                                                                          
0.5s  => => exporting layers                                                                                         
0.5s  => => writing image sha256:2cd023d819465e336ccc67cf2f0e1874dd220a06aed2041c4a19d9fead67f850                    
0.0s  => => naming to docker.io/gigo123/static_web                                                                   
0.0s                                    
```

### docker push gigo123/static_web
```
$ docker push gigo123/static_web
Using default tag: latest
The push refers to repository [docker.io/gigo123/static_web]
23baabfc238d: Pushed
a4ee09aefbe5: Pushed
52c5ca3e9f3b: Pushed
```
### docker images
```
REPOSITORY               TAG          IMAGE ID       CREATED         SIZE
gigo123/static_web       latest       2cd023d81946   7 minutes ago   168MB
<none>                   <none>       b75e274d9a68   20 hours ago    168MB
ubuntu                   latest       74f2314a03de   8 days ago      77.8MB
ubuntu                   18.04        b89fba62bc15   8 days ago      63.1MB
wurstmeister/kafka       2.11-2.0.0   568143d73a6b   4 years ago     339MB
wurstmeister/zookeeper   3.4.6        6fe5551964f5   7 years ago     451MB
```

### docker rmi b75e274d9a68
```
$ docker rmi b75e274d9a68
Error response from daemon: conflict: unable to delete b75e274d9a68 (must be forced) - image is being used by stopped container 8ecbabf9ec8a
```
### docker rm 8ecbabf9ec8a
```
$ docker rm 8ecbabf9ec8a
8ecbabf9ec8a
```
### docker ps -a
```
$ docker ps -a
CONTAINER ID   IMAGE                           COMMAND                  CREATED        STATUS                    PORTS                                  NAMES
c032dea298f8   ubuntu:18.04                    "/bin/bash"              21 hours ago   Exited (0) 21 hours ago                                          new_container
8d3c1aee8a10   ubuntu                          "/bin/bash"              22 hours ago   Exited (0) 22 hours ago                                          bob_the_container
b5e6f9280dd5   ubuntu                          "/bin/bash"              22 hours ago   Exited (0) 22 hours ago                                          clever_kepler
016f2c53b0be   wurstmeister/kafka:2.11-2.0.0   "start-kafka.sh"         5 weeks ago    Exited (255) 2 days ago   0.0.0.0:9092->9092/tcp, 9093/tcp       e-kafka-1
54d2e38c991d   wurstmeister/zookeeper:3.4.6    "/bin/sh -c '/usr/sb…"   5 weeks ago    Exited (255) 2 days ago   22/tcp, 2181/tcp, 2888/tcp, 3888/tcp   e-zookeeper-1
c97b8b3af058   wurstmeister/kafka:2.11-2.0.0   "start-kafka.sh"         5 weeks ago    Exited (1) 5 weeks ago                                           bold_banach
```

### docker rmi b75e274d9a68
```
$ docker rmi b75e274d9a68
Deleted: sha256:b75e274d9a6823adc52e9603332b6847480ca45690cef7c416a2ae813d5756a7
```
