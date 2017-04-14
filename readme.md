# Docker Reverse Proxy
---

ใช้สำหรับทำ reverse proxy จาก port 80 เข้าไปหา port ของ docker แต่ละตัว

ดึง docker image มาจาก `smebberson/alpine-nginx` ([https://hub.docker.com/r/smebberson/alpine-nginx/](https://hub.docker.com/r/smebberson/alpine-nginx/))

# Commands
---

##### Access alpine linux
`docker exec -it reverse-proxy sh`

##### Restart nginx (reload configure)
`s6-svc -h /var/run/s6/services/nginx/`

# How to map new subdomain
---

1. สร้าง subdomain ขึ้นมาก่อน
2. ชี้ subdomain มาที่เครื่องที่รัน `docker-reverse-proxy` อยู่
2. Copy & Paste ไฟล์ nginx config ใน folder `conf.d`
3. แก้ค่าต่างๆ ให้ชี้ไปหา subdomain, docker ตัวใหม่
4. Access เข้าไปใน `docker-reverse-proxy`
5. Restart nginx
