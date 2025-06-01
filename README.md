# Script-para-SSH-administrar-Wordpress-lightsail
Script para ejecutar por SSH dentro de una instancia Lightsail y para poder cambiar nombres de plugins y temas, activar y desactivar
WordPress Emergency Recovery Script
Un script bash completo para recuperación y mantenimiento de emergencia de sitios WordPress en servidores VPS (optimizado para AWS Lightsail con Bitnami)

🚨 ¿Para qué sirve?
Script de emergencia diseñado para administradores y desarrolladores que necesitan recuperar rápidamente un sitio WordPress cuando:

Un plugin o tema causa un error crítico (pantalla blanca de la muerte)
El sitio no responde y no puedes acceder al panel de administración
Necesitas hacer mantenimiento directo por SSH sin usar cPanel
Requieres diagnosticar problemas sin acceso web

🎯 Características principales
Gestión de Plugins

Ver listado completo de plugins instalados
Desactivar/reactivar plugins individualmente (por número o nombre)
Desactivar TODOS los plugins de emergencia con un clic
Sistema de respaldo automático antes de cambios masivos
Método seguro: renombra carpetas agregando 's' al final

Gestión de Temas

Listar todos los temas instalados
Desactivar temas problemáticos selectivamente
Forzar activación de temas por defecto (Twenty*)
Selección por número o nombre de tema
No requiere permisos especiales de WP-CLI

Diagnóstico y Reparación

Ver los últimos 20 errores de WordPress
Activar/desactivar modo DEBUG con un clic
Reparar permisos de archivos automáticamente
Limpiar todos los tipos de caché (transients, object cache, W3TC, WP Super Cache)
Verificar integridad de archivos core de WordPress
Opción de reinstalar WordPress core preservando contenido

Sistema de Respaldos

Backup individual de carpeta plugins
Backup individual de carpeta themes
Backup completo de wp-content
Confirmación antes de crear backups con tamaño estimado
Nombrado automático con timestamp
Almacenamiento organizado en ~/wp-backups

💻 Requisitos

Servidor Linux con WordPress instalado
Acceso SSH al servidor
WordPress instalado en /opt/bitnami/wordpress (ajustable)
Usuario con permisos sudo
Bash shell

🔧 Instalación

# Conectar por SSH
ssh -i tu-llave.pem usuario@tu-servidor

# Descargar el script
wget https://raw.githubusercontent.com/tu-usuario/tu-repo/main/wordpress-emergency.sh

# Dar permisos de ejecución
chmod +x wordpress-emergency.sh

# Ejecutar
./wordpress-emergency.sh
