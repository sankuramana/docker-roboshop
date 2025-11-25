FROM node:20
WORKDIR /opt/server
COPY package.json .
#any files with .j files need to be copied
COPY *.js . 
#dependeny adding
RUN npm install
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"

CMD ["node", "server.js"]
