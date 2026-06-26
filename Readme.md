# 📱 Frontend de FaceLit

## 🌍 Alcance
La aplicación **FaceLit** será **web y móvil (solo Android)**, diseñada para ser **responsive** y adaptarse a cualquier dispositivo.  
Se construirá con base en el **SRS** y el **enmaquetado en Figma**, garantizando que cada módulo y pantalla cumpla con los requerimientos definidos.  
Cada avance debe estar **documentado en `.md`** dentro del repositorio de documentación independiente.

---

## 🛠️ Tecnologías principales

- **Lenguaje**: [TypeScript](ca://s?q=Qué_es_TypeScript) sobre [JavaScript](ca://s?q=Qué_es_JavaScript)  
- **Framework Web**: [React 19](ca://s?q=Qué_hay_de_nuevo_en_React_19) + [Tailwind CSS](ca://s?q=Qué_es_Tailwind_CSS)  
- **Framework Móvil (Android)**: [React Native](ca://s?q=Qué_es_React_Native) + [Expo SDK](ca://s?q=Qué_es_Expo_SDK)  
- **Internacionalización**: [i18next](ca://s?q=Qué_es_i18next) + [react-i18next](ca://s?q=Cómo_usar_react_i18next)  
- **UI y Estilos**:  
  - `StyleSheet` de React Native  
  - `expo-linear-gradient` para fondos degradados  
  - `@expo/vector-icons` (Ionicons) para íconos  
- **Validaciones**: Formularios con reglas estrictas según el SRS (edad, correo, roles, etc.)  
- **Almacenamiento local**: `localStorage` para idioma y tema (web)  

---

## 🎨 Colores y Temas

### Paleta principal
- Verde principal: `#65B361`  
- Verde claro: `#72C96D`  
- Verde oscuro: `#4A9146`  
- Verde tenue: `rgba(101,179,97,0.10)`

### Modo oscuro 🌙
- Fondo página: `#050505`  
- Superficie: `#07120D`  
- Texto principal: `#FFFFFF`  
- Links: `#8EF58A`

### Modo claro ☀️
- Fondo página: `#F7FFF4`  
- Superficie: `#FFFFFF`  
- Texto principal: `#111111`  
- Links: `#3A8C36`

### Estados semánticos
- Error: `#D92027`  
- Warning: `#E89B2C`  
- Success: `#27AE60`  
- Info: `#4A90D9`

---

## 👥 Roles de usuario

- **Aprendiz**:  
  - Ver sus datos personales, historial y asistencias.  
  - Enviar excusas en caso de ausencia.  

- **Instructor**:  
  - Ver listado de aprendices.  
  - Consultar reportes y gestionar excusas.  

- **Administrador**:  
  - Gestión global de usuarios, fichas y horarios.  
  - Estadísticas y reportes generales.  

---

Link del repositorio: [FaceLit en GitHub](https://github.com/FaceID-Proyect-2026/FaceLit)

Link del enmaquetado en Figma: [FaceLit en Figma](https://www.figma.com/design/fRPJLroPiL9Jeu4zhfy0Zf/FaceID-completo?node-id=0-1&p=f&t=uZZV8NwLUQBqG3jG-0)

## 📂 Estructura del repositorio de documentación

Repositorio independiente: `docs-repo`

```plaintext
docs-repo/
│
├── README.md              <- Resumen general del frontend
├── architecture.md        <- Arquitectura híbrida (React 19 + React Native + Spring Boot)
├── adr/                   <- ADR (Architecture Decision Records)
│   ├── adr-001-react-native.md
│   ├── adr-002-i18next.md
│   └── ...
├── modules/               <- Documentación por cada módulo del SRS
│   ├── HU-01.md           <- Inicio de sesión
│   ├── HU-02.md           <- Gestión de ambientes
│   ├── HU-03.md           <- Gestión académica
│   └── ...
├── styles.md              <- Paleta de colores, temas claro/oscuro, tipografía
├── validation.md          <- Validaciones de formularios y pantallas
├── roles.md               <- Documentación de vistas según rol
├── i18n.md                <- Configuración de internacionalización
└── conventions.md         <- Principios de código limpio y estructura de carpetas

La carpeta de FaceLit.zip enviada sirve como referencia ya que es el primer modulo de auth y que tiene los colores, estilos y la estructura de carpetas. PERO ACLARO QUE ESTA EN REACT NATIVE Y TypeScript.

-No utilizar datos quemados despues se tienen que hacer cambios en los datos de la base de datos.