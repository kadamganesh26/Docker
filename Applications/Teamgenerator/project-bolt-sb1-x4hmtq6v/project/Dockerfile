FROM node AS Build
WORKDIR /app 
COPY . .
RUN npm install 
RUN npm run build
FROM nginx
COPY --from=Build /app/dist/ /usr/share/nginx/html
EXPOSE 80 
CMD [ "nginx", "-g", "daemon off;" ]


