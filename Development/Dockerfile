FROM alpine
ARG REPONAME=Sample-Html-Css-Website
ENV REPONAME=$REPONAME

RUN apk update && \
	apk add nginx && \
	apk add git && \
	apk add wget && \
	apk add sed;

RUN	adduser -D -g 'www' www && \
	mkdir /www && \
	chown -R www:www /var/lib/nginx && \
	chown -R www:www /www && \
	mkdir -p /run/nginx && \
	wget vedant-mhatre.github.io/docker-nginx-configfile/nginx.conf && \
	mv nginx.conf /etc/nginx/nginx.conf

RUN	cd /www/ && \
	git clone https://github.com/Vedant-Mhatre/${REPONAME}.git	

RUN sed -i "s/Sample-Html-Css-Website/${REPONAME}/" /etc/nginx/nginx.conf 

CMD ["nginx"]
