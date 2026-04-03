# ⚡ TechGenius — Cloudflare Tunnel

> Expón tu servidor local al internet en segundos usando Cloudflare Tunnel, compatible con **Linux** y **Termux (Android)**.

---

## 📋 Requisitos

| Requisito | Linux | Termux |
|---|---|---|
| `bash` | ✅ Incluido | ✅ Incluido |
| `curl` | ✅ Incluido | `pkg install curl` |
| `git` | `sudo apt install git` | `pkg install git` |
| `python3` *(para pruebas)* | ✅ Incluido | `pkg install python` |
| Permisos root | ✅ Necesario | ❌ No necesario |

---

## 🚀 Instalación

### En Linux

```bash
# 1. Clonar el repositorio
git clone https://github.com/techgenius505-boop/CloudFlare-Build.git
cd CloudFlare-Build

# 2. Dar permisos
chmod +x cloudflare setup

# 3. Ejecutar setup como root
sudo bash setup
```

### En Termux (Android)

```bash
# 1. Clonar el repositorio
git clone https://github.com/techgenius505-boop/CloudFlare-Build.git
cd CloudFlare-Build

# 2. Dar permisos
chmod +x cloudflare setup

# 3. Ejecutar setup (sin sudo)
bash setup
```

El setup instalará automáticamente `cloudflared` y dejará el comando `cloudflare` disponible de forma global en tu sistema.

---

## 📖 Uso

### Activar el Hostpot(donde comparten datos moviles o tambien conocido como Zona Wifi personal)

### Iniciar un túnel

```bash
cloudflare http <puerto>
```

### Ejemplos

```bash
# Exponer servidor en puerto 8080
cloudflare http 8080

# Exponer servidor en puerto 3000 sin banner
cloudflare http 3000 --silent
```

### Ver ayuda

```bash
cloudflare --help
```

### Actualizar el script

```bash
cloudflare --update
```

---

## 🧪 Prueba rápida

```bash
# Terminal 1 — levantar servidor de prueba
python3 -m http.server 8080

# Terminal 2 — iniciar túnel
cloudflare http 8080
```

Verás algo como:

```
  [✓] Túnel activo!
  FORWARDING: https://algo-random.trycloudflare.com
```

Abre esa URL en cualquier navegador desde cualquier dispositivo.

---

## ⚙️ Opciones disponibles

| Comando | Descripción |
|---|---|
| `cloudflare http <puerto>` | Inicia túnel en el puerto indicado |
| `cloudflare http <puerto> --silent` | Inicia túnel sin mostrar el banner |
| `cloudflare --update` | Actualiza el script |
| `cloudflare --help` | Muestra el menú de ayuda |

---

## 🔍 Ver logs si algo falla

```bash
# Linux
cat /tmp/cloudflare-log

# Termux
cat $HOME/cloudflare-log
```

---

## 🖥️ Sistemas soportados

| Sistema | Soportado |
|---|---|
| Linux (x86_64) | ✅ |
| Linux (ARM64) | ✅ |
| Linux (ARMv7) | ✅ |
| Termux Android (ARM64) | ✅ |
| Termux Android (ARMv7) | ✅ |
| Windows (WSL) | ✅ |

---

## 👤 Autor

**TechGenius**

---

## ⚠️ Aviso

Este proyecto utiliza [Cloudflare Tunnel](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/) de forma gratuita a través de `trycloudflare.com`. Las URLs generadas son temporales y cambian en cada sesión.