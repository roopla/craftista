FROM node:latest as builder
WORKDIR /app
COPY package.json ./
RUN npm install
COPY . .

FROM node:alpine
WORKDIR /app
COPY --from=builder /app .
RUN adduser -D nonrootuser
USER nonrootuser
EXPOSE 3000
CMD ["node", "app.js"]

