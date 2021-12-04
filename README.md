# Submodule with git action to update parent 

This document is explaining how to configure and create action which will update parent to point always on latest commit
of its submodule

----------------
First we need to create new SSH key which we will use in our git action
[GitHub Pages](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)

*Note: It is recomended to create new SSH key and not to use existing *

Once we created SSH key we will copy private key and paste it into repository (submodule) secrets with name : *SSH_PRIVATE_KEY*

Then we will create git action with steps:
* Set up SSH Agent to use SSH_PRIVATE_KEY
* Checkout to parent repository
* Pull & update submodules recursively
* Commit and Push changes

Example of action can be found under workflows/submodule_update