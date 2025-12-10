📚 Documentación: BackendDev-Auth

1. Login Básico

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <link rel="stylesheet" href="backenddev.css">
    <link rel="stylesheet" href="backenddev-auth.css">
</head>
<body class="login-container">
    <div class="login-right">
        <div class="login-card">
            <div class="login-header">
                <div class="login-logo">🔒</div>
                <h1 class="login-title">Security Dashboard</h1>
                <p class="login-subtitle">Bug Bounty Toolkit v1.0</p>
            </div>
            
            <div class="login-body">
                <!-- Mensaje de error -->
                <div class="login-error" style="display: none;">
                    Credenciales incorrectas
                </div>
                
                <!-- Formulario -->
                <form id="loginForm">
                    <div class="login-form-group">
                        <label class="login-label">Email o Usuario</label>
                        <input type="text" class="login-input" placeholder="admin@example.com" required>
                    </div>
                    
                    <div class="login-form-group">
                        <label class="login-label">Contraseña</label>
                        <div class="password-group">
                            <input type="password" class="login-input" placeholder="••••••••" required>
                            <button type="button" class="password-toggle">👁️</button>
                        </div>
                    </div>
                    
                    <div class="login-options">
                        <label class="remember-me">
                            <input type="checkbox">
                            <span>Recordar sesión</span>
                        </label>
                        <a href="#" class="forgot-password">¿Olvidaste tu contraseña?</a>
                    </div>
                    
                    <button type="submit" class="login-btn">Iniciar Sesión</button>
                </form>
                
                <div class="login-footer">
                    <p>¿Primera vez? <a href="register.html">Crear una cuenta</a></p>
                </div>
            </div>
        </div>
    </div>
    
    <script>
        // Toggle para mostrar/ocultar contraseña
        document.querySelector('.password-toggle').addEventListener('click', function() {
            const input = this.previousElementSibling;
            const type = input.type === 'password' ? 'text' : 'password';
            input.type = type;
            this.textContent = type === 'password' ? '👁️' : '🙈';
        });
        
        // Validación básica del formulario
        document.getElementById('loginForm').addEventListener('submit', function(e) {
            e.preventDefault();
            // Aquí iría tu lógica de autenticación
            console.log('Login submitted');
        });
    </script>
</body>
</html>
```

2. Login con Social Auth

```html
<div class="login-card">
    <div class="login-header">
        <div class="login-logo">🐛</div>
        <h1 class="login-title">BugTracker Pro</h1>
    </div>
    
    <div class="login-body">
        <form>
            <!-- Campos del formulario -->
            
            <div class="login-divider">
                <span>o continuar con</span>
            </div>
            
            <div class="social-login">
                <button type="button" class="social-btn google">
                    <span>G</span>
                    <span>Google</span>
                </button>
                
                <button type="button" class="social-btn github">
                    <span>🐙</span>
                    <span>GitHub</span>
                </button>
                
                <button type="button" class="social-btn microsoft">
                    <span>Ⓜ️</span>
                    <span>Microsoft</span>
                </button>
            </div>
            
            <button type="submit" class="login-btn">Iniciar Sesión</button>
        </form>
    </div>
</div>
```

3. Registro de Usuario

```html
<div class="register-container">
    <div class="register-card">
        <div class="register-steps">
            <div class="step active">1. Información</div>
            <div class="step">2. Verificación</div>
            <div class="step">3. Completado</div>
        </div>
        
        <div class="login-body">
            <form id="registerForm">
                <div class="login-form-group">
                    <label class="login-label">Nombre completo</label>
                    <input type="text" class="login-input" required>
                </div>
                
                <div class="login-form-group">
                    <label class="login-label">Email</label>
                    <input type="email" class="login-input" required>
                </div>
                
                <div class="login-form-group">
                    <label class="login-label">Contraseña</label>
                    <div class="password-group">
                        <input type="password" class="login-input" id="password" required>
                        <button type="button" class="password-toggle">👁️</button>
                    </div>
                    <div class="password-strength">
                        <div class="strength-bar">
                            <div class="strength-fill" id="strengthFill"></div>
                        </div>
                        <div class="strength-text" id="strengthText">Seguridad de la contraseña</div>
                    </div>
                </div>
                
                <div class="login-form-group">
                    <label class="login-label">Confirmar contraseña</label>
                    <input type="password" class="login-input" required>
                </div>
                
                <div class="login-form-group">
                    <label class="remember-me">
                        <input type="checkbox" required>
                        <span>Acepto los términos y condiciones</span>
                    </label>
                </div>
                
                <button type="submit" class="login-btn">Crear Cuenta</button>
            </form>
            
            <div class="login-footer">
                <p>¿Ya tienes cuenta? <a href="login.html">Iniciar sesión</a></p>
            </div>
        </div>
    </div>
</div>

<script>
    // Verificador de fortaleza de contraseña
    document.getElementById('password').addEventListener('input', function(e) {
        const password = e.target.value;
        const strengthFill = document.getElementById('strengthFill');
        const strengthText = document.getElementById('strengthText');
        
        let strength = 0;
        
        // Lógica de verificación
        if (password.length >= 8) strength++;
        if (/[A-Z]/.test(password)) strength++;
        if (/[0-9]/.test(password)) strength++;
        if (/[^A-Za-z0-9]/.test(password)) strength++;
        
        // Actualizar UI
        if (password.length === 0) {
            strengthFill.className = 'strength-fill';
            strengthText.textContent = 'Seguridad de la contraseña';
        } else if (strength <= 2) {
            strengthFill.className = 'strength-fill weak';
            strengthText.textContent = 'Débil';
        } else if (strength === 3) {
            strengthFill.className = 'strength-fill fair';
            strengthText.textContent = 'Moderada';
        } else {
            strengthFill.className = 'strength-fill good';
            strengthText.textContent = 'Fuerte';
        }
    });
</script>
```

4. Autenticación de Dos Factores (2FA)

```html
<div class="two-factor-container">
    <div class="two-factor-card">
        <div class="two-factor-icon">🔐</div>
        <h2 class="two-factor-title">Verificación en dos pasos</h2>
        <p class="two-factor-description">
            Introduce el código de 6 dígitos de tu aplicación de autenticación
        </p>
        
        <div class="code-inputs">
            <input type="text" maxlength="1" class="code-input" data-index="1">
            <input type="text" maxlength="1" class="code-input" data-index="2">
            <input type="text" maxlength="1" class="code-input" data-index="3">
            <input type="text" maxlength="1" class="code-input" data-index="4">
            <input type="text" maxlength="1" class="code-input" data-index="5">
            <input type="text" maxlength="1" class="code-input" data-index="6">
        </div>
        
        <div class="two-factor-actions">
            <button class="btn btn-outline">Reenviar código</button>
            <button class="btn btn-primary" id="verify2FA">Verificar</button>
        </div>
        
        <div class="login-footer mt-4">
            <p><a href="#">¿Problemas con el código?</a></p>
        </div>
    </div>
</div>

<script>
    // Lógica para inputs de código 2FA
    const inputs = document.querySelectorAll('.code-input');
    
    inputs.forEach((input, index) => {
        // Permitir solo números
        input.addEventListener('input', function(e) {
            this.value = this.value.replace(/[^0-9]/g, '');
            
            // Auto-avanzar al siguiente input
            if (this.value.length === 1 && index < inputs.length - 1) {
                inputs[index + 1].focus();
            }
            
            // Marcar como llenado
            if (this.value.length === 1) {
                this.classList.add('filled');
            } else {
                this.classList.remove('filled');
            }
        });
        
        // Permitir borrar con Backspace
        input.addEventListener('keydown', function(e) {
            if (e.key === 'Backspace' && this.value.length === 0 && index > 0) {
                inputs[index - 1].focus();
                inputs[index - 1].value = '';
                inputs[index - 1].classList.remove('filled');
            }
        });
        
        // Pegar código completo
        input.addEventListener('paste', function(e) {
            e.preventDefault();
            const paste = (e.clipboardData || window.clipboardData).getData('text');
            const numbers = paste.replace(/[^0-9]/g, '').split('');
            
            numbers.slice(0, 6).forEach((num, i) => {
                if (inputs[i]) {
                    inputs[i].value = num;
                    inputs[i].classList.add('filled');
                }
            });
            
            if (numbers.length >= 6) {
                inputs[5].focus();
            }
        });
    });
</script>
```

5. Recuperación de Contraseña

```html
<div class="recovery-container">
    <div class="recovery-card">
        <div class="recovery-steps">
            <div class="recovery-step active">
                <div class="recovery-step-label">Email</div>
            </div>
            <div class="recovery-step">
                <div class="recovery-step-label">Código</div>
            </div>
            <div class="recovery-step">
                <div class="recovery-step-label">Nueva Contraseña</div>
            </div>
        </div>
        
        <div class="login-body">
            <!-- Paso 1: Email -->
            <div id="step1">
                <h3 class="mb-4">Recuperar contraseña</h3>
                <p class="text-muted mb-4">
                    Introduce tu email y te enviaremos un código de verificación
                </p>
                
                <div class="login-form-group">
                    <label class="login-label">Email</label>
                    <input type="email" class="login-input" placeholder="tu@email.com">
                </div>
                
                <button class="login-btn" onclick="nextStep(2)">Enviar código</button>
                
                <div class="login-footer mt-4">
                    <p><a href="login.html">Volver al login</a></p>
                </div>
            </div>
            
            <!-- Paso 2: Código -->
            <div id="step2" style="display: none;">
                <h3 class="mb-4">Verificar código</h3>
                <p class="text-muted mb-4">
                    Revisa tu email e introduce el código de 6 dígitos
                </p>
                
                <div class="code-inputs mb-4">
                    <input type="text" maxlength="1" class="code-input">
                    <!-- ... 6 inputs total -->
                </div>
                
                <div class="d-flex gap-2">
                    <button class="btn btn-outline flex-1" onclick="prevStep(1)">Atrás</button>
                    <button class="btn btn-primary flex-1" onclick="nextStep(3)">Verificar</button>
                </div>
                
                <div class="text-center mt-4">
                    <button class="btn btn-link">Reenviar código</button>
                </div>
            </div>
            
            <!-- Paso 3: Nueva contraseña -->
            <div id="step3" style="display: none;">
                <h3 class="mb-4">Nueva contraseña</h3>
                
                <div class="login-form-group">
                    <label class="login-label">Nueva contraseña</label>
                    <input type="password" class="login-input">
                </div>
                
                <div class="login-form-group">
                    <label class="login-label">Confirmar contraseña</label>
                    <input type="password" class="login-input">
                </div>
                
                <div class="d-flex gap-2">
                    <button class="btn btn-outline flex-1" onclick="prevStep(2)">Atrás</button>
                    <button class="btn btn-primary flex-1">Restablecer</button>
                </div>
            </div>
        </div>
    </div>
</div>

<script>
    // Navegación entre pasos
    function nextStep(step) {
        // Ocultar todos los pasos
        document.querySelectorAll('[id^="step"]').forEach(el => {
            el.style.display = 'none';
        });
        
        // Mostrar paso actual
        document.getElementById(`step${step}`).style.display = 'block';
        
        // Actualizar indicadores
        document.querySelectorAll('.recovery-step').forEach((el, index) => {
            el.classList.remove('active', 'completed');
            if (index + 1 < step) {
                el.classList.add('completed');
            } else if (index + 1 === step) {
                el.classList.add('active');
            }
        });
    }
    
    function prevStep(step) {
        nextStep(step);
    }
</script>
```

6. Gestión de Sesiones

```html
<div class="sessions-container">
    <div class="card">
        <div class="card-header">
            <h3>Sesiones activas</h3>
            <p class="text-muted">Gestiona tus dispositivos conectados</p>
        </div>
        
        <div class="card-body">
            <!-- Sesión actual -->
            <div class="session-card current">
                <div class="session-header">
                    <div class="session-info">
                        <div class="session-title">Este dispositivo</div>
                        <div class="session-details">
                            <span>🖥️ Windows 10</span>
                            <span>🌐 Chrome 120</span>
                            <span>📍 Madrid, ES</span>
                            <span>🕐 Ahora mismo</span>
                        </div>
                    </div>
                    <div class="session-actions">
                        <span class="badge badge-success">ACTIVA</span>
                    </div>
                </div>
            </div>
            
            <!-- Otras sesiones -->
            <div class="session-card">
                <div class="session-header">
                    <div class="session-info">
                        <div class="session-title">iPhone 13 Pro</div>
                        <div class="session-details">
                            <span>📱 iOS 17</span>
                            <span>🌐 Safari</span>
                            <span>📍 Barcelona, ES</span>
                            <span>🕐 Hace 2 horas</span>
                        </div>
                    </div>
                    <div class="session-actions">
                        <button class="btn btn-sm btn-outline">Cerrar sesión</button>
                    </div>
                </div>
            </div>
            
            <div class="session-card">
                <div class="session-header">
                    <div class="session-info">
                        <div class="session-title">MacBook Pro</div>
                        <div class="session-details">
                            <span>💻 macOS 14</span>
                            <span>🌐 Firefox</span>
                            <span>📍 Valencia, ES</span>
                            <span>🕐 Ayer, 14:30</span>
                        </div>
                    </div>
                    <div class="session-actions">
                        <button class="btn btn-sm btn-outline">Cerrar sesión</button>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="card-footer">
            <button class="btn btn-danger" id="logoutAll">
                Cerrar todas las sesiones excepto esta
            </button>
        </div>
    </div>
</div>

<script>
    // Cerrar sesión en dispositivo
    document.querySelectorAll('.session-card:not(.current) .btn').forEach(btn => {
        btn.addEventListener('click', function() {
            const card = this.closest('.session-card');
            card.style.opacity = '0.5';
            card.style.pointerEvents = 'none';
            this.textContent = 'Cerrando...';
            
            // Aquí iría la llamada a tu API
            setTimeout(() => {
                card.remove();
            }, 1000);
        });
    });
    
    // Cerrar todas las sesiones
    document.getElementById('logoutAll').addEventListener('click', function() {
        if (confirm('¿Seguro que quieres cerrar todas las demás sesiones?')) {
            document.querySelectorAll('.session-card:not(.current)').forEach(card => {
                card.remove();
            });
            this.textContent = '✓ Todas cerradas';
            this.disabled = true;
        }
    });
</script>
```

7. Componentes Individuales para Integración

Password Input con Toggle

```html
<div class="login-form-group">
    <label class="login-label">Contraseña</label>
    <div class="password-group">
        <input type="password" class="login-input" id="passwordField">
        <button type="button" class="password-toggle" onclick="togglePassword()">👁️</button>
    </div>
</div>

<script>
function togglePassword() {
    const input = document.getElementById('passwordField');
    const toggle = document.querySelector('.password-toggle');
    
    if (input.type === 'password') {
        input.type = 'text';
        toggle.textContent = '🙈';
    } else {
        input.type = 'password';
        toggle.textContent = '👁️';
    }
}
</script>
```

Mensajes de Error/Éxito

```html
<!-- Error -->
<div class="login-error">
    Credenciales incorrectas. Inténtalo de nuevo.
</div>

<!-- Éxito -->
<div class="login-success">
    ¡Contraseña cambiada correctamente!
</div>
```

Indicador de Fortaleza de Contraseña

```html
<div class="password-strength">
    <div class="strength-bar">
        <div class="strength-fill weak"></div>
    </div>
    <div class="strength-text">Débil</div>
</div>
```

8. API de JavaScript para Login

```javascript
// backendauth.js - Funciones auxiliares
const BackendAuth = {
    // Validar email
    validateEmail: function(email) {
        const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        return re.test(email);
    },
    
    // Validar fortaleza de contraseña
    validatePassword: function(password) {
        const checks = {
            length: password.length >= 8,
            uppercase: /[A-Z]/.test(password),
            lowercase: /[a-z]/.test(password),
            number: /[0-9]/.test(password),
            special: /[^A-Za-z0-9]/.test(password)
        };
        
        const score = Object.values(checks).filter(Boolean).length;
        
        return {
            valid: score >= 3,
            score: score,
            checks: checks
        };
    },
    
    // Mostrar error
    showError: function(message, element = null) {
        const errorDiv = document.createElement('div');
        errorDiv.className = 'login-error';
        errorDiv.textContent = message;
        
        if (element) {
            element.classList.add('shake');
            element.parentNode.insertBefore(errorDiv, element.nextSibling);
            
            setTimeout(() => {
                element.classList.remove('shake');
            }, 500);
        }
        
        // Auto-remover después de 5 segundos
        setTimeout(() => {
            errorDiv.remove();
        }, 5000);
    },
    
    // Mostrar éxito
    showSuccess: function(message) {
        const successDiv = document.createElement('div');
        successDiv.className = 'login-success';
        successDiv.textContent = message;
        
        document.querySelector('.login-body').prepend(successDiv);
        
        setTimeout(() => {
            successDiv.remove();
        }, 5000);
    },
    
    // Simular login (reemplazar con tu API real)
    login: async function(username, password) {
        // Mostrar loading
        const btn = document.querySelector('.login-btn');
        const originalText = btn.textContent;
        btn.textContent = 'Iniciando sesión...';
        btn.disabled = true;
        
        try {
            // Aquí iría tu llamada a la API real
            // const response = await fetch('/api/login', { ... })
            
            // Simular delay de red
            await new Promise(resolve => setTimeout(resolve, 1500));
            
            // Simular respuesta exitosa
            const success = username === 'admin' && password === 'admin123';
            
            if (success) {
                this.showSuccess('¡Login exitoso! Redirigiendo...');
                // window.location.href = '/dashboard';
                return true;
            } else {
                this.showError('Credenciales incorrectas');
                return false;
            }
        } catch (error) {
            this.showError('Error de conexión');
            return false;
        } finally {
            btn.textContent = originalText;
            btn.disabled = false;
        }
    },
    
    // Logout
    logout: function() {
        localStorage.removeItem('auth_token');
        sessionStorage.removeItem('auth_token');
        document.cookie = 'auth_token=; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/;';
        window.location.href = '/login';
    },
    
    // Verificar si está autenticado
    isAuthenticated: function() {
        return !!localStorage.getItem('auth_token') || 
               !!sessionStorage.getItem('auth_token') ||
               document.cookie.includes('auth_token=');
    },
    
    // Proteger ruta
    protectRoute: function() {
        if (!this.isAuthenticated()) {
            window.location.href = '/login';
            return false;
        }
        return true;
    }
};

// Uso:
/*
// En tu formulario de login
document.getElementById('loginForm').addEventListener('submit', async (e) => {
    e.preventDefault();
    
    const username = document.getElementById('username').value;
    const password = document.getElementById('password').value;
    
    const success = await BackendAuth.login(username, password);
    if (success) {
        // Guardar token (ejemplo)
        localStorage.setItem('auth_token', 'fake-jwt-token');
    }
});

// En tus páginas protegidas
if (!BackendAuth.isAuthenticated()) {
    BackendAuth.protectRoute();
}
*/
```

🎨 Personalización

Cambiar Colores

```css
/* custom-auth.css */
:root {
    --auth-primary: #8b5cf6;      /* Color principal */
    --auth-success: #10b981;      /* Color éxito */
    --auth-error: #ef4444;        /* Color error */
    --auth-warning: #f59e0b;      /* Color advertencia */
}

.login-header {
    background: linear-gradient(135deg, var(--auth-primary) 0%, #6d28d9 100%);
}

.login-btn {
    background: linear-gradient(135deg, var(--auth-primary) 0%, #6d28d9 100%);
}

.login-error {
    background: color-mix(in srgb, var(--auth-error) 10%, white);
    border-color: var(--auth-error);
    color: var(--auth-error);
}
```

Tema Oscuro Personalizado

```css
@media (prefers-color-scheme: dark) {
    .login-card {
        background: #1a1a1a;
    }
    
    .login-input {
        background: #2a2a2a;
        border-color: #3a3a3a;
        color: #f0f0f0;
    }
}
```

📦 Instalación Rápida

```bash
# Descargar todos los frameworks
curl -o backenddev.css https://raw.githubusercontent.com/tu-user/backenddev/main/backenddev.css
curl -o backenddev-ui.css https://raw.githubusercontent.com/tu-user/backenddev-ui/main/backenddev-ui.css
curl -o backenddev-auth.css https://raw.githubusercontent.com/tu-user/backenddev-auth/main/backenddev-auth.css

# Crear archivo de utilidades JavaScript
curl -o backendauth.js https://raw.githubusercontent.com/tu-user/backenddev-auth/main/backendauth.js
```

🔐 Ejemplo de Integración con Backend

Login con Flask (Python)

```python
# app.py
from flask import Flask, request, jsonify, make_response
import jwt
import datetime

app = Flask(__name__)
app.config['SECRET_KEY'] = 'tu-clave-secreta-aqui'

@app.route('/api/login', methods=['POST'])
def login():
    data = request.json
    username = data.get('username')
    password = data.get('password')
    
    # Aquí iría tu lógica de autenticación real
    if username == 'admin' and password == 'admin123':
        # Crear token JWT
        token = jwt.encode({
            'user': username,
            'exp': datetime.datetime.utcnow() + datetime.timedelta(hours=24)
        }, app.config['SECRET_KEY'])
        
        response = make_response(jsonify({'success': True}))
        response.set_cookie('auth_token', token, httponly=True, secure=True)
        return response
    
    return jsonify({'success': False, 'error': 'Credenciales inválidas'}), 401

@app.route('/api/protected')
def protected():
    token = request.cookies.get('auth_token')
    
    if not token:
        return jsonify({'error': 'No autenticado'}), 401
    
    try:
        data = jwt.decode(token, app.config['SECRET_KEY'], algorithms=['HS256'])
        return jsonify({'user': data['user'], 'message': 'Acceso concedido'})
    except:
        return jsonify({'error': 'Token inválido'}), 401
```

Frontend con Fetch API

```javascript
// login.js
async function loginUser(username, password) {
    try {
        const response = await fetch('/api/login', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({ username, password })
        });
        
        if (response.ok) {
            const data = await response.json();
            if (data.success) {
                BackendAuth.showSuccess('Login exitoso!');
                setTimeout(() => {
                    window.location.href = '/dashboard';
                }, 1500);
                return true;
            }
        } else {
            const error = await response.json();
            BackendAuth.showError(error.error || 'Error de autenticación');
            return false;
        }
    } catch (error) {
        BackendAuth.showError('Error de conexión con el servidor');
        return false;
    }
}
```

---

BackendDev-Auth te proporciona todo lo necesario para implementar sistemas de autenticación profesionales sin tener que escribir CSS. Solo copia los componentes que necesites y conecta con tu backend.