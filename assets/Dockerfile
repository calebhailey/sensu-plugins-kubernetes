FROM calebhailey/sensu-ruby-runtime:2.4.4-debian

ARG PLUGIN="sensu-plugins-kubernetes"

WORKDIR /build/
COPY Gemfile .
RUN \
  gem install --no-ri --no-doc bundler && \
  bundle install --path=lib/ --binstubs=bin/ --standalone && \
  tar -czf /${PLUGIN}.tar.gz -C /build .
