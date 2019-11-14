FROM java:8-alpine

ARG PINPOINT_VERSION=${PINPOINT_VERSION:-1.8.4}

COPY pinpoint-agent-${PINPOINT_VERSION} /pinpoint-agent

RUN echo "http://mirrors.aliyun.com/alpine/v3.4/main/" > /etc/apk/repositories \
	&& apk update \
	&& apk upgrade \
	&& apk add --no-cache bash curl tzdata \
	&& cp -r -f /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
	&& rm -rf /var/cache/apk/*