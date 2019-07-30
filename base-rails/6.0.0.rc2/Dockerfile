# Image: base-rails
FROM steveforse/base-ruby:2.6.3

######################
# RAILS DEPENDENCIES #
######################
user root

# Install nodejs
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list

# System dependencies
RUN apt-get update && \
    apt-get install -y \
                    yarn \
                    libsqlite3-dev \
                    postgresql \
                    postgresql-contrib \
                    libpq-dev \
                    nginx \
                    && \
    apt-get clean

# Configure sudo for ruby user
RUN adduser ruby-user sudo
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

#################
# INSTALL RAILS #
#################
USER ruby-user
SHELL ["/bin/bash", "-lc"]

# Install rails
RUN gem install rails -v 6.0.0rc2

