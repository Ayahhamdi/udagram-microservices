# Build
FROM beevelop/ionic AS ionic

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies by copying
# package.json and package-lock.json
COPY frontend/package*.json ./
COPY frontend/ionic.config.json ./

# Install dependencies
RUN npm ci

# Copy app source
COPY . .
RUN ionic serve

## Run 
FROM nginx:alpine
#COPY www /usr/share/nginx/html
COPY --from=ionic  /usr/src/app/www /usr/share/nginx/html
