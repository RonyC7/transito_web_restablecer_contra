# Transito Web – Restablecimiento de contraseña

Pequeña página web estática para el **Sistema de Reportes y Monitoreo de Tránsito de la Municipalidad de La Esperanza**.  
Su único objetivo es permitir que los usuarios restablezcan su contraseña a través del enlace enviado por correo electrónico desde Supabase.

## Objetivo

Cuando un usuario de la app móvil selecciona **“Olvidé mi contraseña”**, Supabase envía un correo con un enlace de recuperación.  
Ese enlace abre esta página web, donde el usuario puede:

1. Ingresar una nueva contraseña.
2. Confirmarla.
3. Enviar el formulario para que Supabase actualice la contraseña del usuario.

## Tecnologías utilizadas

- **HTML + CSS** para la interfaz (diseño similar a la app móvil).
- **JavaScript (ES Modules)**.
- **Supabase JS v2** para:
  - Intercambiar el código del enlace (`code`) por una sesión.
  - Actualizar la contraseña del usuario mediante `auth.updateUser`.
- Imagen institucional alojada en Supabase Storage.

## Flujo de restablecimiento

1. El usuario solicita *“Olvidé mi contraseña”* desde la app móvil.
2. Supabase envía un correo con un enlace de recuperación.
3. El enlace redirige a esta página (deploy en GitHub Pages).
4. El usuario ingresa y confirma su nueva contraseña.
5. La página llama a Supabase y actualiza la contraseña.
6. El usuario vuelve a la app móvil e inicia sesión con la nueva contraseña.

## Estructura del proyecto

```text
.
└── index.html   # Página principal de restablecimiento de contraseña
