---
title: О API
description: Главная страница
layout: ../../layouts/MainLayout.astro
---

## Общие

* **GET** `subdomain.domain.com/api/v1/object`
* ```json
    {
        "status": 200,
        "body": "200",
        "head": {
            "Content-Type": "application/json",
            "CORS-Policy": "same-origin"
        }
    }
    ```

* **GET** `subdomain.domain.com/api/v1/object/{id}`
* ```json
    {
        "status": 200,
        "body": {
            /* ... */
        },
        "head": {
            "Content-Type": "application/json",
            "CORS-Policy": "same-origin"
        }
    }
    ```

## User

* **GET** `subdomain.domain.com/api/v1/user/{id}`
* ```json
    {
        "status": 200,
        "body": {
            "name":  "Name Of Person",
            "photo": "https://subdomain.domain.com/api/v1/files/nameofperson/photo.jpg",
            "group": "AA-00-0",
            "course": 4,
            "fac": "FAI"
        },
        "head": {
            "Content-Type": "application/json",
            "CORS-Policy": "same-origin",
            "X-Content-Type-Options": "nosniff",
            "Content-Security-Policy": "default-src 'self' *.domain.com"
        }
    }
    ```

* **GET** `subdomain.domain.com/api/v1/user/login`
* *Принимает*
     ```json
            {
                "login": "login",
                "password": "password"
            }
    ```
* *Отправляет* [более о токенах](/ru/security/tokens)
    ```json
    {
        "status": 200,
        "body": "token...",
        "head": {
            "Content-Type": "application/json",
            "CORS-Policy": "same-origin",
            "X-Content-Type-Options": "nosniff",
            "Content-Security-Policy": "default-src 'self' *.domain.com"
        }
    }
    ```
* **PATCH** `subdomain.domain.com/api/v1/user/{id}`
* ```json
    {
        "name": "name-of-object",
        "content": "content"
    }
    ```

* **PATCH** `subdomain.domain.com/api/v1/user/{id}/meta`
* ```json
    {
        "name": "name-of-object",
        "content": "content"
    }
    ```
