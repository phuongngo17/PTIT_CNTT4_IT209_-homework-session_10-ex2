Exercise 2: Single-stage Dockerfile



\## 1. Mục tiêu

Đóng gói ứng dụng REST API Node.js/Express bằng Single-stage Dockerfile.



\## 2. Công nghệ

\- Node.js 18 Alpine

\- Express.js

\- Docker Desktop



\## 3. Cấu trúc thư mục

```text

ex2/

├── Dockerfile

├── package.json

├── server.js

├── .dockerignore

└── README.md

```



\## 4. Build Docker Image

```bash

docker build -t hw-backend:v1 .

```



\## 5. Chạy Container

```bash

docker run -d --name app-single-stage -p 8080:3000 hw-backend:v1

```



\## 6. Kiểm tra

```bash

docker ps

docker logs app-single-stage

curl -i http://localhost:8080/

```



\## 7. Kết quả mong đợi

\- Docker Image: `hw-backend:v1`

\- Container: `app-single-stage`

\- Trạng thái: `Up`

\- Port Mapping: `8080:3000`

\- HTTP Status: `200 OK`



Response JSON:



```json

{

&#x20; "status": "success",

&#x20; "message": "Hello from Docker Single-stage!"

}

```



\## 8. Giải thích Dockerfile

\- FROM: Chọn Node.js 18 Alpine làm Base Image.

\- WORKDIR: Thiết lập thư mục `/app`.

\- COPY: Sao chép mã nguồn vào Image.

\- RUN: Cài đặt dependencies.

\- ENV: Khai báo biến môi trường PORT=3000.

\- EXPOSE: Khai báo cổng 3000.

\- CMD: Chạy ứng dụng Node.js.



\## 9. Kết luận

Ứng dụng REST API được đóng gói bằng Single-stage Dockerfile, giúp chuẩn hóa môi trường triển khai và đơn giản hóa quá trình vận hành.

