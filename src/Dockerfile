FROM sindriainc/openjdk:1.3.0-16

ARG TAG_VERSION
ARG HOST_USER_UID
ARG TIMEZONE

LABEL \
	name="minecraft" \
	image="sindriainc/minecraft" \
	tag="${TAG_VERSION}" \
	vendor="sindria"

ENV TZ=${TIMEZONE}
ENV SINDRIA_USER="sindria"
ENV SINDRIA_USER_HOME="/home/sindria"

# Install application, setting timezone and reset permession
COPY resources/minecraft/server.jar /var/www/app
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone && \
    chmod -R 771 /var/www/app && \
    chown -R ${SINDRIA_USER}:${SINDRIA_USER} /var/www/app