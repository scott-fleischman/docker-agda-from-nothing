FROM        haskell:7.10.3
MAINTAINER  Scott Fleischman <scott.fleischman@logos.com>

RUN cabal update
RUN cabal install Agda-2.5.1

RUN apt-get update
RUN apt-get install -y emacs24-nox

RUN touch ~/.emacs
RUN echo "(load-file (let ((coding-system-for-read 'utf-8)) (shell-command-to-string \"agda-mode locate\")))" >> ~/.emacs

RUN apt-get install -y git
RUN git clone https://github.com/scott-fleischman/agda-from-nothing ~/agda-from-nothing

CMD emacs ~/agda-from-nothing/Exercises/01-Boolean.agda
