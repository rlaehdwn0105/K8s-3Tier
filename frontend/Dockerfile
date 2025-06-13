# 1단계: Node.js를 사용하여 애플리케이션 빌드
FROM node:21-alpine3.17 AS build
WORKDIR /app
COPY . .
ENV NODE_OPTIONS=--openssl-legacy-provider
RUN npm install
RUN npm update
RUN npm run build

# 2단계: 애플리케이션 실행
FROM node:21-alpine3.17
WORKDIR /app
COPY --from=build /app /app
ENV NODE_OPTIONS=--openssl-legacy-provider
CMD ["npm", "start"]

