---
title: Gitflow
layout: default
parent: Technique
---

## Commit policy :

### Branches : 

- fix/ = bug fix  
- feat/ = user feature - must be associated to an EPIC issue
    - step/ = step toward a user feature, must be stacked upon a feat branch and be related to an issue
- refactor/ = important reworking of the code, must be related to an issue that has been prioritized. For everyday improvment, use scout/

- scout/ = linting and [scout-rule](https://matheus.ro/2017/12/11/clean-code-boy-scout-rule/), may not be related to an issue
- master = deployed version (beta and prod are marqued by tag), any new merge to master is considered as a new version.
    - each commit to master must comes via a merge and follow the template emoji:version:prefix:description. 
    - each commit to master is emphasised by an emoji depending on the kind of change 
        - fix -> :bug:
        - feat -> :sparkles:
        - refactor -> :stethoscope:
        - scout -> :recycle:
        - breaking changes no matter their kind -> :rotating_light:
    - versionning :
        - fix -> upgrade \_.\_.X
        - scout -> upgrade \_.\_.X
        - refactor -> upgrade \_.X.\_
        - feat -> upgrade \_.X.\_
        - breaking change -> upgrade X.\_.\_



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
