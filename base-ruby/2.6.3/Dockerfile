# Image: ruby-base

FROM debian:9.8

# Install Ruby dependencies
USER root
RUN apt-get update
RUN apt-get install -y autoconf \
                       bison \
                       build-essential \
                       libssl-dev \
                       libyaml-dev \
                       libreadline6-dev \
                       zlib1g-dev \
                       libncurses5-dev \
                       libffi-dev \
                       libgdbm3 \
                       libgdbm-dev



# Install git
RUN apt-get install -y git-core

# Install useful apps
RUN apt-get install -y vim curl

# Clean files
RUN apt-get clean

# Install rbenv under ruby-user
RUN useradd -m ruby-user -p password
USER ruby-user

SHELL ["/bin/bash", "-lc"]

# Install and configure rbenv
RUN git clone https://github.com/rbenv/rbenv.git ~/.rbenv

RUN echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
RUN echo 'eval "$(rbenv init -)"' >> ~/.bashrc

RUN echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.profile
RUN echo 'eval "$(rbenv init -)"' >> ~/.profile

# Install rbenv-install plugin
RUN git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
RUN echo "gem: --no-document" > ~/.gemrc

RUN rbenv install 2.6.3
run rbenv global 2.6.3

RUN gem install bundler

