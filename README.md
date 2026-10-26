# Mi Negocio USA → SV

Proyecto inicial para publicar en Netlify, guardar el código en GitHub y preparar la base de datos en Supabase.

## Archivos
- `index.html`: página actual del inventario y reporte de Excel.
- `config.js.example`: plantilla para la URL y clave pública de Supabase.
- `supabase/schema.sql`: crea la tabla de productos y activa Row Level Security (RLS).

## Importante: estado inicial
La página incluida todavía guarda el inventario en el navegador (`localStorage`). El esquema de Supabase está preparado, pero la página aún debe conectarse a Supabase para iniciar sesión y sincronizar productos. No consideres los datos respaldados en la nube hasta completar y probar esa integración.

## Pasos de publicación

### 1. GitHub
1. Crea una cuenta en https://github.com
2. Crea un repositorio nuevo llamado `mi-negocio-usa-sv`.
3. Sube `index.html`, `config.js.example`, `README.md` y la carpeta `supabase`.
4. No subas contraseñas, tokens ni claves secretas.

### 2. Supabase
1. Crea una cuenta en https://supabase.com
2. Crea un proyecto y guarda la contraseña de la base de datos en un gestor seguro.
3. Abre SQL Editor, pega el contenido de `supabase/schema.sql` y ejecuta.
4. Copia la Project URL y la clave pública (publishable/anon). Nunca uses la clave `service_role` en el navegador.
5. La integración de autenticación y sincronización de la página es el siguiente paso de desarrollo.

### 3. Netlify
1. Crea una cuenta en https://www.netlify.com
2. Conecta GitHub y elige el repositorio `mi-negocio-usa-sv`.
3. Para esta página estática, deja el comando de build vacío y el directorio de publicación como `.` (raíz).
4. Pulsa Deploy site. Netlify te dará una dirección web.

## Seguridad
- El SQL activa RLS y restringe las filas por usuario autenticado.
- No compartas la contraseña de la base de datos ni una clave `service_role`.
- Antes de guardar información real de clientes, prueba el inicio de sesión y los permisos.
