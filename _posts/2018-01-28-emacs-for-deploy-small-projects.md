---
layout: post
title: Emacs for deploy small programs
---

**Work in progress**

# Literate DevOpts

Run code close to data by sending it to more powerful machine in the
same network of the database server can speedup analysis. Although
there are modern tools to do that, the size of the project does not
justify the use of these tools. For these projects, I utilize
[Emacs](https://www.gnu.org/software/emacs/) and its modes:
[orgmode](https://orgmode.org/),
[org-babel](https://orgmode.org/worg/org-contrib/babel/) and
[tramp](https://www.gnu.org/software/tramp/). These tools can be
useful to deploy small projects as Howardisms mention in his blog
[Literate
DevOps](http://howardism.org/Technical/Emacs/literate-devops.html).

Orgmode is powerful mode for keep notes, mantain todo list and project
planing. Org-babel gives ability to org-mode to execute source inside
orgmode documents in many different languages. Tramp gives ability to
Emacs to edit remote files tranparant like local file and also run
remote shells. orgmode, org-babel and tramp comes with emacs by
default.

## Move code

In order to move your code to the remote machine you just need to
press *C-c C-c* with the cursor in the org-babel block
below. org-bable will create a session that can be used in the next
necessary steps

```
#+begin_src sh 
  scp -pr -i ~/demo_server.pem utils.py  USER@HOST:/home/user/project/
  echo "done"
#+end_src
```

## Create seesion in the remote machine

### Create a session in the remote machine

```

#+begin_src sh :session *deploy*  :results output
  ## ssh to the server
  ssh -i ~/demo_server.pem USER@HOST
#+end_src

```

### Create folders

```

#+begin_src sh :session *delploy* :results output
   mkdir -p ~/data
#+end_src

```

### Install requirments

```

#+begin_src sh :session *deploy* :results output
  pip install REQUIREMENT
#+end_src

```

### Exit session


```

#+begin_src sh :session *deploy*  :results output
  exit
#+end_src

```

## Get shell in remote machine

Define function to run remote shell 

```
   #+begin_src emacs-lisp
     (defun my-remote-shell()
         (interactive)
         (let ((default-directory "/ssh:USER@HOST:/home/USER/project/"))
           (eshell)))

     ;; Run: Alt-x my-remote-shell
   #+end_src

```

By pressing *C-c C-c* with the cursor in the org-babel block above you
define a lisp function that open eshell buffer in the remote
server. To run the function in emacs minibuffer run: *M-x
my-remote-shell*
