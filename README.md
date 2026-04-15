# 🎾 Arena Padel Club — Frontend

Proyecto frontend para la plataforma web de **Arena Padel Club**, un club de pádel ubicado en Madrid. La aplicación permite a los usuarios consultar las instalaciones, registrarse, iniciar sesión y gestionar sus reservas de pistas. Los administradores disponen de un panel de control completo para gestionar pistas, usuarios y reservas.

---

## 🗂️ Estructura del proyecto

El proyecto está construido únicamente con **HTML5 y CSS3** (sin frameworks de JavaScript), y se organiza en tres grandes bloques de páginas según el rol del usuario:

```
practica_final_FRONTEND/
│
├── img/                          # Recursos gráficos (logo, imágenes de secciones, blog, etc.)
├── styles.css                    # Hoja de estilos global compartida por todas las páginas
│
├── index.html                    # Landing page pública
├── login.html                    # Inicio de sesión
├── registro.html                 # Registro de nuevos usuarios
│
├── index_log_user.html           # Home para usuario autenticado
├── index_log_admin.html          # Home para administrador autenticado
│
├── pistas.html                   # Listado de pistas (vista pública)
├── pista_detalle.html            # Detalle de una pista (vista pública)
│
├── usuario_pistas.html           # Listado de pistas (vista usuario)
├── usuario_pista_detalle.html    # Detalle de pista (vista usuario)
├── usuario_reservas.html         # Mis reservas
├── usuario_reserva_detalle.html  # Detalle de una reserva
├── usuario_reserva_nueva.html    # Formulario para nueva reserva
├── usuario_detalle.html          # Perfil del usuario
│
├── admin_pistas.html             # Gestión de pistas (admin)
├── admin_pista_form.html         # Formulario crear/editar pista (admin)
├── pista_detalle_admin.html      # Detalle de pista (admin)
├── admin_reservas.html           # Gestión de reservas (admin)
├── admin_reserva_detalle.html    # Detalle de reserva (admin)
├── admin_reserva_nueva.html      # Nueva reserva (admin)
├── admin_usuarios.html           # Gestión de usuarios (admin)
├── admin_usuario_detalle.html    # Detalle de usuario (admin)
└── admin_usuario_form.html       # Formulario crear/editar usuario (admin)
```

---

## 👥 Roles y flujos de navegación

### Visitante (no autenticado)
- Accede a la landing page (`index.html`) con información del club, blog y secciones de instalaciones.
- Puede registrarse (`registro.html`) o iniciar sesión (`login.html`).
- Puede consultar el listado y detalle de pistas disponibles sin autenticación.

### Usuario registrado
- Tras el login, accede a su versión del home (`index_log_user.html`).
- Puede consultar pistas, ver su disponibilidad y crear nuevas reservas.
- Gestiona sus reservas y accede a los detalles de su perfil.

### Administrador
- Accede al home de administración (`index_log_admin.html`) con un menú desplegable de gestión.
- Tiene control total sobre pistas (crear, modificar, eliminar), reservas y usuarios.
- Navega por paneles de listado con buscador y acciones directas por registro.

---

## 📄 Descripción de las páginas principales

### `index.html` — Landing page
Página de inicio pública. Contiene las siguientes secciones:

- **Cabecera** (`<header class="cabecera">`): logo, navegación principal con anclas internas y botones de registro/login.
- **Sección de entrada** (`#inicio`): título principal, descripción y llamada a la acción hacia el registro.
- **Blog** (`#blog`): cuadrícula de 6 artículos con imagen y texto sobre contenidos del club (técnica, nutrición, equipamiento, etc.).
- **Instalaciones** (`#instalaciones`): imagen + lista de las instalaciones disponibles (10 pistas de pádel, 4 de tenis, gimnasio, piscina, spa, etc.).
- **Reservas / Disponibilidad** (`#reservas`, `#disponibilidad`): sección de llamada a la acción con dos botones de navegación.
- **Footer** (`#contacto`): información del club, contacto y derechos.

### `login.html` — Inicio de sesión
Página con layout de dos columnas (`contenedor-2col`):
- Columna izquierda: texto introductorio.
- Columna derecha: formulario de login con campos de correo y contraseña, que redirige a `index_log_user.html`.

### `registro.html` — Registro
Formulario de registro de nuevo usuario con campos de datos personales.

### `admin_pistas.html` — Panel de gestión de pistas
Vista de administración con:
- **Banner de sección** con título y descripción.
- **Barra de acciones**: botón "Añadir pista" + campo buscador.
- **Listado de pistas** en formato de filas (`fila-dato`) con ID, nombre y botones de acción (Modificar / Eliminar).

### `admin_usuarios.html` / `admin_reservas.html`
Siguen el mismo patrón que `admin_pistas.html`: banner + barra de acciones + listado tabular con acciones por fila.

---

## 🎨 Estilos CSS (`styles.css`)

Existe una única hoja de estilos compartida por todas las páginas del proyecto. Las clases más representativas son:

### Layout y contenedor
| Clase | Descripción |
|---|---|
| `.contenedor` | Ancho máximo centrado horizontalmente |
| `.estructura-cabecera` | Flexbox horizontal para cabecera (logo + nav + acciones) |
| `.contenedor-2col` | Rejilla de dos columnas (usado en login/registro) |
| `.estructura-pie` | Flexbox horizontal para el footer |

### Cabecera y navegación
| Clase | Descripción |
|---|---|
| `.cabecera` | Barra superior fija con fondo y sombra |
| `.logotipo-cabecera` | Contenedor del logo |
| `.navegacion-inicio` | Menú de enlaces horizontales |
| `.registro-login` | Grupo de botones de acceso |
| `.menu-usuario` | Menú desplegable del usuario autenticado |
| `.desplegable-usuario` | Panel desplegable con opciones de perfil y logout |

### Botones
| Clase | Descripción |
|---|---|
| `.btn` | Estilos base del botón (padding, border-radius, transiciones) |
| `.btn-relleno` | Botón con fondo de color primario |
| `.btn-claro` | Botón con borde y fondo transparente |
| `.btn-pequeno` | Variante de tamaño reducido para tablas y listas |

### Secciones de contenido
| Clase | Descripción |
|---|---|
| `.entrada` | Sección hero con imagen y texto en dos columnas |
| `.entrada-pequena` | Versión compacta del hero para páginas interiores |
| `.bloque-intermedio` | Franja de separación con texto destacado |
| `.seccion-blog` | Sección del blog con cuadrícula de artículos |
| `.blog-cuadrado` | Tarjeta individual de artículo (imagen + contenido) |
| `.seccion-instalaciones` | Layout dos columnas: imagen + lista de instalaciones |
| `.seccion-res-disp` | Sección de reservas/disponibilidad centrada |
| `.seccion-login` | Contenedor principal de páginas de login, formularios y paneles |

### Formularios
| Clase | Descripción |
|---|---|
| `.caja` | Caja con fondo, borde y sombra suave para formularios y listados |
| `.formulario-login` | Estilo del formulario de acceso |
| `.grupo-formulario` | Grupo de label + input |
| `.boton-formulario` | Botón de submit a ancho completo |
| `.texto-secundario-login` | Texto de apoyo bajo el formulario |

### Panel de administración
| Clase | Descripción |
|---|---|
| `.barra-acciones` | Fila con botón de acción principal y campo de búsqueda |
| `.buscador` | Input de texto para filtrar listados |
| `.fila-dato` | Fila de un elemento en un listado (ID + datos + botones) |
| `.cabecera-listado` | Fila de cabecera del listado con estilo diferenciado |

---

## 🛠️ Tecnologías utilizadas

- **HTML5** — estructura semántica con `<header>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<nav>`.
- **CSS3** — estilos propios sin librerías externas; uso de Flexbox para layouts, variables de clase para componentes reutilizables.
- Sin dependencias de JavaScript ni frameworks externos.

---

## 📌 Notas

- El proyecto representa el **prototipo frontend** de una plataforma de reservas, por lo que los formularios y acciones de los botones son simulados mediante navegación entre páginas estáticas.
- Las imágenes del club (logo, instalaciones, blog) se encuentran en la carpeta `/img`.
- La navegación entre roles se simula a través de diferentes versiones de las mismas páginas (p. ej. `pista_detalle.html` vs `pista_detalle_admin.html`).

---

*Proyecto desarrollado como práctica final de Frontend — © 2026 Arena Padel Club*
