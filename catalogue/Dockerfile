FROM node:20.19.5-alpine3.21 AS build
WORKDIR /opt/server
COPY package.json .
#any files with .j files need to be copied
COPY *.js . 
#dependeny adding
RUN npm install



#this is final image

FROM node:20.19.5-alpine3.21 
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop && \ chown -R roboshop:roboshop /opt/server

WORKDIR /opt/server
COPY --from=build /opt/server /opt/server
EXPOSE 8080
LABEL com.project="roboshop" \
      component="catalogue" \
      created_by="ramana snaku"

ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"
USER roboshop
CMD ["server.js"]
ENTRYPOINT ["node" ]




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

