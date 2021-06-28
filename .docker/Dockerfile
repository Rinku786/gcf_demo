# Step 1


FROM node:14.10.1-alpine as build-set


#RUN mkdir app


WORKDIR /app


#COPY package.json /app
COPY . /app


#RUN npm install


#COPY . /app


#RUN npm run build



# Stage 2
FROM nginx:1.18.0-alpine

WORKDIR /etc/nginx
ADD nginx.conf /etc/nginx/nginx.conf

COPY --from=build-set /app/build /usr/share/nginx/html
EXPOSE 8080
CMD ["nginx", "-g", "daemon off;"]
