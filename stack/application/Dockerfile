FROM  node
WORKDIR /usr
COPY package.json .
RUN npm install
COPY src src
EXPOSE 8080
Entrypoint [ "npm", "start" ]
