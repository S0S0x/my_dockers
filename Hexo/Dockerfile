FROM alpine
WORKDIR /app

RUN apk add git \
            nodejs \
            npm

# install Hexo
RUN npm install -g hexo-cli

# init hexo dir

RUN npx hexo init hexo
WORKDIR /app/hexo/


# install dependencies
RUN npm install hexo-admin
RUN npm install hexo-generator-search --save

# install cactus theme
RUN git clone https://github.com/probberechts/hexo-theme-cactus.git themes/cactus

# copy config
COPY _config.yml _config.yml
# start hexo server
CMD [ "npm", "run", "server" ]

