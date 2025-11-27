# 🚀 Instalación de PrestaShop con Docker

Este proyecto permite levantar rápidamente un entorno de **PrestaShop 8.0** utilizando **Docker** y **MySQL 5.7**.

---

## 📦 Requisitos Previos

Antes de iniciar, asegúrate de tener instalado:

- Docker
- Docker Compose

---

## 🔧 Instalación

1. Clona o copia el archivo `docker-compose.yml`.
2. Abre una terminal en la carpeta donde está el archivo.
3. Ejecuta el siguiente comando:

```bash
docker compose up -d
```

4. Espera a que los contenedores se inicien.
5. Accede a PrestaShop desde el navegador:

👉 **http://localhost:8090**

---

## 🔑 Credenciales por defecto

Durante la instalación automática se crean las siguientes credenciales:

| Parámetro | Valor |
|-----------|-------|
| URL Front-Office | http://localhost:8090 |
| URL Back-Office | http://localhost:8090/admin (deberás renombrarla luego por seguridad) |
| Usuario Admin | admin@prestashop.com |
| Contraseña Admin | prestashop |
| Base de datos | prestashop |
| Usuario DB | prestashop |
| Contraseña DB | prestashop |
| Servidor DB | prestashop_db |
| Puerto DB | 3306 |

---

## 🔒 Importante (Seguridad)

Después de la instalación:

1. Entra al contenedor o al directorio `/var/www/html`.
2. Renombra el directorio `/admin`, por ejemplo:

```bash
mv admin admin677sjgnl5tqk0nt15cs
```

3. Accede al panel de administración mediante la nueva URL:

👉 **http://localhost:8090/admin677sjgnl5tqk0nt15cs**

---

## 🛑 Detener los contenedores

```bash
docker compose down
```

---

## ♻️ Reiniciar con instalación limpia

Si deseas reinstalar desde cero:

```bash
docker compose down -v
docker compose up -d
```

---

## ✨ Notas adicionales

- La opción `PS_DEV_MODE=1` permite ver errores durante el desarrollo.
- Si necesitas cambiar el dominio, modifica `PS_DOMAIN` en el archivo `docker-compose.yml`.
