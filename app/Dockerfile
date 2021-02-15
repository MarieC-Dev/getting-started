FROM node:12-alpine
WORKDIR /app
COPY . .
COPY source_code Dockerfile
RUN yarn install --production
RUN brew install node
RUN npm init
RUN apt-get update && apt-get install -y locales && rm -rf /var/lib/apt/lists/* \
    && localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8
ENV LANG en_US.utf8
ENV PORT 3000
CMD ["node", "src/index.js", "npm", "start"]
