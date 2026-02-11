# 🎲 Monopoly Online Multiplayer

Juego de Monopoly en 3D con soporte para multijugador local/LAN, construido con Django + Channels + Three.js.

## 🚀 Características

- ✅ Tablero 3D interactivo con WebGL
- ✅ Multijugador en tiempo real (WebSockets)
- ✅ Soporte para 2-4 jugadores
- ✅ Interfaz moderna y responsive
- ✅ Sistema de chat en vivo
- ✅ Persistencia de datos con SQLite

## 📋 Requisitos

- Python 3.6+
- pip
- Navegador con soporte WebGL

## 🔧 Instalación Local

### 1. Clonar el repositorio
```bash
git clone https://github.com/pablomtz-ti/monopoly-online.git
cd monopoly-online
```

### 2. Instalar dependencias
```bash
# Actualizar pip
python -m pip install --upgrade pip

# Instalar paquetes
pip install -r requirement.txt
```

### 3. Configurar base de datos
```bash
python manage.py migrate
```

### 4. Crear usuarios de prueba (opcional)
```bash
python manage.py createsuperuser --username je0k --email je0k@test.com --noinput
python manage.py shell
```
En el shell de Python:
```python
from django.contrib.auth.models import User
u = User.objects.get(username='je0k')
u.set_password('1')
u.save()
exit()
```

### 5. Ejecutar servidor
```bash
python manage.py runserver 0.0.0.0:8000
```

### 6. Acceder al juego

- **Local**: http://localhost:8000/monopoly/
- **LAN**: http://[TU-IP]:8000/monopoly/

**Credenciales de prueba**:
- Usuario: `je0k` / Contraseña: `1`

## 🌐 Despliegue en Railway

1. Crear cuenta en [railway.app](https://railway.app)
2. Conectar este repositorio
3. Railway detectará automáticamente Django
4. Configurar variables de entorno:
   ```
   DEBUG=False
   ALLOWED_HOSTS=*
   ```
5. Desplegar

## 🎮 Cómo Jugar

1. **Crear cuenta** o usar credenciales de prueba
2. **Crear sala** o unirse a una existente
3. **Esperar jugadores** (2-4 jugadores)
4. **¡Jugar!** - Lanzar dados, comprar propiedades, construir casas/hoteles

## 🛠️ Tecnologías

- **Backend**: Django 1.11, Channels 1.1.8
- **Frontend**: Three.js, JavaScript vanilla
- **Comunicación**: WebSockets (Daphne)
- **Base de datos**: SQLite

## 📝 Notas

- El juego usa **modo de email en consola** para desarrollo
- Los emails de verificación se imprimen en la consola del servidor
- Para producción, configura un servidor SMTP real en `webapps/settings.py`

## 🔥 Firewall (Windows)

Para jugar en LAN, abre el puerto 8000:
```powershell
# Como Administrador
netsh advfirewall firewall add rule name="Monopoly Server" dir=in action=allow protocol=TCP localport=8000
```

## 📄 Licencia

Este proyecto es una adaptación educativa del Monopoly original.

## 🙏 Créditos

- Basado en el proyecto original de CMU Team 16
- Assets 3D de clara.io
- Iconos de Material Design
