FROM node
RUN apt-get update && apt-get install -y iputils-ping && apt-get dist-upgrade -y && apt-get clean && apt-get autoclean
EXPOSE 3000
ENV APP_PATH /usr/share/app
RUN mkdir -p $APP_PATH && chown node:node $APP_PATH
WORKDIR $APP_PATH
USER node
COPY . $APP_PATH/
RUN npm install
CMD ["npm","start"]