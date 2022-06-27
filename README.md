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
