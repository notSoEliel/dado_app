⚠️ **Importante**: Este proyecto utiliza submódulos de Git para separar el frontend (Flutter) y el backend (FastAPI).  
Después de clonar este repositorio, asegúrate de seguir las instrucciones más abajo para inicializar correctamente los submódulos.

# Dado App - Sistema de Login y Registro de Puntos (Flutter + FastAPI)

Este proyecto es una combinación de frontend en Flutter y backend en FastAPI, diseñado como una aplicación sencilla pero funcional que permite a los usuarios autenticarse (sin registro), lanzar un dado y administrar puntos que se actualizan automáticamente desde el servidor.

---

## 📦 Tecnologías Usadas

### 🧭 Frontend

- **Flutter (Dart)**
- SQLite (modo local si se desea sin backend)
- Consumo de API REST para login y puntos

### 🚀 Backend

- **FastAPI (Python)**
- SQLite (Base de datos relacional)
- SQLAlchemy (ORM)
- Estructura modular: modelos, CRUD, rutas

---

## 🔄 Flujo General

1. **Login en Flutter** con username y contraseña.
2. **Flutter envía solicitud a FastAPI** (`/login`).
3. Si es exitoso, el usuario entra a la app.
4. El usuario lanza el dado (función de Flutter).
5. El backend descuenta puntos automáticamente al lanzar el dado y suma si el resultado es 6, todo gestionado en `/lanzar_dado`.

---

## 📁 Carpetas del Proyecto

```markdown
dado_app/
├── dado_app_backend/           # FastAPI
│   ├── main.py
│   ├── models.py
│   ├── database.py
│   ├── crud.py
│   └── seed.py
│
├── dado_app_fluttter/       # Flutter
│   ├── lib/
│   │   ├── main.dart
│   │   └── screens/
│   └── pubspec.yaml
│
└── README.md          # Este archivo
```

---

## 🧰 Cómo clonar y actualizar este repositorio correctamente

Este proyecto utiliza **submódulos de Git** para separar el código del backend y del frontend.

### Clonar el repositorio con submódulos (recomendado):

```bash
git clone --recurse-submodules https://github.com/notSoEliel/dado_app.git
```

### Actualizar el repositorio y submódulos (pull):

```bash
git pull --recurse-submodules
```

### Si ya clonaste o hiciste pull sin la opción de submódulos:

Inicializa y actualiza los submódulos manualmente (recomendado):

```bash
git submodule update --init --recursive
```



---

## 🚀 Cómo Iniciar

Asegúrate de estar en la carpeta raíz del proyecto antes de ejecutar cualquier comando:

```bash
cd dado_app
```

### Backend

1. Instalar dependencias:

```bash
cd dado_app_backend
pip install uv
uv sync
```

2. Crear la base de datos y precargar usuarios:

```bash
uv run seed.py
```

3. Ejecutar el servidor:

```bash
uv run uvicorn main:app --reload
```

### Frontend (Flutter)

```bash
cd dado_app_fluttter
flutter pub get
flutter run
```

⚠️ Usa `10.0.2.2` en lugar de `localhost` si corres Flutter en emulador Android.
