FROM nginx:alpine
LABEL maintainer="student.student@student.com"
RUN apk add --no-cache nodejs npm && npm install -g htmlhint
COPY . /usr/share/nginx/html
RUN date > /usr/share/nginx/html/build.txt
RUN htmlhint /usr/share/nginx/html/index.html
EXPOSE 80
LABEL autor="Adam Debniak" data="2026-11-06"