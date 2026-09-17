# Seed-Birdeye Fullstack

Bot de trading de memecoins en Solana (Birdeye + Jupiter v6) con panel web,
backtest engine y agente IA gestor (Hunter, fase shadow).

## Distribuciones
| Objetivo | Cómo |
|---|---|
| VPS/Docker (amd64+arm64) | `cp .env.example .env` → `docker compose up --build` → http://localhost:8000/ui/ |
| Termux headless (ARM64) | `pip install -r backend/requirements.txt` → `uvicorn app.main:app --port 8000` |
| Escritorio (Electron) | `cd desktop && npm install && npm start` (o binarios en Releases) |

## Primera vez
1. `cp .env.example .env` y rellena `MASTER_KEY` (32+ chars aleatorios) y `ADMIN_PASSWORD`.
2. Login demo (SOLO dev): `admin@seed.local` / `changeme-1234`.
3. El bot arranca en `stopped` y `DRY_RUN=true`. Siempre.

## Tests
    cd backend && pytest --cov=app

## Seguridad
- Secretos cifrados en reposo (ChaCha20-Poly1305 puro, RFC 8439). MASTER_KEY independiente del JWT.
- El security_gate (6 checks) es innegociable: ninguna entrada lo omite, ni del scanner ni del agente LLM.
- El agente opera en fase shadow por defecto: cero capital real hasta promoción manual con evidencia.

## Aviso
Software experimental, sin garantía. Ver DISCLAIMER.md. No es asesoramiento financiero.
