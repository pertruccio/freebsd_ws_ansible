# Installation Steps
## 1. install, enable ssh
```
pkg install sshd, nano
nano /etc/ssh/sshd_config
# enable root login
nano /etc/rc.conf
# add sshd_enable="YES"
service sshd start
```
## 2. install python, git, ansible
```
pkg install python37, git, py37-ansible
```
## 3. download vault password secret
- put the vault secret to /root/.vault_file
## 4. run ansible-pull
```
ansible-pull -U https://github.com/pertruccio/freebsd_ws_ansible -i inventory --vault-password-file=~/.vault_file
```
## 5. install, compile lsd
```
cargo install lsd
# sometimes there is a compile error in module terminal size, 
# you need to change TIOCGWINSZ to TIOCGWINSZ.into() in the file 
# /root/.cargo/registry/src/github.com-1ecc6299db9ec823/terminal_size-0.1.10/src/unix.rs
```
