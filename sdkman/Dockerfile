FROM adoptopenjdk/openjdk8:alpine

#
# Work with user
#

ARG USER="default"
ENV HOME="/home/$USER"

# install tools
RUN apk add --no-cache sudo bash curl git zip

# add new user
RUN adduser -D $USER \
        && echo "$USER ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/$USER \
        && chmod 0440 /etc/sudoers.d/$USER

# switch user
USER $USER
WORKDIR $HOME

#
# Work with SDKMAN!
#

ARG SDKMAN_DIR="$HOME/.sdkman"
ENV SDKMAN_DIR=$SDKMAN_DIR

# download SDKMAN!
RUN curl -s "https://get.sdkman.io" | bash

# init SDKMAN!
RUN bash -c "source $SDKMAN_DIR/bin/sdkman-init.sh"