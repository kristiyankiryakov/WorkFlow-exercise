#Multi step Build

#Build Phase
FROM node:16-alpine AS builder

WORKDIR '/app'
COPY frontend/package.json .

RUN npm install
COPY . .

RUN npm run build

# Run Phase

FROM nginx
EXPOSE 80
COPY --from=builder /app/build /usr/share/nginx/html

#nginx start with it's default command
