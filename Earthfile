FROM node:14.15.0
WORKDIR /usr/build

src:
    COPY package.json package-lock.json ./
    RUN npm install --production
    COPY . .

standalone-experiment-setup:
    FROM +src
    RUN mv src/build/Dockerfile.standalone Dockerfile

standalone-experiment:
    FROM DOCKERFILE +standalone-experiment-setup/
    SAVE IMAGE recordreplay-standalone