---
title: Bug Journal
layout: default
parent: Technique
---

# Qu'avait il fait dans cette galère ?

{: .note }
>This file is used as a reference for any bug encountered during the project.
>
>Its purpose is to take the time to reflect on what was learned while solving it and identify recurring ones.

Copy the following template to add a new bug description :

--------------
## Bug description

*how long* :

*what happened* :

*why* :

*what did i do to fix it* :

*how often* :

--------------
## `NextRouter` was not mounted

*how long* : 2min

*what happened* :
can't use the useRouter function

*why* :
because we use the app structure instead of the pages but the useRouter was imported from "next/router"

*what did i do to fix it* :
should use useRouter from "next/navigation"

*how often* : 2

--------------

### The virtual environment found in /home/.../gdrsante-Wj0OGRaF-py3.10 seems to be broken.

*how long* : 5 min

*what happened* :
  the nixos package of python change from 3.10 to 3.11 so the env wasn't correct anymore
  when deleted and recreated the package weren't installed so pytest and flask not found

*why* :

*what did i do to fix it* :

https://stackoverflow.com/questions/61351659/the-virtual-environment-found-seems-to-be-broken-python-poetry
  - poetry env remove drsante-Wj0OGRaF-py3.10
  - poetry env use python3.11
*how often* :
