# Piston Bot

<p align="center">
  <img src="assets/logo-neon.png" alt="Piston Bot" width="220" />
</p>

<p align="center">
  <strong>Asistente de ventas para WhatsApp con panel propio, IA y control operativo.</strong><br/>
  Producto de <strong>Piston Quarks</strong>.
</p>

---

## Qué es

**Piston Bot** es un sistema para atender, vender y dar soporte por WhatsApp con:

- **Panel propio** (`/admin`) para operar conversaciones sin depender de la UI de Open-WA.
- **IA asistente de ventas** con modos Plan/Ejecución, sugerencias, estudio de estilo y borradores.
- **Mensajes programados** con historial, cancelación y eliminación.
- **Multi-sesión** por puerto/carpeta de datos (aislamiento por número/operación).
- **PWA** instalable para uso tipo app.
- **Directivas** internas (`DIRECTIVA:`, `REGLA:`, `GUIA:`, `APRENDE:`) para entrenar el comportamiento.
- **Hardening base**: bind local por defecto, token admin opcional, auditoría de acciones sensibles.

## Para quién es

- Negocios que venden por WhatsApp y necesitan respuesta rápida + control humano.
- Equipos que quieren IA con supervisión, no un bot suelto.
- Operaciones que requieren panel, historial, programación y múltiples sesiones.

## Qué incluye este repo público

Este repositorio es la **cara pública / documentación / distribución** del producto:

- Información del producto y arquitectura de alto nivel.
- Guía de instalación y actualización.
- Material de campaña y assets públicos.
- Enlaces a descargas autorizadas.

> **El motor/core comercial, licenciamiento, activación y recursos privados** se mantienen en un repositorio privado: [`piston-bot-core`](https://github.com/pistonquarks-glitch/piston-bot-core) (acceso autorizado/pago).

## Arquitectura (público + privado)

| Capa | Repo | Acceso | Contenido |
|---|---|---|---|
| Público | `piston-bot` | Público | Docs, marketing, instalador público, guías, assets |
| Privado | `piston-bot-core` | Autorizado/pago | Motor, reglas comerciales avanzadas, activación/licencias, integraciones premium, actualizaciones controladas |

El instalador puede distribuirse públicamente, pero **las funciones/licencias premium y el motor privado** se habilitan solo con verificación/autorización válida.

## Instalación rápida (PC autorizada)

### Requisitos

- Windows 10/11
- Node.js LTS (si usas modo portable/código)
- Open-WA / sesión WhatsApp configurada
- Archivo `.env` con credenciales

### Opción A — Instalador (recomendado)

1. Descarga el instalador autorizado.
2. Instálalo y abre el panel local.
3. Configura `.env` / mini panel de configuración.
4. Escanea/activa la sesión WhatsApp en Open-WA.
5. Abre `http://127.0.0.1:2014/admin` (o el puerto configurado).

### Opción B — Código (desarrollo)

```powershell
git clone https://github.com/pistonquarks-glitch/piston-program.git
cd piston-program
Copy-Item .env.example .env
notepad .env
npm install
node src/services/bridgeTest.js
```

Panel dev: `http://127.0.0.1:2013/admin`

## Variables de entorno importantes

```env
OPENWA_URL=http://127.0.0.1:2785
OPENWA_API_KEY=...
OPENWA_SESSION=default
OPENROUTER_API_KEY=...
PORT=2013
ADMIN_BIND=127.0.0.1
ADMIN_TOKEN=pon-un-token-largo-aleatorio
```

## Seguridad (mínimo recomendado)

- Mantener `ADMIN_BIND=127.0.0.1`.
- Configurar `ADMIN_TOKEN` fuerte.
- No exponer el panel a Internet sin túnel autenticado (Tailscale/Cloudflare Access/VPN).
- Rotar claves si fueron expuestas.
- No habilitar ejecución shell remota libre desde WhatsApp.

## Estado del producto

- **MVP operativo**: panel, asistente IA, programados, multi-sesión, PWA, hardening base.
- **En desarrollo**: activación/licencias completa, verificación por dispositivo, descarga controlada del core privado, firma EXE, compliance legal final.

## Contacto / comercial

- **Piston Quarks**: https://pistonquarks.com
- **Soporte/ventas**: canal autorizado por Piston Quarks.

---

© Piston Quarks. Uso público de esta documentación permitido; el motor/comercial privado se rige por licencia/autorización.