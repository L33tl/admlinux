# Отчет по администрированию линукс

## Задание 1

http://ap2-409161.lab-itmo.ru:8080/

![vosemvosem](images/vosemvosem.png "Screen:")

/etc/nginx/sites-available/lab:

```bash
server {
    listen 80;
    server_name ap2-409161.lab-itmo.ru;
    return 301 https://$host$request_uri;
}

server {
    listen 443 ssl;
    server_name ap2-409161.lab-itmo.ru;

    ssl_certificate /etc/nginx/ssl/cert.pem;
    ssl_certificate_key /etc/nginx/ssl/privkey.pem;

    root /var/www/html;
    index lab.html;

    ssi on;

    location / {
        try_files $uri $uri/ =404;
    }
}

server {
    listen 8080;
    server_name ap2-409161.lab-itmo.ru;

    root /var/www/html;
    index lab.html;

    ssi on;

    location / {
        try_files $uri $uri/ =404;
    }
}
```

---

https://ap2-409161.lab-itmo.ru/

![ssl](images/ssl.png "SSL:")

Сертификаты:

![certs](images/certs.png "Certs:")


## Задание 2
