Passbolt en Docker

Este entorno contiene la configuración necesaria para desplegar **Passbolt Community Edition** utilizando Docker y `docker-compose`. Está pensado para integrarse con un proxy reverso (NGINX) y compartir red con otros servicios como n8n.

---

## 📦 Contenido

- `docker-compose.yml`: define los contenedores de Passbolt y la base de datos MariaDB.
- `.env`: archivo con variables sensibles como usuario de base de datos y URL de acceso.
- `nginx_passbolt.conf`: archivo de configuración para integrar Passbolt con un proxy NGINX.
- Este `README.md`.

---

## ⚙️ Requisitos previos

- Docker y Docker Compose instalados.
- Red Docker externa existente: `n8n_net`
- Certificado SSL generado (Let's Encrypt o propio).
- Configuración DNS apuntando a `vault.matiascanteros.site`.

---

## 📝 Variables necesarias (`.env`)

Ejemplo de `.env`:

```env
APP_FULL_BASE_URL=https://vault.matiascanteros.site
DB_HOST=passbolt-db
DB_PORT=3306
DB_NAME=passbolt
DB_USERNAME=passbolt_user
DB_PASSWORD=passbolt_pass
EMAIL_DEFAULT_FROM=passbolt@matiascanteros.site
EMAIL_TRANSPORT_DEFAULT_HOST=smtp.example.com
EMAIL_TRANSPORT_DEFAULT_PORT=587
EMAIL_TRANSPORT_DEFAULT_USERNAME=user@example.com
EMAIL_TRANSPORT_DEFAULT_PASSWORD=yourpassword
