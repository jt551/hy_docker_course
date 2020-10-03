# Build phase
FROM node:12-alpine as build

WORKDIR /app

ENV PATH /app/node_modules/.bin:$PATH

COPY package.json ./
COPY package-lock.json ./

RUN npm ci
RUN npm install react-scripts

COPY . ./

RUN npm run build

# Production
FROM nginx:stable-alpine



COPY --from=build /app/build /usr/share/nginx/html
# Copy nginx conf files
COPY nginx/nginx.conf /etc/nginx/nginx.conf
COPY nginx/default.conf /etc/nginx/conf.d/default.conf

#permissions for nginx user
RUN chown -R nginx:nginx /usr/share/nginx/html && chmod -R 755 /usr/share/nginx/html && \
        chown -R nginx:nginx /var/cache/nginx && \
        chown -R nginx:nginx /var/log/nginx && \
        chown -R nginx:nginx /etc/nginx/conf.d && \
        chown -R nginx:nginx /var/log
RUN touch /var/run/nginx.pid && \
        chown -R nginx:nginx /var/run/nginx.pid

#set non root user nginx
USER nginx
#use high port since non root cant access port 80
EXPOSE 8080

CMD [ "nginx", "-g", "daemon off;"]
