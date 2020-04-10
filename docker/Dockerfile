############################################################
# Octave + DSP pkgs
#
# GNU Octave plus control and signal packages
# https://www.gnu.org/software/octave/
#
# Octave is an open source scientific programming language
# based off of and mostly compatible with Matlab.
#
############################################################

FROM ubuntu:18.04
MAINTAINER john.arroyo@gmail.com

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update \
    && apt-get install -y octave liboctave-dev less make \
    && apt-get clean

RUN useradd -ms /bin/bash octave
ADD install.m /home/octave
RUN chown -R octave:octave /home/octave/

RUN octave /home/octave/install.m

USER octave
WORKDIR /home/octave/src

ENTRYPOINT ["octave"]
