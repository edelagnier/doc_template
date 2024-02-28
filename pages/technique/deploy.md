---
title: Deployment
layout: default
parent: Technique
---

## Setup 

### Using Nix (recommanded)

Nix is a package manager that can be used on any platform (linux, mac, windows..)

It allows you to create isolated environnements with all the requirements of the project as documented by the ```shell.nix``` file

``` sh
sh <(curl -L https://nixos.org/nix/install) --no-daemon # install on linux
```

For other platform (linux, mac, windows) see the [official documentation](https://nixos.org/download.html)

### Others

All the packages required for the project are listed in the ```shell.nix``` files available in ./server and ./web
You can install them directly on your machine then proceed to the next step.

## Run

The BackEnd and FrontEnd even if stored in the same repo are treated as separate projects each with their own configuration and requirements.
They can be run independantly with the following commands at the root of the relevant folder (./server for the BackEnd and ./web for the FrontEnd)

``` sh
nix-shell --pure # (if using nix) enter the isolated environnement 
task # will list the available scripts for this project
task run # will start the program
```

## Testing 

``` sh
nix-shell --pure # (if using nix) enter the isolated environnement 
task test
```
