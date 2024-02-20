FROM node:16-alpine

WORKDIR /src

COPY . .

RUN apk update && apk add --no-cache tzdata ca-certificates curl && \
    cp /usr/share/zoneinfo/Asia/Jakarta /etc/localtime && \
    echo "Asia/Jakarta" > /etc/timezone

ENV TZ=Asia/Jakarta

RUN npm install 

RUN npm run build

EXPOSE 3000

CMD ["npm", "run", "start"]