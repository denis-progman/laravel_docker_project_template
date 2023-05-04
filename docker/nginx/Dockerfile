FROM alpine:3.14
RUN apk update \ 
&& apk add openrc \
&& apk add nginx \
&& apk add curl

EXPOSE 80

ENTRYPOINT ["nginx", "-g", "daemon off;"]