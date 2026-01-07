# 🌐 BizSafer Infrastructure  
## Production-Grade Edge Delivery (Frontend)

This repository serves as a **credibility anchor**, documenting the production-grade frontend delivery architecture used for the **BizSafer** platform.

This is a **functional blueprint**, designed to demonstrate industrial-grade **performance optimization, edge security, and automated deployment** for modern React applications.

The frontend is architected to provide a seamless user experience while maintaining strong security controls at the edge.

---

## 🏗️ Repository Structure (Frontend-Focused)

```text
├── .github/workflows/
│   ├── deploy.yml         # Frontend CI/CD pipeline with health gates
│   └── rollback.yml       # Manual emergency rollback workflow
├── src/                   # React + Vite + Tailwind CSS source
├── public/                # Static assets and configuration
├── nginx/
│     └── frontend.conf  # Nginx config for www.bizsafer.com
├── docker-compose.yml     # Frontend service orchestration
└── README.md              # Delivery & infrastructure documentation
```

---

## 🌐 Network & Edge Architecture

The BizSafer frontend is delivered through a hardened **Nginx reverse proxy** and accelerated by **Cloudflare’s global edge network**.

### Orchestrated Endpoints

- **Frontend Application**  
  https://www.bizsafer.com  
  *React + Vite + Node.js*

- **API Connectivity**  
  Communicates with the BizSafer backend core via:  
  https://panel.bizsafer.com/api/v1/

---

## 🛠️ Technical Stack & Expertise

### Containerization & Delivery
- Docker & Docker Compose
- Multi-stage builds for minimal image size and fast delivery
- Full environment parity between development and production

### CI/CD Automation
- GitHub Actions for automated build, linting, and deployment
- Zero-downtime updates using a blue–green deployment strategy

### Performance & Security
- Optimized Core Web Vitals (LCP, CLS, INP) through advanced asset caching
- Cloudflare WAF rules for DDoS and bot mitigation
- Hardened Nginx with security headers (HSTS, CSP, X-Frame-Options)

---

## 🔄 Reliability & SRE Strategy

**Target Availability:** 99.9%

### Automated Health Gates
Deployments are finalized only after the Nginx layer confirms that frontend containers respond successfully to health probes.

### Dual-Layer Rollback

**Automated Rollback**
- Instant reversion to the last stable UI build if post-deployment checks fail

**Manual Emergency Rollback**
- GitHub Actions `workflow_dispatch`
- Human-led recovery of UI state in under 60 seconds

---

## 🚀 Deployment Workflow

1. **Test & Audit (CI)**
   Automated **Unit Tests**, linting, and dependency vulnerability scanning to ensure code quality.

2. **Build**
   Parallel multi-stage Docker builds using Node.js for optimized static asset generation.

3. **Deploy (CD)**
   SSH-based deployment to production droplets using GitHub Secrets:
   - `PROD_HOST`
   - `PROD_USER`
   - `PROD_SSH_KEY`

4. **Verification**
   Post-deployment UI smoke tests
   Cleanup of legacy containers and assets

---

## 👤 Ownership

**Lead Engineer:** Md. Kamruzzaman  
**Role:** Cloud & DevOps Engineer | SRE  

LinkedIn: https://www.linkedin.com/in/4kamruzzaman

---

## 📌 Project Purpose

- Represents real production standards for frontend delivery
- Serves as a technical showcase of high-performance, secure edge architectures
- Demonstrates reliable, automated frontend operations at scale
- Every automation path follows a strict **production-first** mindset
