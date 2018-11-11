FROM node:10.13-alpine

WORKDIR /usr/local/docker/app

COPY ./package.json /usr/local/docker/app/package.json
COPY ./package-lock.json /usr/local/docker/app/package-lock.json

RUN npm install

# for nuxt
COPY ./assets /usr/local/docker/app/assets
COPY ./components /usr/local/docker/app/components
COPY ./layouts /usr/local/docker/app/layouts
COPY ./middleware /usr/local/docker/app/middleware
COPY ./pages /usr/local/docker/app/pages
COPY ./plugins /usr/local/docker/app/plugins
COPY ./static /usr/local/docker/app/static
COPY ./store /usr/local/docker/app/store
COPY ./nuxt.config.js /usr/local/docker/app/nuxt.config.js

# for build
COPY ./.eslintrc.js /usr/local/docker/app/.eslintrc.js
COPY ./.prettierrc /usr/local/docker/app/.prettierrc

# build nuxt
RUN npm run build

# start nuxt server
CMD npm run start