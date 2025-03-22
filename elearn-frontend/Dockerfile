FROM node AS build
WORKDIR  /app 
COPY package*.json ./
RUN npm install   # It will create node module
COPY . . 
RUN npm run build # It will install all dependenacies
FROM nginx
COPY --from=build /app/build /usr/share/nginx/html 
ENTRYPOINT [ "nginx", "-g", "daemon off;" ]
EXPOSE 80
