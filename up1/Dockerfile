FROM node:alpine

RUN apk --update add su-exec bash wget git unzip ca-certificates && \
	cd / && git clone https://github.com/Upload/Up1 && \
	cd /Up1/server && \
	apk del wget unzip git && rm -rf /var/cache/apk/* && \
	npm install
	
ADD start.sh /start.sh
RUN chmod +x /start.sh

EXPOSE 5000

WORKDIR /Up1/server

ENV NODE_ENV production

ENTRYPOINT ["/start.sh"]

CMD [""]