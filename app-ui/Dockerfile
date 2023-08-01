# Stage 1
FROM node:latest as nodebuild
WORKDIR /app
COPY . .
RUN npm install
RUN npm run build --prod

#Stage 2
FROM nginx:alpine
COPY --from=nodebuild /app/dist/app-ui /usr/share/nginx/html

EXPOSE 80
