Overview
========

Whereas git does not provide a ``post-clone`` hook, this project
effectively provides a the functionality of a ``post-clone`` hook
(implemented with a ``post-checkout`` hook).  You may use this project
to invoke your own ``post-clone`` hook, and to install various hooks
in the local repository after cloning.

Usage
=====

#. Clone this repository somewhere on disk::

    git clone https://github.com/EricCrosson/git-post-clone-hook /tmp/git-post-clone-hook

#. Clone the desired repository::

    git clone --template=/tmp/git-post-clone-hook git@github.com:username/repo-of-interest

In addition to cloning the repository, this method will: ensure 

- if present in the cloned repo, ``/hooks/`` is symlinked to ``/.git/hooks/``
- if present in the cloned repo, ``/.git/hooks/post-clone`` is invoked

    **Note**: this hook will not be automatically invoked again.

Benefits
========

Using this ``post-clone`` template allows repo maintainers to

- automate installation of client-side git hooks
- version-control this automation inside the relevant repository

Acknowledgements
================

This git hook was inspired by `this StackOverflow post`_.

.. _this StackOverflow post: http://stackoverflow.com/questions/2141492/git-clone-and-post-checkout-hook/2141577#2141577
