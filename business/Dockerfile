FROM node:20
WORKDIR /app
COPY package.json ./
RUN npm install
COPY . .


# Installe wait-for-it pour attendre PostgreSQL
COPY wait-for-it.sh /wait-for-it.sh
RUN chmod +x /wait-for-it.sh

CMD ["./wait-for-it.sh", "db:5432", "--timeout=30", "--", "npm", "start"]
