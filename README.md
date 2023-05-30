## Laravel docker project template

default host: localhost
default tcp port: 8800 \
`http://localhost:8800` 

---
### For start
Run: \
\$ `composer create-project laravel/laravel app` \
\$ `cp .env.example .env` \

Set up `.env` and `app/.env` according each other. \
Run docker compose: \
\$ `docker compose up -d --build`
