FROM mjgargani/puppeteer:trybe1.0
WORKDIR /app
COPY ["package.json", "package-lock.json", "./"]
RUN npm install
COPY . .
ENTRYPOINT ["npm", "test"]
