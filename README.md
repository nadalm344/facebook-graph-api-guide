# Guía de Inicio: API de Facebook (Graph API)

Esta guía explica el proceso real para configurar el acceso a la Graph API de Facebook y realizar la primera consulta de usuario.

## 📋 Prerrequisitos
Antes de comenzar, asegúrate de tener:
* Una cuenta de Facebook personal activa.
* Una cuenta de [Facebook for Developers](https://developers.facebook.com/).

> **Nota:** Facebook for Developers es el puente que permite que tu web o app hable con el mundo de Facebook para aprovechar sus funciones y sus miles de millones de usuarios.

---

## 🚀 Paso 1: Crear una App en el Panel de Desarrolladores
1. Entra al **App Dashboard** de Facebook.
2. Haz clic en **Create App**.
3. Selecciona el tipo de App (ej. "Other" o "Business").
4. Dale un nombre a tu proyecto y vincula un correo de contacto.

> **Nota:** **App Dashboard** es el **Panel de control** y **Create App** es **Crear aplicación**.

## 🔐 Paso 2: Obtener el Access Token (Token de Acceso)
Para interactuar con la API, necesitas una "llave" temporal:
1. Ve a la herramienta **Graph API Explorer**.
2. En el menú desplegable de la derecha, selecciona la **App** que creaste.
3. Haz clic en **Get Token** -> **Get User Access Token**.
4. Acepta los permisos en la ventana emergente de Facebook.

> **Nota:** **Graph API Explorer** es el **Explorador de API de gráficos**.

> [!IMPORTANT]
> Los tokens de usuario suelen ser de "corta duración" (expiran en 1 o 2 horas). Para producción, se requiere un Token de larga duración.

## 📡 Paso 3: Tu primera consulta (Endpoint GET)
Copia la siguiente URL en el explorador de la API para obtener tu nombre e ID:

`GET /v21.0/me?fields=id,name`

### Respuesta esperada (JSON):

```json
{
  "name": "Tu Nombre Completo",
  "id": "123456789012345"
}
```
 ## ⚠️ Códigos de Error Comunes 

| **Código** | **Mensaje** | **Solución** |
| --- | --- | --- |
| 190 | Invalid OAuth 2.0 Access Token | El token expiró o es inválido. Genera uno nuevo. |
|200 | Permissions error | No tienes el permiso necesario (ej. `publish_actions`). |



