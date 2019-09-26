FROM ruby

RUN apt update && apt upgrade -y
RUN apt install -y nodejs
RUN gem install rails

ONBUILD COPY app /opt/app

ONBUILD WORKDIR /opt/app

ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed

# docker build -t ft-rails:on-build .

# To try (with a rails app folder):
# docker build -t container .
# docker run -it --rm -p 3000:3000 container
