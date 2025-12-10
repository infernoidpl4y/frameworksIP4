📚 BackendDev-UI - Documentación Completa

📋 Tabla de Contenidos

1. Instalación
2. Componentes del Dashboard
3. Componentes de Herramientas
4. Componentes Bug Bounty
5. Componentes de Formularios
6. Componentes de Tablas
7. Componentes de Notificación
8. Componentes de Navegación
9. Componentes Modales
10. Componentes Especiales
11. Componentes de Utilidad
12. Ejemplos Completos

---

1. Instalación

Descarga Básica

```html
<!-- En tu HTML -->
<head>
    <!-- Framework base (obligatorio) -->
    <link rel="stylesheet" href="backenddev.css">
    
    <!-- Componentes UI (complementario) -->
    <link rel="stylesheet" href="backenddev-ui.css">
</head>
```

Archivos Requeridos

```
tu-proyecto/
├── backenddev.css      # 4.8KB - Framework base
├── backenddev-ui.css   # 12KB - Componentes UI
└── index.html         # Tu aplicación
```

---

2. Componentes del Dashboard

2.1 Dashboard Grid

```html
<!-- Sistema de grid para dashboard -->
<div class="dashboard-grid">
    <!-- Tus cards aquí -->
</div>
```

Propiedades CSS:

· display: grid
· grid-template-columns: repeat(auto-fit, minmax(280px, 1fr))
· gap: 1rem
· Responsive automático

2.2 Dashboard Card

```html
<div class="dashboard-card">
    Contenido de tu card
</div>
```

Modificadores disponibles:

```html
<!-- Card con borde izquierdo de severidad -->
<div class="dashboard-card stat-critical">
    <!-- Critical severity -->
</div>

<div class="dashboard-card stat-high">
    <!-- High severity -->
</div>

<div class="dashboard-card stat-medium">
    <!-- Medium severity -->
</div>

<div class="dashboard-card stat-low">
    <!-- Low severity -->
</div>
```

2.3 Stat Card

```html
<div class="dashboard-card stat-card stat-critical">
    <div class="stat-icon">💀</div>
    <div class="stat-number">8</div>
    <div class="stat-label">Critical</div>
</div>
```

Estructura interna:

· .stat-icon - Contenedor para icono
· .stat-number - Número grande
· .stat-label - Etiqueta descriptiva

---

3. Componentes de Herramientas

3.1 Tool Panel

```html
<div class="tool-panel">
    <div class="tool-header">
        <h3 class="tool-title">Scanner Tools</h3>
        <span class="tool-badge">PRO</span>
    </div>
    
    <!-- Contenido del panel -->
</div>
```

3.2 Action Grid

```html
<div class="action-grid">
    <a href="#" class="action-btn">
        <span class="action-icon">🔍</span>
        <span class="action-label">Port Scan</span>
    </a>
    
    <a href="#" class="action-btn">
        <span class="action-icon">🕸️</span>
        <span class="action-label">Web Crawl</span>
    </a>
</div>
```

Estructura Action Button:

· .action-btn - Botón de acción
· .action-icon - Icono dentro del botón
· .action-label - Texto del botón

---

4. Componentes Bug Bounty

4.1 Vulnerability Item

```html
<div class="vuln-item">
    <div class="vuln-severity critical"></div>
    <div class="vuln-content">
        <div class="vuln-title">SQL Injection</div>
        <div class="vuln-desc">/api/users endpoint</div>
    </div>
    <div class="vuln-actions">
        <button class="btn btn-sm btn-primary">View</button>
        <button class="btn btn-sm btn-outline">Export</button>
    </div>
</div>
```

Clases de severidad:

· .vuln-severity.critical - Rojo
· .vuln-severity.high - Naranja
· .vuln-severity.medium - Amarillo
· .vuln-severity.low - Verde

4.2 Scan Progress

```html
<div class="scan-progress">
    <div class="progress-header">
        <span>Scanning: target.com</span>
        <span>65%</span>
    </div>
    <div class="progress-bar">
        <div class="progress-fill" style="width: 65%"></div>
    </div>
    <div class="progress-info">
        <span>12 vulnerabilities found</span>
        <span>3 minutes remaining</span>
    </div>
</div>
```

Para actualizar progreso:

```javascript
// Cambiar el ancho de la barra
document.querySelector('.progress-fill').style.width = '75%';
```

---

5. Componentes de Formularios

5.1 Form Card

```html
<div class="form-card">
    <div class="form-section">
        <h4 class="form-title">Scanner Configuration</h4>
        
        <!-- Campos del formulario -->
    </div>
</div>
```

5.2 Input Groups

```html
<div class="input-group">
    <label class="input-label">Target URL</label>
    <input type="url" class="form-control" placeholder="https://example.com">
    <div class="input-hint">Enter the target URL to scan</div>
</div>
```

5.3 Switch Toggle

```html
<label class="input-label">Enable XSS Detection</label>
<label class="switch">
    <input type="checkbox" checked>
    <span class="switch-slider"></span>
</label>
```

Funcionamiento:

· El checkbox real está oculto
· .switch-slider es el control visual
· Se activa con CSS cuando el input está checked

---

6. Componentes de Tablas

6.1 Data Table

```html
<table class="data-table">
    <thead>
        <tr>
            <th>ID</th>
            <th>Type</th>
            <th>Severity</th>
            <th>Actions</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>#001</td>
            <td>XSS</td>
            <td><span class="badge badge-high">HIGH</span></td>
            <td>
                <div class="table-actions">
                    <button class="btn btn-sm btn-primary">View</button>
                </div>
            </td>
        </tr>
    </tbody>
</table>
```

Características:

· Filas con hover effect
· Encabezados estilizados
· Responsive por defecto

6.2 Table Actions Container

```html
<div class="table-actions">
    <button class="btn btn-sm btn-primary">View</button>
    <button class="btn btn-sm btn-outline">Export</button>
</div>
```

---

7. Componentes de Notificación

7.1 Toast Container

```html
<div class="toast-container">
    <!-- Toasts aparecen aquí -->
</div>
```

Posicionamiento: Fixed top-right por defecto

7.2 Toast Notifications

```html
<div class="toast toast-success">
    <div class="toast-icon">✅</div>
    <div class="toast-content">
        <div class="toast-title">Scan Complete</div>
        <div class="toast-message">Found 8 vulnerabilities</div>
    </div>
    <button class="toast-close">×</button>
</div>
```

Tipos de Toast:

· .toast-success - Verde (éxito)
· .toast-error - Rojo (error)
· .toast-warning - Amarillo (advertencia)
· .toast-info - Azul (información)

Para mostrar/ocultar con JavaScript:

```javascript
function showToast(type, title, message) {
    const toast = document.createElement('div');
    toast.className = `toast toast-${type}`;
    toast.innerHTML = `
        <div class="toast-icon">${getIcon(type)}</div>
        <div class="toast-content">
            <div class="toast-title">${title}</div>
            <div class="toast-message">${message}</div>
        </div>
        <button class="toast-close" onclick="this.parentElement.remove()">×</button>
    `;
    
    document.querySelector('.toast-container').appendChild(toast);
    
    // Auto-remove después de 5 segundos
    setTimeout(() => toast.remove(), 5000);
}
```

---

8. Componentes de Navegación

8.1 Sidebar Navigation

```html
<nav class="sidebar-nav">
    <div class="nav-header">
        <div class="nav-title">🐛 BugTracker Pro</div>
    </div>
    
    <div class="nav-menu">
        <a href="#" class="nav-item active">
            <span class="nav-icon">📊</span>
            <span class="nav-label">Dashboard</span>
        </a>
        
        <a href="#" class="nav-item">
            <span class="nav-icon">🔍</span>
            <span class="nav-label">Scanner</span>
            <span class="nav-badge">3</span>
        </a>
    </div>
</nav>
```

Estados del Nav Item:

· .nav-item - Estado normal
· .nav-item:hover - Estado hover
· .nav-item.active - Estado activo (con borde azul)

8.2 Nav Badge

```html
<span class="nav-badge">3</span>
```

Muestra notificaciones o contadores

---

9. Componentes Modales

9.1 Modal Overlay

```html
<div class="modal-overlay">
    <div class="modal">
        <div class="modal-header">
            <h3 class="modal-title">Report Details</h3>
            <button class="modal-close">×</button>
        </div>
        
        <div class="modal-body">
            <!-- Contenido del modal -->
        </div>
        
        <div class="modal-footer">
            <button class="btn btn-outline">Cancel</button>
            <button class="btn btn-primary">Save</button>
        </div>
    </div>
</div>
```

Para mostrar/ocultar modal:

```javascript
// Mostrar modal
document.querySelector('.modal-overlay').style.display = 'flex';

// Ocultar modal
document.querySelector('.modal-overlay').style.display = 'none';

// O cerrar con botón
document.querySelector('.modal-close').onclick = function() {
    this.closest('.modal-overlay').style.display = 'none';
};
```

---

10. Componentes Especiales

10.1 Payload Display

```html
<div class="payload-box">
    <code class="payload-line">
        <span class="payload-comment"># SQL Injection payload</span>
    </code>
    <code class="payload-line">
        <span class="payload-keyword">GET</span> /api/users?id=1' <span class="payload-keyword">OR</span> '1'='1
    </code>
</div>
```

Clases para sintaxis:

· .payload-line - Línea de código
· .payload-comment - Comentarios (verde)
· .payload-string - Strings (naranja)
· .payload-keyword - Palabras clave (azul)

10.2 Attack Timeline

```html
<div class="attack-timeline">
    <div class="timeline-item">
        <div class="timeline-dot success"></div>
        <div class="timeline-content">
            <div class="timeline-time">14:30:23</div>
            <div>Port scan completed</div>
        </div>
    </div>
</div>
```

Tipos de dots:

· .timeline-dot.success - Verde (éxito)
· .timeline-dot.warning - Amarillo (advertencia)
· .timeline-dot.error - Rojo (error)

---

11. Componentes de Utilidad

11.1 Loading Spinner

```html
<!-- Spinner simple -->
<div class="loading"></div>

<!-- Overlay de carga completa -->
<div class="loading-overlay">
    <div class="loading"></div>
</div>
```

11.2 Empty State

```html
<div class="empty-state">
    <div class="empty-icon">🔍</div>
    <h3 class="empty-title">No vulnerabilities found</h3>
    <p class="empty-description">Start a scan to find security issues</p>
    <button class="btn btn-primary mt-4">Start Scan</button>
</div>
```

Usar cuando no hay datos

---

12. Ejemplos Completos

Dashboard de Seguridad Completo

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Security Dashboard</title>
    
    <link rel="stylesheet" href="backenddev.css">
    <link rel="stylesheet" href="backenddev-ui.css">
    
    <style>
        .app-layout {
            display: grid;
            grid-template-columns: 250px 1fr;
            min-height: 100vh;
        }
        
        .main-content {
            padding: 2rem;
            background: #f8fafc;
        }
    </style>
</head>
<body>
    <div class="app-layout">
        <!-- Sidebar -->
        <nav class="sidebar-nav">
            <div class="nav-header">
                <div class="nav-title">🐛 BugTracker Pro</div>
            </div>
            
            <div class="nav-menu">
                <a href="#" class="nav-item active">
                    <span class="nav-icon">📊</span>
                    <span class="nav-label">Dashboard</span>
                </a>
                
                <a href="#" class="nav-item">
                    <span class="nav-icon">🔍</span>
                    <span class="nav-label">Scanner</span>
                    <span class="nav-badge">3</span>
                </a>
            </div>
        </nav>
        
        <!-- Main Content -->
        <main class="main-content">
            <h1 class="mb-4">Security Dashboard</h1>
            
            <!-- Stats -->
            <div class="dashboard-grid">
                <div class="dashboard-card stat-card stat-critical">
                    <div class="stat-icon">💀</div>
                    <div class="stat-number">8</div>
                    <div class="stat-label">Critical</div>
                </div>
            </div>
            
            <!-- Tool Panel -->
            <div class="tool-panel">
                <div class="tool-header">
                    <h3 class="tool-title">Quick Actions</h3>
                    <span class="tool-badge">v1.2.3</span>
                </div>
                
                <div class="action-grid">
                    <a href="#" class="action-btn">
                        <span class="action-icon">🔍</span>
                        <span class="action-label">Port Scan</span>
                    </a>
                </div>
            </div>
        </main>
    </div>
</body>
</html>
```

Reporte de Vulnerabilidad

```html
<div class="form-card">
    <div class="form-section">
        <h4 class="form-title">Vulnerability Report</h4>
        
        <div class="input-group">
            <label class="input-label">Title</label>
            <input type="text" class="form-control" value="SQL Injection in /api/users">
        </div>
        
        <div class="input-group">
            <label class="input-label">Severity</label>
            <select class="form-control">
                <option>Critical</option>
                <option>High</option>
            </select>
        </div>
        
        <div class="input-group">
            <label class="input-label">Payload</label>
            <div class="payload-box">
                <code class="payload-line">GET /api/users?id=1' OR '1'='1</code>
            </div>
        </div>
    </div>
    
    <div class="form-section">
        <div class="d-flex justify-between">
            <button class="btn btn-outline">Cancel</button>
            <button class="btn btn-primary">Save Report</button>
        </div>
    </div>
</div>
```

---

🎨 Personalización

Sobreescribir Variables CSS

```css
/* custom.css */
:root {
    --critical: #ff0000;      /* Cambiar rojo crítico */
    --high: #ff6b00;         /* Cambiar naranja alto */
    --medium: #ffa500;       /* Cambiar amarillo medio */
    --low: #00c853;          /* Cambiar verde bajo */
}

/* Estilos personalizados */
.my-custom-panel {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    border-radius: 16px;
    border: 2px solid var(--critical);
}
```

Responsive Design

Todos los componentes son responsive por defecto. Breakpoints:

· Mobile: < 480px
· Tablet: 480px - 768px
· Desktop: > 768px

---

⚡ Quick Reference Cheat Sheet

Para Dashboard:

```html
.dashboard-grid > .dashboard-card.stat-card.stat-*
  .stat-icon
  .stat-number
  .stat-label
```

Para Herramientas:

```html
.tool-panel > .tool-header
  .tool-title + .tool-badge
  .action-grid > .action-btn
    .action-icon + .action-label
```

Para Bug Bounty:

```html
.vuln-item
  .vuln-severity.[critical|high|medium|low]
  .vuln-content > .vuln-title + .vuln-desc
  .vuln-actions
```

Para Formularios:

```html
.form-card > .form-section
  .form-title
  .input-group > .input-label + input + .input-hint
  .switch > input + .switch-slider
```

---

📝 Notas Importantes

1. Orden de importación: Siempre importa backenddev.css antes que backenddev-ui.css
2. Compatibilidad: Funciona con cualquier navegador moderno
3. Sin dependencias: No requiere JavaScript, pero mejora con él
4. Performance: Solo 12KB gzipped
5. Personalización: Usa custom.css para sobreescribir estilos

---

🚀 Script de Instalación Rápida

```bash
#!/bin/bash
# install-backenddev-ui.sh

echo "Instalando BackendDev UI..."

# Crear directorio
mkdir -p my-bugbounty-tool
cd my-bugbounty-tool

# Descargar frameworks
curl -s -o backenddev.css https://raw.githubusercontent.com/tu-user/backenddev/main/backenddev.css
curl -s -o backenddev-ui.css https://raw.githubusercontent.com/tu-user/backenddev-ui/main/backenddev-ui.css

# Crear ejemplo básico
cat > index.html << 'EOF'
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="backenddev.css">
    <link rel="stylesheet" href="backenddev-ui.css">
</head>
<body>
    <div class="container mt-4">
        <h1>¡BackendDev UI Instalado!</h1>
        <p>Revisa la documentación para usar los componentes.</p>
    </div>
</body>
</html>
EOF

echo "✅ Instalación completada en: $(pwd)"
echo "📖 Ver documentación: https://github.com/tu-user/backenddev-ui"
```