# 🚀 Easy Evolution API Deployment for Odoo

Deploy a production-ready **Evolution API (WhatsApp Gateway)** instance in seconds using Docker & Traefik. Designed for seamless integration with Odoo.

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

## 🔗 Odoo Integration Steps

Once your containers are running (Green lock on HTTPS):

1.  Go to **Odoo** -> **Settings** -> **Companies** -> **your company**.
2.  Open the **Evolution Integration** tab.
3.  **API URL:** Enter your domain (e.g., `https://whatsapp.yourdomain.com`).
4.  **API Global Token:** Enter the `AUTHENTICATION_API_KEY` you set in `.env`.
5.  **Instance Name:** Enter a name (e.g., `SalesBot`).
6.  Click **"Test Connection"**.
    - *If it fails, use the "Create Instance" button in the WhatsApp Accounts menu.*

---

## 📁 Project Structure

- `docker-compose.yml`: Main service definition (API + DB + Redis).
- `.env.example`: Configuration template.
- `traefik_network`: Assumes your public Traefik network is named `proxy` (or `web`). Check `docker-compose.yml` if different.
