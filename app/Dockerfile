# FROM node:latest AS download

FROM node:latest AS install
WORKDIR /app/
# COPY --from=download . .
COPY package-lock.json package.json ./
RUN npm install

FROM node:latest AS run
WORKDIR /app/
COPY --from=install . . 
EXPOSE 8080
CMD ls && npm run start:dev