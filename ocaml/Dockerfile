FROM ubuntu:16.04
ENV DEBIAN_FRONTEND noninteractive
MAINTAINER Noritaka Horio <holy.shared.design@gmail.com>
RUN apt-get -y update
RUN apt-get -y install sudo m4 opam
RUN adduser --disabled-password --gecos "" ocaml
RUN passwd -l ocaml
ADD ocamlsudo /etc/sudoers.d/ocaml
RUN chmod 440 /etc/sudoers.d/ocaml
RUN chown root:root /etc/sudoers.d/ocaml
RUN chown -R ocaml:ocaml /home/ocaml
USER ocaml
ENV HOME /home/ocaml
WORKDIR /home/ocaml
USER ocaml
RUN sudo -u ocaml sh -c "opam init -y"
RUN sudo -u ocaml sh -c "opam switch 4.04.1"
RUN sudo -u ocaml sh -c "opam install oasis ocamlfind camlp4"
