ARG BUILD_FROM
FROM $BUILD_FROM

# Add env
ENV LANG C.UTF-8

ENV LGTV2MQTT_VERSION=1.0.0
ENV ARCHIVE=lgtv2mqtt-$LGTV2MQTT_VERSION

# Get latest version of the lgtv2mqtt app
RUN apk add --update --no-cache curl jq nodejs npm && \
  npm install -g lgtv2mqtt

COPY run.sh "/$ARCHIVE/run.sh"
WORKDIR "/$ARCHIVE"

RUN ["chmod", "a+x", "./run.sh"]
CMD [ "./run.sh" ]
# Start app
#CMD node index.js --verbosity=$lgtv2mqtt_v --name=$lgtv2mqtt_n --url=$lgtv2mqtt_u --tv=$lgtv2mqtt_t
