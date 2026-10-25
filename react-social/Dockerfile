# Dùng Node 18 mượt mà cho React 17
FROM node:18-alpine

WORKDIR /app

# Copy danh sách thư viện
COPY package*.json ./

# Cài đặt thư viện với flag bỏ qua xung đột phiên bản
RUN npm install --legacy-peer-deps

# Copy toàn bộ code giao diện
COPY . .

EXPOSE 3000
CMD ["npm", "start"]