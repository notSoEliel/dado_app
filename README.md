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
├── backend/           # FastAPI
│   ├── main.py
│   ├── models.py
│   ├── database.py
│   ├── crud.py
│   └── seed.py
│
├── flutter_app/       # Flutter
│   ├── lib/
│   │   ├── main.dart
│   │   └── screens/
│   └── pubspec.yaml
│
└── README.md          # Este archivo
```

---

## 🚀 Cómo Iniciar

### Backend

### 1. Instalar dependencias:

```bash
pip install uv
uv sync
```

### 2. Crear la base de datos y precargar usuarios:

```bash
uv run seed.py
```

### 3. Ejecutar el servidor:

```bash
uv run uvicorn main:app --reload
```


### Frontend (Flutter)

```bash
cd flutter_app
flutter pub get
flutter run
```

⚠️ Usa `10.0.2.2` en lugar de `localhost` si corres Flutter en emulador Android.
