Git
===

Data Model
::::::::::

* Object := (sha1) -> (headers, body)

  * The sha1 is always the full content hash (headers + body) and thus is a signature of the object and dependant objects.
  * TODO : find links to proofs of what can be forged and what can't be. For example, I have the feeling from Linus talks that a commit in the middle of an history can't be forged, because it's impossible not to modify the subsequent commits by doing it. But is it possible to forge a blob content to choose its hash? Or even a leaf commit?

* Commit (Object)::

    tree 0fdc764f4c477e55f9326b1340af175cd823518c # root tree describing this commit's snapshot
    parent 723781bf7cc1a6eb8bdecd987975b8af7ed960bb # 0, 1 or more parent commits (0 is first commit, 1 is normal commit, more is merge commit)
    author Romain Dorgueil <romain@dorgueil.net> 1459760873 +0200 (author and authored date)
    committer Romain Dorgueil <romain@dorgueil.net> 1459760873 +0200 (committer and committed date)
    
    commit message is the body

* Tree (Object)

  A tree has no header, only contains a list (one by line) of children, whith (perms, type, sha1, filename) as tab separated values. It represents what a regular filesystem would call a «directory», replacing inodes by hashes so the sub-nodes are identified in a universal namespace instead of a locally determined namespace.
    
  Example::

    40000   tree  67a00caf3712f4a38c9da6d14a07420530714fb5   doc
    100755  blob  d22a068dc89ac8d25532b0fea8829832e278ee7a   docker-compose.yml
    
* Blob (Object)

  A blob is representing a file content. It's important to understand that it only represents the content, and not where is it in the filesystem or what name points to it.
  For example, if two files have the exact same content, it will be stored only once in the git object database, and the two tree entries (either in two different trees or even in the same tree) will point to the same sha1 hash.

Aliases
:::::::

.. code-block:: shell

	git config --global alias.ci commit
	git config --global alias.st status
	git config --global alias.co checkout
	git config --global alias.br branch
	git config --global alias.lg "log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"

User setup
::::::::::

.. code-block:: shell

	git config --global user.name "Romain Dorgueil"
	git config --global user.email "romain@dorgueil.net"

	
References
::::::::::

* `Original article with my git config and aliases <http://romain.dorgueil.net/blog/en/git/2014/12/16/git-config.html>`_
* Github flow: https://guides.github.com/introduction/flow/
* Git-flow: http://nvie.com/posts/a-successful-git-branching-model/


*Deprecated* - Colors (not required after git 1.8.4)
::::::::::::::::::::::::::::::::::::::::::::::::::::

.. code-block:: shell

	git config --global color.branch auto
	git config --global color.diff auto
	git config --global color.interactive auto
	git config --global color.status auto

or

.. code-block:: shell

	git config --global color.ui true
