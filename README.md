WSL2 Docker Environment Setup
=============================

We assumed that you have activated WSL2 environment with Ubuntu installed. 
Different Linux distribution might have different packages requirements, so please check in previous on your own.  
We don't recommend users to install Docker Desktop since the network routing in such environment will be complex and may break existing services inside your WSL2.

### 1. Install docker engine

Please follow This document: https://docs.docker.com/engine/install/ubuntu/#installation-methods

### 2. Add the following line to `.bashrc`, or `.zshrc` if you're using zsh, so that when you start linux shell, docker daemon could be started automatically:

```bash
wsl.exe -u root -d Ubuntu service docker status > /dev/null || wsl.exe -u root -d Ubuntu service docker start > /dev/null
```

### 3. Enable systemd in WSL2 (Optional)

If you are not able to upgrade WSL to the experimental version, you may want to try the following method:
[gist](https://gist.github.com/djfdyuruiry/6720faa3f9fc59bfdf6284ee1f41f950)

The only issue for the setup in the link is that when launching the second WSL session, genie will be restarted again.<br>
To prevent this, add the following lines in your `.bashrc`:

```bash
if [[ -z ${INSIDE_GENIE} ]]; then
  exec /usr/bin/genie -s
fi
```
