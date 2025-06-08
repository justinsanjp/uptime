# 🚦 Simple Status – A Zero-Dependency Status Page

**Simple Status** is a modern, zero-backend status page that runs entirely in your browser.  
No servers. No databases. No frameworks. Just one HTML file you can drop into any static host.

> ⚡ Ideal for small teams, side projects, personal portfolios, or lightweight monitoring dashboards.

---

## ✨ Features

- **🖥 100% Client-Side**  
  Everything runs in the browser. No backend or Node.js required.

- **📦 Zero Dependencies**  
  Only uses [Tailwind CSS](https://tailwindcss.com/) via CDN. No npm, no builds.

- **⚙️ Simple Configuration**  
  Define services in a plain JavaScript array inside the HTML file.

- **📡 Real-Time Status Checks**  
  Uses the `fetch` API to ping services periodically and show their current state.

- **🌙 Clean, Responsive UI**  
  Tailwind-powered dark UI, responsive on all devices.

---

## 📁 Live Preview

> Want to see it in action?  
> [**Live Demo**](https://klexai.justinsanjp.de/status/) 

---

## 🛠 How It Works

- Each service URL is checked using the browser’s `fetch()` API.
- A public, free **CORS proxy** is used to avoid cross-origin errors.
- Service status is shown as:
  - ✅ Operational
  - ❌ Down
  - ⏳ Checking...

> All status checks happen **in the user’s browser** — no external processing involved.

---

## 🔧 Configuration

1. Open the `index.html` file in a code editor.
2. Scroll to the bottom of the file and locate the `services` array inside the `<script>` tag.
3. Add or modify your monitored services.

### Example:

```js
const services = [
  { name: 'Google', url: 'https://google.com' },
  { name: 'Gmail', url: 'https://mail.google.com' },
  { name: 'Gemini', url: 'https://gemini.google.com' },
  { name: 'YouTube', url: 'https://youtube.com' }
];
````

4. Save and deploy the updated file to your static host.

---

## ☁️ Hosting Options

You can host `index.html` anywhere that serves static files:

* [GitHub Pages](https://pages.github.com/)
* [Netlify](https://www.netlify.com/)
* [Vercel](https://vercel.com/)
* Traditional servers (Apache, Nginx, etc.)

---

## 🚀 Deployment Guide

You can host **Simple Status** either on a static **webspace** provider or by **self-hosting** it on your own server. Both methods are quick and easy.

---

### 🌐 Option 1: Webspace Hosting

**Recommended for beginners** — no server setup required.

#### Steps:

1. Get a webspace from a hosting provider.
   👉 Save 5% on [Hostigo](https://hostigo-cloud.de) with code `uptime-justin`, or use any provider of your choice.
2. Download the `index.html` file from this repo.
3. Edit it to add your services.
4. Upload the file to your webspace (usually via FTP or your host's file manager).

✅ You're done! Visit your domain to see the status page in action.

---

### 🧰 Option 2: Self-Host on a Debian-Based Server

**Recommended for developers or advanced users** who want full control.

#### Apache Setup (Debian/Ubuntu)

```bash
# Update and upgrade system packages
sudo apt update && sudo apt upgrade -y

# Install Apache and a text editor
sudo apt install apache2 nano
```

> 💬 **Note:** You *can* use Nginx instead, but **Apache is recommended for simplicity and stability**.
> Based on personal experience, Nginx can be unstable and unpredictable. While it may seem more powerful or modern, I’ve consistently found Apache to be more reliable — and would not recommend Nginx under any circumstances.

---

#### Create & Upload the Status Page

```bash
# Navigate to the web root directory
cd /var/www/html

# (Optional) Create a new folder for the status page
mkdir status
cd status

# Create and edit the HTML file
sudo nano index.html
```

1. Paste the full HTML code into the file.
2. Save and exit:

   * On QWERTY: `Ctrl+S`, then `Ctrl+X`
   * On German layout: `Strg+S`, then `Strg+X`

---

#### Set Permissions

```bash
# Navigate back to the web root
cd /var/www/html

# Ensure the web server user owns the files
sudo chown -R www-data:www-data *
```

✅ Your status page is now live at `http://<your-server-ip>/status`
Make sure port **80** is open in your firewall!

---

## 📄 License

This project is licensed under the **MIT License**.

> ⚠️ Please **do not remove** the footer attribution:
> *"Statuspage by justinsanjp | get on GitHub"*
> per the license terms, it must remain in all versions or derivatives.

---

## 🙌 Credits

Made by [justinsanjp](https://github.com/justinsanjp)

```

