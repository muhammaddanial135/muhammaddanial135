<h1 align="center">Muhammad Danial Rasool</h1>
<h3 align="center">Full-Stack Developer — Laravel · Vue.js · REST APIs · Payment & Notification Systems</h3>

<p align="center">
  I build production web applications: event ticketing platforms, marketplaces, payment integrations, and API-driven backend systems used by real businesses today.
</p>

<p align="center">
  <a href="mailto:danialrasool135@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white" /></a>
  <a href="https://www.linkedin.com/in/muhammad-danial-web-dev/"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white" /></a>
  <!-- <a href="https://YOUR_PORTFOLIO_URL_HERE"><img src="https://img.shields.io/badge/Portfolio-000000?style=flat&logo=vercel&logoColor=white" /></a> -->
</p>

---

## About Me

I'm a Full-Stack Developer specializing in Laravel and Vue.js, focused on backend architecture, REST API design, and the kind of business logic that real production systems demand — payment processing, authentication flows, notification pipelines, and third-party integrations. My work spans event ticketing platforms, online marketplaces, and SaaS products, from initial schema design through deployment and live production debugging on Linux servers.

I care about systems that hold up under real usage: correct handling of payment edge cases, race conditions in ticket inventory, and background jobs that actually complete under production constraints (PHP-FPM sandboxing, queue workers, process management) rather than just in local development.

---

## 🚀 Featured Projects

### EthicalFreelance

> *One-line description — placeholder, pending details.*

**What it does**
`[PLACEHOLDER — describe the platform: what problem it solves and for whom]`

**Key Engineering Work**
* `[PLACEHOLDER — e.g. backend architecture, auth system, matching/escrow logic]`
* `[PLACEHOLDER]`
* `[PLACEHOLDER]`

**Tech Stack**
`[PLACEHOLDER]`

**Links**
[Repository](#) • [Live Demo](#)

> ⚠️ I don't have verified details on this project yet — share the repo URL or a description of its architecture/features and I'll write this section properly instead of leaving placeholders.

---

### HeyBatman

> *One-line description — placeholder, pending details.*

**What it does**
`[PLACEHOLDER — describe the project's purpose and functionality]`

**Key Engineering Work**
* `[PLACEHOLDER]`
* `[PLACEHOLDER]`
* `[PLACEHOLDER]`

**Tech Stack**
`[PLACEHOLDER]`

**Links**
[Repository](#) • [Live Demo](#)

> ⚠️ Same here — give me the repo link or feature/architecture details and I'll replace this with a real writeup.

---

### Eventos.so — Event Management & Ticketing Platform

> A Laravel-based event ticketing platform serving the Somali market, handling everything from ticket sales to on-site QR check-in.

**What it does**
Eventos.so lets organizers create and sell tickets for events (regular, special, live, and invite-only), while providing dedicated tooling for staff check-in, guest management, and multi-channel payments in a market where local mobile-money providers dominate over cards.

**Key Engineering Work**
* Multi-role authentication system (organizer, organizer staff, scanner, admin) with OTP login over phone and email, including carrier-specific SMS delivery (Somtel, Hormuud) and a phone-number-normalization helper covering Somali carrier prefixes
* Payment integration layer for Somtel/eDahab and WaafiPay, including invoice status polling, transient-vs-terminal failure handling, floating-point rounding fixes for currency math, and an Artisan reconciliation command for stuck "Processing" orders
* QR-code-based check-in system: web-based HID scanner input handling, Honeywell EDA52 hardware integration for a companion Flutter app, and email-embedded QR codes (SVG/base64) built to render correctly across mail clients
* Guest Manager feature: full CRUD across model/controller/dashboard/customer-facing views, with paid-event payment flow reuse and per-event ticket-type assignment
* Background notification pipeline dispatched via `exec()`/`popen()` Artisan commands, solving PHP-FPM vs CLI binary resolution issues so long-running jobs complete outside the request lifecycle; bulk push notifications via CSV/Excel upload with device-token targeting
* Organizer-staff permission scoping (`effectiveOrganizer()` pattern) applied consistently across controllers to prevent cross-organizer data leakage

**Tech Stack**
`Laravel` `PHP` `MySQL` `jQuery` `Bootstrap 5` `Flutter (companion scanner app)` `Somtel/eDahab API` `WaafiPay API`

**Links**
[Repository](#) • [Live Demo](https://eventos.so)

---

### FastWheel.pk — Pakistani Used Car Marketplace

> A Laravel-based marketplace for buying and selling used cars in Pakistan, built to compete directly with established players in the space.

**What it does**
FastWheel.pk lets sellers list vehicles and buyers search, filter, and browse detailed car listings, with a design system and content built specifically around the Pakistani auto market (local makes, cities, and fuel-price context).

**Key Engineering Work**
* Full homepage build with a custom dark navy/orange design system, animated data-reveal sections, and a live fuel-price widget
* Car detail page implementation from a design-tool export into production Blade views
* Car listing upload flow with request validation and storage migration from S3 to local storage
* Phone number normalization for Pakistani numbers, shared across listing and contact flows
* WhatsApp API integration for buyer-seller contact
* Responsive fixes across navigation, listing sidebars, and data tables for mobile use

**Tech Stack**
`Laravel` `PHP` `MySQL` `JavaScript` `Bootstrap` `AWS S3` `WhatsApp Business API`

**Links**
[Repository](#) • [Live Demo](https://fastwheel.pk)

---

## 🧩 Other Projects

### BuynSell — Property / Real Estate Marketplace
A Laravel real estate platform for New Zealand covering agency and agent management, property listings, and buyer engagement.
- Agency/agent CRUD with authentication guards
- Property listing detail pages with per-listing Google Maps integration
- Book-a-viewing modal with email notification flow
- Bookmarking with status-change email alerts to interested buyers
- Brochure PDF generation via `html2pdf`
`Laravel` `Vue 3` `Google Maps API` `MySQL`

### ATX Classic Cars — Car Rental Platform
A Laravel Blade rental platform built on a customized theme integration.
- Booking and checkout flow
- Fleet filtering and car listing cards
- Responsive layout fixes across the booking pipeline
`Laravel` `Blade` `Bootstrap`

### ClinicOS — Dental Clinic SaaS
Reporting and document module for a multi-tenant clinic management SaaS.
- Invoice, patient history, and appointment report pages redesigned to a production-ready SaaS theme
- PDF generation via `dompdf`, built with table-based layouts and inline styles for compatibility
`Laravel` `dompdf` `MySQL`

### SecurityChecked.org — Identity Verification (KYC)
Identity verification flow integrating a third-party KYC provider.
- Sumsub WebSDK integration with HMAC-SHA256 request signing
- Webhook handler processing applicant review status updates
- Two-panel verification UI flow
`Laravel` `Sumsub API` `Webhooks`

### General Marketplace Platform (Buy & Sell)
A Vue-driven multi-category listing platform (Motors / General / Property / Jobs / Services).
- Multi-step listing forms built with Vue 3 Composition API
- Cascading region/district/suburb address selection with postal autocomplete
- Availability filtering via JSON-based day/time fields
`Laravel` `Vue 3` `MySQL`

---

## 🛠 What I Actually Do

- Design and build Laravel REST APIs for multi-role applications
- Implement authentication/authorization systems, including OTP flows and Sanctum-based API auth
- Integrate external payment providers (WaafiPay, Somtel/eDahab) and handle real-world failure modes — timeouts, duplicate callbacks, currency rounding
- Build ticket/order processing systems with QR-code generation and verification
- Design background job and notification pipelines that survive production hosting constraints
- Debug live production issues directly on Linux servers (PHP-FPM, Nginx/Apache configs, queue workers)
- Build Vue 3 and Blade/jQuery frontends and wire them to backend APIs

---

## 🎯 Current Direction

Alongside full-stack development, I'm actively building toward **cybersecurity** — currently deepening my understanding of application security, authentication hardening, and secure API design. This isn't a claimed specialization yet, just a direction I'm deliberately growing into through my ongoing backend and infrastructure work.

---

## 🧰 Tech Stack

**Backend**
![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat&logo=php&logoColor=white)
![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=flat&logo=laravel&logoColor=white)
![REST APIs](https://img.shields.io/badge/REST_APIs-005571?style=flat)
![Sanctum](https://img.shields.io/badge/Sanctum-FF2D20?style=flat&logo=laravel&logoColor=white)

**Frontend**
![Vue.js](https://img.shields.io/badge/Vue.js-4FC08D?style=flat&logo=vuedotjs&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Blade](https://img.shields.io/badge/Blade-FF2D20?style=flat&logo=laravel&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=flat&logo=bootstrap&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)

**Database**
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)
![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat&logo=mariadb&logoColor=white)
![Eloquent ORM](https://img.shields.io/badge/Eloquent_ORM-FF2D20?style=flat&logo=laravel&logoColor=white)

**Tools**
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)
![Composer](https://img.shields.io/badge/Composer-885630?style=flat&logo=composer&logoColor=white)
![NPM](https://img.shields.io/badge/NPM-CB3837?style=flat&logo=npm&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=flat&logo=postman&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat&logo=vite&logoColor=white)

**Infrastructure**
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat&logo=nginx&logoColor=white)
![Apache](https://img.shields.io/badge/Apache-D22128?style=flat&logo=apache&logoColor=white)

**Integrations**
`WaafiPay` `Somtel / eDahab` `Google Maps & Places API` `WhatsApp Business API` `QR Code Systems` `Sumsub KYC`

---

## 📊 GitHub Statistics

<p align="center">
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=muhammaddanial135&show_icons=true&theme=default&hide_border=true" />
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=muhammaddanial135&layout=compact&hide_border=true" />
</p>
<p align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=muhammaddanial135&hide_border=true" />
</p>

> Replace `muhammaddanial135` with your actual GitHub handle for these to render — stats pull live from GitHub, nothing here is fabricated.

---

## 📁 Repositories

**⭐ Featured**
`eventos` (or private/client repo) · `fastwheel-pk` · `ethicalfreelance` · `heybatman`

**🔧 Backend / Laravel**
`buynsell` · `atx-classic-cars` · `clinicos-reports` · `securitychecked-kyc`

**🎨 Frontend**
`[Vue 3 marketplace listing forms repo]`

**🧪 Experiments / Other**
`[client site repos — roofing sites, small integrations, etc.]`

> Repository names above are placeholders — swap in your actual repo slugs so links resolve correctly.

---

<p align="center">
  📫 Reach me at <strong>danialrasool135@gmail.com</strong> — open to full-stack roles, freelance backend/API work, and collaboration on production Laravel/Vue systems.
</p>
