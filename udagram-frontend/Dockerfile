FROM beevelop/ionic:latest AS ionic

WORKDIR /usr/src/app

COPY package*.json ./
RUN npm ci

# Bundle app source
COPY . .
RUN ionic build

# Run
FROM nginx:alpine

COPY --from=ionic /usr/src/app/www /usr/share/nginx/html