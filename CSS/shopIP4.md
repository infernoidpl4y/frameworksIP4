Documentación Completa de BackendStyle

📚 Índice

1. Estructura HTML Básica
2. Sistema de Grid
3. Componentes de Producto
4. Carrito de Compras
5. Checkout
6. Formularios
7. Navegación
8. Utilidades
9. Ejemplos Completos

---

1. 📄 Estructura HTML Básica {#estructura}

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Tienda Online</title>
    <!-- 1. Enlaza el framework -->
    <link rel="stylesheet" href="backendstyle.css">
    <!-- 2. Iconos opcionales -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body>
    <!-- 3. Navegación -->
    <nav class="navbar">
        <!-- Contenido de navegación -->
    </nav>
    
    <!-- 4. Contenedor principal -->
    <div class="container">
        <!-- Tu contenido aquí -->
    </div>
    
    <!-- 5. Scripts (si necesitas) -->
    <script src="tu-script.js"></script>
</body>
</html>
```

Orden obligatorio:

1. Meta tags primero
2. Framework CSS
3. Iconos (opcional)
4. Tu contenido HTML con las clases
5. Scripts al final

---

2. 🏗️ Sistema de Grid {#grid}

Grid Simple (Productos)

```html
<!-- Grid de 3 columnas en desktop, 2 en tablet, 1 en móvil -->
<div class="product-grid">
    <!-- Producto 1 -->
    <div class="product-card">
        <div class="product-image">
            <img src="producto1.jpg" alt="Producto">
        </div>
        <div class="product-info">
            <!-- Contenido del producto -->
        </div>
    </div>
    
    <!-- Producto 2 -->
    <div class="product-card">
        <!-- Misma estructura -->
    </div>
    
    <!-- Más productos... -->
</div>
```

Grid Manual

```html
<div class="grid grid-3">  <!-- Puede ser grid-2, grid-3, grid-4 -->
    <div>Columna 1</div>
    <div>Columna 2</div>
    <div>Columna 3</div>
</div>
```

Sistema Flexbox (para layouts más complejos)

```html
<div class="row">
    <div class="col">Columna flexible 1</div>
    <div class="col">Columna flexible 2</div>
</div>
```

---

3. 🛍️ Componentes de Producto {#productos}

Tarjeta de Producto Básica

```html
<div class="product-card">
    <!-- IMAGEN DEL PRODUCTO (siempre primero) -->
    <div class="product-image">
        <img src="ruta/imagen.jpg" alt="Nombre producto">
        <!-- Badge opcional -->
        <span class="product-badge">Nuevo</span>
    </div>
    
    <!-- INFORMACIÓN DEL PRODUCTO (siempre después de la imagen) -->
    <div class="product-info">
        <!-- 1. Título -->
        <h3 class="product-title">Nombre del Producto</h3>
        
        <!-- 2. Descripción -->
        <p class="product-description">
            Descripción breve del producto. Máximo 2-3 líneas.
        </p>
        
        <!-- 3. Rating (opcional) -->
        <div class="product-rating">
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="far fa-star"></i>
            <span>(4.0)</span>
        </div>
        
        <!-- 4. Precio -->
        <div class="product-price">
            <span class="product-price-old">$99.99</span>
            $79.99
        </div>
        
        <!-- 5. Botón de acción -->
        <button class="btn btn-primary btn-block">
            <i class="fas fa-cart-plus"></i> Añadir al Carrito
        </button>
        
        <!-- Botones adicionales (opcional) -->
        <div class="d-flex justify-between mt-2">
            <button class="btn btn-outline-primary btn-small">
                <i class="far fa-heart"></i> Guardar
            </button>
            <button class="btn btn-outline-secondary btn-small">
                <i class="fas fa-exchange-alt"></i> Comparar
            </button>
        </div>
    </div>
</div>
```

Grid Completo de Productos

```html
<!-- SECCIÓN DE PRODUCTOS -->
<section class="mt-5">
    <!-- Título de sección -->
    <h2 class="text-center mb-4">Productos Destacados</h2>
    
    <!-- Grid de productos -->
    <div class="product-grid">
        <!-- Producto 1 -->
        <div class="product-card">
            <div class="product-image">
                <img src="producto1.jpg" alt="Producto 1">
                <span class="product-badge bg-danger">-20%</span>
            </div>
            <div class="product-info">
                <h3 class="product-title">Laptop Gaming Pro</h3>
                <p class="product-description">RTX 4070, Intel i9, 32GB RAM</p>
                <div class="product-price">$1,299.99</div>
                <button class="btn btn-primary btn-block">Añadir al Carrito</button>
            </div>
        </div>
        
        <!-- Producto 2 -->
        <div class="product-card">
            <div class="product-image">
                <img src="producto2.jpg" alt="Producto 2">
            </div>
            <div class="product-info">
                <h3 class="product-title">Smartphone Ultra</h3>
                <p class="product-description">Pantalla 6.7", 256GB, Cámara 108MP</p>
                <div class="product-price">$899.99</div>
                <button class="btn btn-primary btn-block">Añadir al Carrito</button>
            </div>
        </div>
        
        <!-- Añade más productos igual -->
    </div>
</section>
```

---

4. 🛒 Carrito de Compras {#carrito}

```html
<!-- PÁGINA DEL CARRITO -->
<div class="container">
    <h1 class="text-center mb-4">Tu Carrito de Compras</h1>
    
    <div class="row">
        <!-- Lista de productos en el carrito -->
        <div class="col" style="flex: 2;">
            <div class="cart">
                <!-- ITEM 1 -->
                <div class="cart-item">
                    <!-- Imagen -->
                    <div class="cart-item-image">
                        <img src="producto1.jpg" alt="Producto">
                    </div>
                    
                    <!-- Información -->
                    <div class="cart-item-info">
                        <h4 class="cart-item-title">Laptop Gaming Pro</h4>
                        <p class="text-gray">Color: Negro • Modelo: RTX 4070</p>
                        <div class="cart-item-price">$1,299.99</div>
                    </div>
                    
                    <!-- Acciones -->
                    <div class="cart-item-actions">
                        <!-- Selector de cantidad -->
                        <select class="form-control quantity-input">
                            <option>1</option>
                            <option>2</option>
                            <option>3</option>
                            <option>4</option>
                            <option>5</option>
                        </select>
                        
                        <!-- Botón eliminar -->
                        <button class="btn btn-danger btn-small">
                            <i class="fas fa-trash"></i> Eliminar
                        </button>
                    </div>
                </div>
                
                <!-- ITEM 2 (misma estructura) -->
                <div class="cart-item">
                    <!-- ... -->
                </div>
            </div>
        </div>
        
        <!-- Resumen del pedido -->
        <div class="col" style="flex: 1;">
            <div class="cart p-4">
                <h3 class="mb-3">Resumen del Pedido</h3>
                
                <!-- Subtotal -->
                <div class="d-flex justify-between mb-2">
                    <span>Subtotal:</span>
                    <span>$2,199.98</span>
                </div>
                
                <!-- Envío -->
                <div class="d-flex justify-between mb-2">
                    <span>Envío:</span>
                    <span class="text-success">Gratis</span>
                </div>
                
                <!-- Impuestos -->
                <div class="d-flex justify-between mb-2">
                    <span>Impuestos:</span>
                    <span>$219.99</span>
                </div>
                
                <!-- Línea divisoria -->
                <hr class="my-3">
                
                <!-- Total -->
                <div class="cart-total">
                    <strong>Total:</strong>
                    <span class="text-primary" style="font-size: 1.5rem;">$2,419.97</span>
                </div>
                
                <!-- Botón de checkout -->
                <button class="btn btn-success btn-large btn-block mt-4">
                    <i class="fas fa-lock"></i> Proceder al Pago
                </button>
                
                <!-- Continuar comprando -->
                <a href="productos.html" class="btn btn-light btn-block mt-2">
                    <i class="fas fa-arrow-left"></i> Seguir Comprando
                </a>
            </div>
        </div>
    </div>
</div>
```

---

5. 💳 Checkout (Paso a Paso) {#checkout}

```html
<!-- PROCESO DE CHECKOUT -->
<div class="container">
    <h1 class="text-center mb-4">Finalizar Compra</h1>
    
    <!-- Pasos del checkout -->
    <div class="checkout-steps">
        <!-- Paso 1 - Activo -->
        <div class="checkout-step active">
            <div class="step-number">1</div>
            <div class="step-label">Información</div>
        </div>
        
        <!-- Paso 2 - Inactivo -->
        <div class="checkout-step">
            <div class="step-number">2</div>
            <div class="step-label">Envío</div>
        </div>
        
        <!-- Paso 3 - Inactivo -->
        <div class="checkout-step">
            <div class="step-number">3</div>
            <div class="step-label">Pago</div>
        </div>
        
        <!-- Paso 4 - Inactivo -->
        <div class="checkout-step">
            <div class="step-number">4</div>
            <div class="step-label">Confirmación</div>
        </div>
    </div>
    
    <!-- Formulario actual (Paso 1) -->
    <div class="row mt-5">
        <div class="col" style="flex: 2;">
            <div class="cart p-4">
                <h3 class="mb-4">Información de Contacto</h3>
                
                <!-- Formulario -->
                <form id="checkout-form">
                    <!-- Nombre completo -->
                    <div class="form-group">
                        <label class="form-label" for="nombre">Nombre Completo</label>
                        <input type="text" class="form-control" id="nombre" placeholder="Juan Pérez" required>
                    </div>
                    
                    <!-- Email -->
                    <div class="form-group">
                        <label class="form-label" for="email">Email</label>
                        <input type="email" class="form-control" id="email" placeholder="juan@ejemplo.com" required>
                    </div>
                    
                    <!-- Teléfono -->
                    <div class="form-group">
                        <label class="form-label" for="telefono">Teléfono</label>
                        <input type="tel" class="form-control" id="telefono" placeholder="+34 600 000 000" required>
                    </div>
                    
                    <!-- Dirección -->
                    <div class="form-group">
                        <label class="form-label" for="direccion">Dirección</label>
                        <textarea class="form-control" id="direccion" rows="3" required></textarea>
                    </div>
                    
                    <!-- Ciudad y Código Postal -->
                    <div class="row">
                        <div class="col">
                            <div class="form-group">
                                <label class="form-label" for="ciudad">Ciudad</label>
                                <input type="text" class="form-control" id="ciudad" required>
                            </div>
                        </div>
                        <div class="col">
                            <div class="form-group">
                                <label class="form-label" for="cp">Código Postal</label>
                                <input type="text" class="form-control" id="cp" required>
                            </div>
                        </div>
                    </div>
                    
                    <!-- País -->
                    <div class="form-group">
                        <label class="form-label" for="pais">País</label>
                        <select class="form-control form-select" id="pais" required>
                            <option value="">Selecciona un país</option>
                            <option value="ES">España</option>
                            <option value="MX">México</option>
                            <option value="AR">Argentina</option>
                            <option value="CO">Colombia</option>
                            <option value="CL">Chile</option>
                        </select>
                    </div>
                </form>
            </div>
        </div>
        
        <!-- Resumen del pedido (lateral) -->
        <div class="col" style="flex: 1;">
            <div class="cart p-4">
                <h3 class="mb-3">Tu Pedido</h3>
                
                <!-- Lista de productos -->
                <div class="mb-3">
                    <div class="d-flex justify-between mb-1">
                        <span>Laptop Gaming Pro x1</span>
                        <span>$1,299.99</span>
                    </div>
                    <div class="d-flex justify-between mb-1">
                        <span>Smartphone Ultra x2</span>
                        <span>$1,799.98</span>
                    </div>
                </div>
                
                <!-- Totales -->
                <div class="cart-total">
                    <strong>Total:</strong>
                    <span>$3,099.97</span>
                </div>
                
                <!-- Botón siguiente -->
                <button type="submit" form="checkout-form" class="btn btn-primary btn-large btn-block mt-4">
                    Continuar al Envío <i class="fas fa-arrow-right"></i>
                </button>
            </div>
        </div>
    </div>
</div>
```

---

6. 📝 Formularios {#formularios}

Formulario de Registro

```html
<div class="container" style="max-width: 600px;">
    <div class="cart p-5">
        <h2 class="text-center mb-4">Crear Cuenta</h2>
        
        <form>
            <!-- Nombre -->
            <div class="form-group">
                <label class="form-label">Nombre</label>
                <input type="text" class="form-control" placeholder="Tu nombre" required>
            </div>
            
            <!-- Apellidos -->
            <div class="form-group">
                <label class="form-label">Apellidos</label>
                <input type="text" class="form-control" placeholder="Tus apellidos" required>
            </div>
            
            <!-- Email -->
            <div class="form-group">
                <label class="form-label">Email</label>
                <input type="email" class="form-control" placeholder="tu@email.com" required>
            </div>
            
            <!-- Contraseña -->
            <div class="form-group">
                <label class="form-label">Contraseña</label>
                <input type="password" class="form-control" placeholder="Mínimo 8 caracteres" required>
                <small class="text-gray">Debe contener al menos una letra mayúscula y un número</small>
            </div>
            
            <!-- Confirmar contraseña -->
            <div class="form-group">
                <label class="form-label">Confirmar Contraseña</label>
                <input type="password" class="form-control" placeholder="Repite tu contraseña" required>
            </div>
            
            <!-- Checkbox términos -->
            <div class="form-check mb-4">
                <input type="checkbox" class="form-check-input" id="terminos" required>
                <label class="form-check-label" for="terminos">
                    Acepto los <a href="#" class="text-primary">Términos y Condiciones</a>
                </label>
            </div>
            
            <!-- Botón submit -->
            <button type="submit" class="btn btn-primary btn-block btn-large">
                Crear Cuenta
            </button>
            
            <!-- Enlace login -->
            <p class="text-center mt-3">
                ¿Ya tienes cuenta? <a href="login.html" class="text-primary">Inicia sesión</a>
            </p>
        </form>
    </div>
</div>
```

Formulario de Contacto

```html
<form>
    <!-- Asunto con select -->
    <div class="form-group">
        <label class="form-label">Asunto</label>
        <select class="form-control form-select" required>
            <option value="">Selecciona un asunto</option>
            <option value="pedido">Consulta sobre un pedido</option>
            <option value="devolucion">Devolución o cambio</option>
            <option value="producto">Información de producto</option>
            <option value="otro">Otro</option>
        </select>
    </div>
    
    <!-- Mensaje -->
    <div class="form-group">
        <label class="form-label">Mensaje</label>
        <textarea class="form-control" rows="5" placeholder="Describe tu consulta..." required></textarea>
    </div>
    
    <!-- Adjuntar archivo -->
    <div class="form-group">
        <label class="form-label">Adjuntar archivo (opcional)</label>
        <input type="file" class="form-control">
        <small class="text-gray">Máximo 5MB. Formatos: PDF, JPG, PNG</small>
    </div>
</form>
```

---

7. 🧭 Navegación {#navegacion}

Navbar Completo

```html
<nav class="navbar">
    <!-- Logo y marca -->
    <a href="index.html" class="navbar-brand">
        <i class="fas fa-store"></i> MiTienda
    </a>
    
    <!-- Menú principal -->
    <ul class="navbar-nav">
        <li><a href="index.html" class="nav-link active">Inicio</a></li>
        <li><a href="productos.html" class="nav-link">Productos</a></li>
        <li><a href="categorias.html" class="nav-link">Categorías</a></li>
        <li><a href="ofertas.html" class="nav-link">Ofertas</a></li>
        <li><a href="contacto.html" class="nav-link">Contacto</a></li>
    </ul>
    
    <!-- Iconos de usuario/carrito -->
    <div class="d-flex align-center">
        <!-- Buscador -->
        <div class="mr-3">
            <input type="text" class="form-control" placeholder="Buscar productos..." style="width: 200px;">
        </div>
        
        <!-- Usuario -->
        <a href="cuenta.html" class="nav-link mr-3">
            <i class="fas fa-user"></i> Mi Cuenta
        </a>
        
        <!-- Carrito con contador -->
        <a href="carrito.html" class="nav-link cart-icon">
            <i class="fas fa-shopping-cart"></i>
            <span class="cart-count">3</span>
        </a>
    </div>
</nav>
```

---

8. 🎨 Utilidades (Clases Rápidas) {#utilidades}

Espaciado (Margins y Paddings)

```html
<!-- Margin Top -->
<div class="mt-1">Pequeño margen superior</div>
<div class="mt-3">Margen superior normal</div>
<div class="mt-5">Gran margen superior</div>

<!-- Margin Bottom -->
<div class="mb-2">Margen inferior pequeño</div>
<div class="mb-4">Margen inferior grande</div>

<!-- Padding -->
<div class="p-3">Padding normal</div>
<div class="p-5">Padding grande</div>
```

Display y Flexbox

```html
<!-- Display -->
<div class="d-none">Oculto</div>
<div class="d-block">En bloque</div>
<div class="d-flex">Contenedor flex</div>

<!-- Flexbox -->
<div class="d-flex justify-between">
    <div>Izquierda</div>
    <div>Derecha</div>
</div>

<div class="d-flex justify-center">
    <div>Centrado</div>
</div>

<div class="d-flex align-center">
    <div>Centrado vertical</div>
</div>
```

Colores de fondo y texto

```html
<!-- Fondos -->
<div class="bg-primary text-white">Azul con texto blanco</div>
<div class="bg-success text-white">Verde éxito</div>
<div class="bg-danger text-white">Rojo peligro</div>
<div class="bg-light">Fondo claro</div>

<!-- Texto -->
<p class="text-primary">Texto azul</p>
<p class="text-success">Texto verde</p>
<p class="text-danger">Texto rojo</p>
<p class="text-center">Texto centrado</p>
```

Bordes y Sombras

```html
<div class="rounded">Bordes redondeados</div>
<div class="rounded-lg">Bordes más redondeados</div>
<div class="shadow">Con sombra</div>
<div class="shadow-lg">Con sombra grande</div>
```

---

9. 🚀 Ejemplos Completos {#ejemplos}

Página de Inicio Completa

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Tienda Online</title>
    <link rel="stylesheet" href="backendstyle.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body>
    <!-- NAVEGACIÓN -->
    <nav class="navbar">
        <a href="index.html" class="navbar-brand">
            <i class="fas fa-store"></i> TechStore
        </a>
        <ul class="navbar-nav">
            <li><a href="index.html" class="nav-link active">Inicio</a></li>
            <li><a href="productos.html" class="nav-link">Productos</a></li>
            <li><a href="categorias.html" class="nav-link">Categorías</a></li>
            <li><a href="ofertas.html" class="nav-link">Ofertas</a></li>
        </ul>
        <div>
            <a href="carrito.html" class="nav-link cart-icon">
                <i class="fas fa-shopping-cart"></i>
                <span class="cart-count">2</span>
            </a>
        </div>
    </nav>
    
    <!-- HERO SECTION -->
    <div class="bg-primary text-white p-5 rounded-lg mb-5">
        <div class="container">
            <h1 class="mb-3">Ofertas de Temporada</h1>
            <p class="mb-4">Hasta 50% de descuento en productos seleccionados</p>
            <a href="ofertas.html" class="btn btn-light btn-large">
                Ver Ofertas <i class="fas fa-arrow-right"></i>
            </a>
        </div>
    </div>
    
    <!-- PRODUCTOS DESTACADOS -->
    <div class="container">
        <h2 class="text-center mb-4">Productos Destacados</h2>
        
        <div class="product-grid">
            <!-- PRODUCTO 1 -->
            <div class="product-card">
                <div class="product-image">
                    <img src="laptop.jpg" alt="Laptop Gaming">
                    <span class="product-badge bg-danger">-30%</span>
                </div>
                <div class="product-info">
                    <h3 class="product-title">Laptop Gaming Pro</h3>
                    <p class="product-description">RTX 4070, Intel i9, 32GB RAM</p>
                    <div class="product-rating">
                        <i class="fas fa-star"></i><i class="fas fa-star"></i>
                        <i class="fas fa-star"></i><i class="fas fa-star"></i>
                        <i class="far fa-star"></i> (4.2)
                    </div>
                    <div class="product-price">
                        <span class="product-price-old">$1,499.99</span>
                        $1,299.99
                    </div>
                    <button class="btn btn-primary btn-block">Añadir al Carrito</button>
                </div>
            </div>
            
            <!-- PRODUCTO 2 -->
            <div class="product-card">
                <div class="product-image">
                    <img src="smartphone.jpg" alt="Smartphone">
                </div>
                <div class="product-info">
                    <h3 class="product-title">Smartphone Ultra</h3>
                    <p class="product-description">6.7", 256GB, Cámara 108MP</p>
                    <div class="product-rating">
                        <i class="fas fa-star"></i><i class="fas fa-star"></i>
                        <i class="fas fa-star"></i><i class="fas fa-star"></i>
                        <i class="fas fa-star"></i> (4.8)
                    </div>
                    <div class="product-price">$899.99</div>
                    <button class="btn btn-primary btn-block">Añadir al Carrito</button>
                </div>
            </div>
            
            <!-- Añade más productos... -->
        </div>
    </div>
    
    <!-- PIE DE PÁGINA -->
    <footer class="bg-dark text-white p-5 mt-5">
        <div class="container">
            <div class="row">
                <div class="col">
                    <h4>TechStore</h4>
                    <p>Tu tienda de tecnología de confianza</p>
                </div>
                <div class="col">
                    <h5>Enlaces Rápidos</h5>
                    <ul style="list-style: none; padding: 0;">
                        <li><a href="#" class="text-white">Sobre Nosotros</a></li>
                        <li><a href="#" class="text-white">Contacto</a></li>
                        <li><a href="#" class="text-white">Términos y Condiciones</a></li>
                    </ul>
                </div>
                <div class="col">
                    <h5>Contacto</h5>
                    <p><i class="fas fa-envelope"></i> info@techstore.com</p>
                    <p><i class="fas fa-phone"></i> +34 900 000 000</p>
                </div>
            </div>
            <p class="text-center mt-4">© 2023 TechStore. Todos los derechos reservados.</p>
        </div>
    </footer>
</body>
</html>
```

---

📋 Guía Rápida de Uso

Para Productos:

1. Empieza con .product-grid para el contenedor
2. Dentro, cada producto va en .product-card
3. Dentro de cada card: .product-image primero, luego .product-info
4. En info: título → descripción → rating (opcional) → precio → botón

Para Formularios:

1. Cada campo en .form-group
2. Etiqueta con .form-label
3. Input con .form-control
4. Select con .form-control form-select
5. Checkbox con .form-check

Para Layouts:

1. Usa .container para centrar contenido
2. Para dos columnas: .row con dos .col
3. Para grid de productos: .product-grid automático

Orden de Clases (de izquierda a derecha):

```html
<!-- Clase principal primero, luego utilidades -->
<button class="btn btn-primary btn-block mt-3">
<!-- ^ componente ^ color ^ tamaño ^ margen -->
```

---

🎯 Regla de Oro del Backend Developer

Copia y pega estos bloques en tus templates y solo cambia:

· Los textos
· Las imágenes
· Los precios
· Los enlaces

El CSS ya hace todo el trabajo de diseño por ti. ¡No necesitas saber CSS!

¿Problemas? Usa siempre este orden:

1. .container o .container-fluid
2. .row si necesitas columnas
3. .col para cada columna
4. .product-card, .cart, o .form-group según lo que necesites
5. Dentro, las clases específicas de cada componente

¡Listo! Ahora puedes crear una tienda online completa solo copiando estos bloques de código.