FROM node:14-slim
WORKDIR /opt/node-server
COPY . .
ENV POST=8000
RUN npm install
CMD ["node","main.js"]