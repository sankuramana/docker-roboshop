FROM node:20.19.5-alpine3.21 AS build
WORKDIR /opt/server
COPY package.json .
#any files with .j files need to be copied
COPY *.js . 
#dependeny adding
RUN npm install





FROM node:20.19.5-alpine3.21 
WORKDIR /opt/server
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop 
USER roboshop
COPY --from=build /opt/server /opt/server
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"

CMD ["node", "server.js"]



# FROM node:20
# WORKDIR /opt/server
# COPY package.json .
# #any files with .j files need to be copied
# COPY *.js . 
# #dependeny adding
# RUN npm install
# ENV MONGO="true" \
#     MONGO_URL="mongodb://mongodb:27017/catalogue"

# CMD ["node", "server.js"]

