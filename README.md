# 🚀 Easy Evolution API Deployment for Docker & Traefik

Deploy a production-ready **Evolution API (WhatsApp Gateway)** instance in seconds using Docker & Traefik.  
This is a **Universal Deployment Package** compatible with any system (CRM, ERP, Chatbot, etc.) that needs to consume the Evolution API.

## ✨ Features
- **Zero-Config Deployment:** Pre-tuned `docker-compose.yml` for production.
- **Full Stack:** Includes PostgreSQL (DB) and Redis (Cache) for high performance.
- **Traefik Ready:** Automatically integrates with your existing Traefik proxy.
- **Secure:** Enforced API Key authentication.

---

## 🛠️ Quick Start (1-Command Install)

1.  **Clone & Go:**
    ```bash
    git clone https://github.com/Mimbex/docker-evolution && cd docker-evolution
    cp .env.example .env && nano .env
    ```

2.  **Edit `.env` (Critical!):**
    Change these values to match your domain and security needs:
    ```ini
    # Domain where API will live (e.g., whatsapp.yourdomain.com)
    SERVER_URL=https://whatsapp.yourdomain.com
    
    # MASTER API KEY (Use a strong password!)
    AUTHENTICATION_API_KEY=CHANGE_THIS_TO_STRONG_PASSWORD_123
    ```

3.  **Launch:**
    ```bash
    docker compose up -d
    ```

---

## 🔗 Integration

Once your containers are running (Green lock on HTTPS), you can connect any software to your API:

- **API URL:** `https://whatsapp.yourdomain.com`
- **Global Token:** The `AUTHENTICATION_API_KEY` you defined in `.env`.
- **Docs:** Your API Swagger docs will be available at `https://whatsapp.yourdomain.com/docs` (if enabled in Evolution settings).

---

## 📁 Project Structure

- `docker-compose.yml`: Main service definition (API + DB + Redis).
- `.env.example`: Configuration template.
- `traefik_network`: Assumes your public Traefik network is named `proxy`. Check `docker-compose.yml` if you use a different name (e.g., `web`).
