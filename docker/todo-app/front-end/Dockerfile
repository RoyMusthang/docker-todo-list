FROM node:14-alpine as build
#Alias = :as
WORKDIR /app
COPY ["package.json", "package-lock.json", "./"]
RUN npm install
COPY ["./public", "./public"]
COPY ["./src", "./src"]
ENV REACT_APP_API_HOST=todoback
RUN npm run build


FROM nginx:1.12-alpine
COPY --from=build /app/build /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 3000
CMD ["nginx", "-g", "daemon off;"]
