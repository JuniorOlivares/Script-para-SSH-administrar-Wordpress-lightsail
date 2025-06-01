<h1>📋 WordPress Emergency Recovery Script</h1>
    
<p><strong>Un script bash completo para recuperación y mantenimiento de emergencia de sitios WordPress en servidores VPS (optimizado para AWS Lightsail con Bitnami)</strong></p>
<hr>
<h2>🚨 ¿Para qué sirve?</h2>
    
    <p>Script de emergencia diseñado para administradores y desarrolladores que necesitan recuperar rápidamente un sitio WordPress cuando:</p>
    
    <ul>
        <li>Un plugin o tema causa un error crítico (pantalla blanca de la muerte)</li>
        <li>El sitio no responde y no puedes acceder al panel de administración</li>
        <li>Necesitas hacer mantenimiento directo por SSH sin usar cPanel</li>
        <li>Requieres diagnosticar problemas sin acceso web</li>
    </ul>
    
    <h2>🎯 Características principales</h2>
    
    <h3>Gestión de Plugins</h3>
    <ul>
        <li>Ver listado completo de plugins instalados</li>
        <li>Desactivar/reactivar plugins individualmente (por número o nombre)</li>
        <li>Desactivar TODOS los plugins de emergencia con un clic</li>
        <li>Sistema de respaldo automático antes de cambios masivos</li>
        <li>Método seguro: renombra carpetas agregando 's' al final</li>
    </ul>
    
    <h3>Gestión de Temas</h3>
    <ul>
        <li>Listar todos los temas instalados</li>
        <li>Desactivar temas problemáticos selectivamente</li>
        <li>Forzar activación de temas por defecto (Twenty*)</li>
        <li>Selección por número o nombre de tema</li>
        <li>No requiere permisos especiales de WP-CLI</li>
    </ul>
    
    <h3>Diagnóstico y Reparación</h3>
    <ul>
        <li>Ver los últimos 20 errores de WordPress</li>
        <li>Activar/desactivar modo DEBUG con un clic</li>
        <li>Reparar permisos de archivos automáticamente</li>
        <li>Limpiar todos los tipos de caché (transients, object cache, W3TC, WP Super Cache)</li>
        <li>Verificar integridad de archivos core de WordPress</li>
        <li>Opción de reinstalar WordPress core preservando contenido</li>
    </ul>
    
    <h3>Sistema de Respaldos</h3>
    <ul>
        <li>Backup individual de carpeta plugins</li>
        <li>Backup individual de carpeta themes</li>
        <li>Backup completo de wp-content</li>
        <li>Confirmación antes de crear backups con tamaño estimado</li>
        <li>Nombrado automático con timestamp</li>
        <li>Almacenamiento organizado en ~/wp-backups</li>
    </ul>
    
    <h2>💻 Requisitos</h2>
    
    <ul>
        <li>Servidor Linux con WordPress instalado</li>
        <li>Acceso SSH al servidor</li>
        <li>WordPress instalado en <code>/opt/bitnami/wordpress</code> (ajustable)</li>
        <li>Usuario con permisos sudo</li>
        <li>Bash shell</li>
    </ul>
