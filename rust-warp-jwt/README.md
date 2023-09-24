# `rust-warp-jwt`

Example of JWT authentication and authorization in Rust using Warp

[![shield-youtube-warp-jwt][shield-youtube-warp-jwt]][link-youtube-warp-jwt]
[![shield-github-warp-jwt][shield-github-warp-jwt]][link-github-warp-jwt]

---

## What's included?

![shield-rust][shield-rust]

---

## 🚀Quickstart

### Build

run the following command

```sh
cargo run
```

---

## Test

Example of JWT authentication and authorization in Rust using Warp

### User Endpoint

```sh
#
# 1. Login to retrieve valid JWT
#
curl http://localhost:8000/login \
  -H 'Content-Type: application/json' \
  -d '{"email": "user@userland.com", "pw": "1234"}'

# {
#   "token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJzdWIiOiIxIiwicm9sZSI6IlVzZXIiLCJleHAiOjE2MDMxMzQwODl9.dWnt5vfcGdwypEQUr3bLMrZYfdyxj3v6-io6VREWHXebMUCKBddf9xGcz4vHrCXruzx42zrS3Kygiqw3xV8W-A"
# }

#
# 2a. Retrieve User info
#
curl http://localhost:8000/user \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJzdWIiOiIxIiwicm9sZSI6IlVzZXIiLCJleHAiOjE2MDMxMzQwODl9.dWnt5vfcGdwypEQUr3bLMrZYfdyxj3v6-io6VREWHXebMUCKBddf9xGcz4vHrCXruzx42zrS3Kygiqw3xV8W-A'

# Hello User 1

#
# 2b. 401 Not admin
#
curl http://localhost:8000/admin \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJzdWIiOiIxIiwicm9sZSI6IlVzZXIiLCJleHAiOjE2MDMxMzQwODl9.dWnt5vfcGdwypEQUr3bLMrZYfdyxj3v6-io6VREWHXebMUCKBddf9xGcz4vHrCXruzx42zrS3Kygiqw3xV8W-A'

# {"message":"no permission","status":"401 Unauthorized"}
```


### Admin Endpoint

```sh
#
# 1. Login (as admin) to retrieve valid JWT
#

curl http://localhost:8000/login \
  -H 'Content-Type: application/json' \
  -d '{"email": "admin@adminaty.com", "pw": "4321"}'

# {
#   "token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJzdWIiOiIyIiwicm9sZSI6IkFkbWluIiwiZXhwIjoxNjAzMTM0MjA1fQ.uYglVKRvb3h0bDC0Uz8FwGTu4v__Rl3toVI9fMI4_IT8keKde_SZRFQ4ii_PKzI4wjmDsZlnpULe6Tg0vWfEnw"
# }

#
# 2a. Retrieve User info (admin)
#
curl http://localhost:8000/admin \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJzdWIiOiIyIiwicm9sZSI6IkFkbWluIiwiZXhwIjoxNjAzMTM0MjA1fQ.uYglVKRvb3h0bDC0Uz8FwGTu4v__Rl3toVI9fMI4_IT8keKde_SZRFQ4ii_PKzI4wjmDsZlnpULe6Tg0vWfEnw' 

# Hello Admin 2

#
# 2a. Retrieve User info
#
curl http://localhost:8000/user \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJzdWIiOiIyIiwicm9sZSI6IkFkbWluIiwiZXhwIjoxNjAzMTM0MjA1fQ.uYglVKRvb3h0bDC0Uz8FwGTu4v__Rl3toVI9fMI4_IT8keKde_SZRFQ4ii_PKzI4wjmDsZlnpULe6Tg0vWfEnw' 

# Hello User 2
```
[shield-rust]: https://img.shields.io/badge/Rust-1.7.21-000000?logo=rust&logoColor=000000&style=flat-square

[shield-youtube-warp-jwt]: https://img.shields.io/badge/YouTube-(@AkhilSharmaTech)-FF0000?logo=youtube&logoColor=FF0000&style=flat-square
[shield-github-warp-jwt]: https://img.shields.io/badge/GitHub-(AkhilSharma90)-000000?logo=github&logoColor=000000&style=flat-square
[link-youtube-warp-jwt]: https://www.youtube.com/watch?v=HqAyAV-0gKc
[link-github-warp-jwt]: https://github.com/AkhilSharma90/rust-warp-jwt