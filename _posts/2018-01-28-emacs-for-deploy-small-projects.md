---
layout: post
title: Emacs for deploy small programs
---

**Work in progress**


Run code close to data by sending it to more powerful machine in the
same network of the database server can speedup analysis. Although
there are modern tools to do that, the size of the project does not
justify the use of these tools. For these projects, I utilize Emacs
and its modes: orgmode and tramp. These tools can be useful to deploy
small projects as Howardisms mention in his blog [Literate
DevOps](http://howardism.org/Technical/Emacs/literate-devops.html).


Example to move code 
```
    #+begin_src sh :session *tmp* :results output
      scp -pr -i ~/demo_server.pem utils.py  USER@HOST:/home/user/project/
      echo "done"
    #+end_src

```


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
