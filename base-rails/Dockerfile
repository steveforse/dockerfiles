# Image: ruby-rails
FROM base-ruby:2.6.3

######################
# RAILS DEPENDENCIES #
######################
user root

# Install nodejs
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash -

# System dependencies
RUN apt-get install -y nodejs libsqlite3-dev postgresql postgresql-contribb libpq-dev

#################
# INSTALL RAILS #
#################
USER ruby-user
SHELL ["/bin/bash", "-lc"]

# Install rails
RUN gem install rails -v 6.0.0rc2

