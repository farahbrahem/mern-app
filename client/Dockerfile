FROM node:lts-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

# URL de l'API vue par le NAVIGATEUR (injectée au build)
ARG REACT_APP_API_URL=http://localhost:9000
ENV REACT_APP_API_URL=$REACT_APP_API_URL

RUN npm run build
RUN npm install -g serve
EXPOSE 3000
CMD ["serve", "-s", "build", "-l", "3000"]