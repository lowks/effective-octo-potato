FROM node:10.14 as build-deps
WORKDIR /usr/src/app
COPY src/package.json src/yarn.lock src/src/index.js ./
RUN yarn
COPY . ./
ENTRYPOINT ["bash"]
# RUN yarn build

FROM node:12

WORKDIR /usr/src/app
COPY --from=build-deps /usr/src/app .
EXPOSE 3000
CMD [ "yarn", "start" ]