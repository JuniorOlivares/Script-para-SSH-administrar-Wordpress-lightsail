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
    
    <h2>🔧 Instalación</h2>
    
    <pre><code># Conectar por SSH
ssh -i tu-llave.pem usuario@tu-servidor

# Descargar el script
wget https://raw.githubusercontent.com/tu-usuario/tu-repo/main/wordpress-emergency.sh

# Dar permisos de ejecución
chmod +x wordpress-emergency.sh

# Ejecutar
./wordpress-emergency.sh</code></pre>
    
    <h2>📖 Uso</h2>
    
    <p>El script presenta un menú interactivo con 17 opciones organizadas en categorías:</p>
    
    <pre><code>==================================
   WordPress Emergency Script     
==================================

GESTIÓN DE PLUGINS:
  1. Ver todos los plugins
  2. Desactivar UN plugin específico
  3. Reactivar UN plugin específico
  4. Desactivar TODOS los plugins
  5. Restaurar todos los plugins

GESTIÓN DE TEMAS:
  6. Ver todos los temas
  7. Cambiar tema activo
  8. Desactivar tema problemático
  9. Activar tema por defecto

DIAGNÓSTICO Y REPARACIÓN:
  10. Ver últimos errores
  11. Activar/Desactivar DEBUG
  12. Reparar permisos
  13. Limpiar caché
  14. Verificar integridad

RESPALDOS:
  15. Backup de plugins
  16. Backup de temas
  17. Backup completo wp-content

  0. Salir</code></pre>
    
    <h2>🛡️ Características de seguridad</h2>
    
    <ul>
        <li><strong>Confirmaciones</strong>: Solicita confirmación antes de acciones destructivas</li>
        <li><strong>Respaldos automáticos</strong>: Crea backups con timestamp antes de cambios masivos</li>
        <li><strong>Sin eliminación</strong>: Nunca borra archivos, solo los renombra</li>
        <li><strong>Validación</strong>: Verifica existencia de archivos/carpetas antes de operar</li>
        <li><strong>Permisos seguros</strong>: Mantiene permisos correctos de WordPress</li>
    </ul>
    
    <h2>🎨 Interfaz mejorada</h2>
    
    <p>Códigos de color para mejor legibilidad:</p>
    <ul>
        <li>🟢 <span style="color: green;">Verde</span>: Operaciones exitosas</li>
        <li>🟡 <span style="color: orange;">Amarillo</span>: Información importante</li>
        <li>🔴 <span style="color: red;">Rojo</span>: Errores y advertencias</li>
    </ul>
    
    <p>Características adicionales:</p>
    <ul>
        <li>Menú numerado fácil de navegar</li>
        <li>Mensajes claros de confirmación</li>
        <li>Indicadores de progreso</li>
    </ul>
    
    <h2>⚙️ Personalización</h2>
    
    <p>Puedes ajustar las rutas editando las variables al inicio del script:</p>
    
    <pre><code>WP_PATH="/opt/bitnami/wordpress"        # Ruta de WordPress
PLUGINS_PATH="$WP_PATH/wp-content/plugins"
THEMES_PATH="$WP_PATH/wp-content/themes"
BACKUP_DIR="$HOME/wp-backups"           # Directorio de respaldos</code></pre>
    
    <h2>🚀 Casos de uso comunes</h2>
    
    <h3>1. Plugin causó pantalla blanca</h3>
    <ul>
        <li>Opción 2: Desactivar el plugin problemático</li>
        <li>O Opción 4: Desactivar todos los plugins</li>
    </ul>
    
    <h3>2. Tema roto el sitio</h3>
    <ul>
        <li>Opción 8: Desactivar tema problemático</li>
        <li>WordPress activará automáticamente un tema por defecto</li>
    </ul>
    
    <h3>3. Necesitas ver qué está fallando</h3>
    <ul>
        <li>Opción 11: Activar modo DEBUG</li>
        <li>Opción 10: Ver últimos errores</li>
    </ul>
    
    <h3>4. Mantenimiento preventivo</h3>
    <ul>
        <li>Opción 15-17: Crear respaldos</li>
        <li>Opción 12: Reparar permisos</li>
        <li>Opción 13: Limpiar caché</li>
    </ul>
    
    <h2>📝 Notas importantes</h2>
    
    <ul>
        <li>Diseñado específicamente para instalaciones Bitnami en AWS Lightsail</li>
        <li>Compatible con otras instalaciones ajustando las rutas</li>
        <li>No requiere herramientas adicionales (no necesita cPanel, Webmin, etc.)</li>
        <li>Alternativa ligera a paneles de control pesados</li>
        <li>Ideal para emergencias cuando el acceso web no funciona</li>
    </ul>
    
    <h2>🤝 Contribuciones</h2>
    
    <p>Las contribuciones son bienvenidas. Por favor:</p>
    
    <ol>
        <li>Fork el proyecto</li>
        <li>Crea tu rama de características (<code>git checkout -b feature/NuevaCaracteristica</code>)</li>
        <li>Commit tus cambios (<code>git commit -m 'Agregar nueva característica'</code>)</li>
        <li>Push a la rama (<code>git push origin feature/NuevaCaracteristica</code>)</li>
        <li>Abre un Pull Request</li>
    </ol>
    
    <h2>📄 Licencia</h2>
    
    <p>Este proyecto está bajo la Licencia MIT - ver el archivo LICENSE para más detalles.</p>
    
    <h2>👨‍💻 Autor</h2>
    
    <p>Creado para la comunidad de WordPress por desarrolladores que han sufrido demasiadas pantallas blancas de la muerte.</p>
    
    <h2>🙏 Agradecimientos</h2>
    
    <ul>
        <li>Comunidad WordPress</li>
        <li>Equipo Bitnami</li>
        <li>Usuarios de AWS Lightsail</li>
    </ul>
    
    <hr>
    
    <p><strong>⭐ Si este script te salvó el día, considera darle una estrella al repositorio!</strong></p>
    
    <div style="margin-top: 50px; padding: 20px; background-color: #f0f0f0; border-radius: 10px;">
        <h3>🔥 Características destacadas</h3>
        <table border="1" cellpadding="10" cellspacing="0" style="width: 100%; border-collapse: collapse;">
            <tr>
                <th>Característica</th>
                <th>Descripción</th>
                <th>Beneficio</th>
            </tr>
            <tr>
                <td><strong>Sin eliminación</strong></td>
                <td>Solo renombra archivos agregando 's'</td>
                <td>Recuperación fácil si te equivocas</td>
            </tr>
            <tr>
                <td><strong>Selección inteligente</strong></td>
                <td>Por número o nombre</td>
                <td>Más rápido y menos errores</td>
            </tr>
            <tr>
                <td><strong>Confirmaciones</strong></td>
                <td>Pregunta antes de acciones importantes</td>
                <td>Evita accidentes costosos</td>
            </tr>
            <tr>
                <td><strong>Colores</strong></td>
                <td>Verde, amarillo y rojo</td>
                <td>Fácil identificación de estados</td>
            </tr>
            <tr>
                <td><strong>Respaldos automáticos</strong></td>
                <td>Con timestamp único</td>
                <td>Historial completo de cambios</td>
            </tr>
        </table>
    </div>
    
    <div style="margin-top: 30px; text-align: center;">
        <p><em>Script creado con ❤️ para la comunidad WordPress</em></p>
    </div>
