
# install containerd in offline mode with service with commands 
note: go to root user `sudo su`
1. unrar files 
```
tar Cxzvf /usr/local containerd-1.6.2-linux-amd64.tar.gz
```
2. move file containerd.service to `/etc/systemd/system/`
```
mv containerd.service /etc/systemd/system/
```
3. execute this commands
```
systemctl daemon-reload
systemctl enable --now containerd
```
4. The binary is built statically and should work on any Linux distribution.
```
install -m 755 runc.amd64 /usr/local/sbin/runc
```
5. 
```
$ mkdir -p /opt/cni/bin
$ tar Cxzvf /opt/cni/bin cni-plugins-linux-amd64-v1.5.1.tgz 
```
6. file config create and config file
```
$ mkdir  /etc/containerd/
$ touch /etc/containerd/config.toml
```
7. check to install or any thing 
```
ctr
```
# install with ansible role install_containerd_offline
note: first load file of conatinerd and another file from containerd [github account] ([/guides/content/editing-an-existing-page](https://github.com/containerd/containerd/blob/main/docs/getting-started.md))
```
 ansible-playbook -i inventory.ini playbook.yml
```