FROM node:8.15.1-alpine
RUN adduser -D appuser
WORKDIR /
ADD ./ /
RUN chown -R appuser /
RUN npm config set unsafe-perm true
RUN apk update && \
    npm install package.json && \
    npm install -g gulp@3.9.1

USER appuser
CMD gulp && node src/app.js
