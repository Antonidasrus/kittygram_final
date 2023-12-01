FROM node:18

WORKDIR /app

COPY package.json package.json
COPY package-lock.json package-lock.json

RUN npm ci --strict-ssl=false

COPY . .
RUN npm run build
RUN npm install --global http-server --strict-ssl=false

CMD ["npx", "-y", "http-server", "-p", "8000", "/app/build"]
