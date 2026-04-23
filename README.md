# Enterprise-Scale CRM & Client Intelligence Platform
**Developed for Ascendant Global INC (AGI Group) — Software Development Internship**

A high-performance, real-time CRM prototype designed to centralize business operations, manage high-value lead lifecycles, and automate financial document generation.

## 🚀 Technical Architecture
*   **Backend:** NestJS (Node.js) with TypeScript
*   **Database:** PostgreSQL with Prisma ORM
*   **Frontend:** Ionic Framework + Angular 18 + Tailwind CSS
*   **Real-time:** Socket.io (Pulse Gateway)
*   **Automation:** Puppeteer (PDF Engine) & EventEmitter2 (Internal Workflows)

## 🛠 Key Engineering Challenges Solved

### 1. Atomic Lead Conversion Engine
Developed a complex **Prisma Transaction** system that converts a `Lead` into three separate entities (`Account`, `Contact`, and `Deal`) in a single database pulse. 
*   Implemented logic to link legacy activity history (notes, tasks, bookings) to the new entities to ensure zero data loss during conversion.

### 2. Real-time "Pulse" Gateway
Integrated **Socket.io** to create a live notification stream.
*   The system intercepts inbound booking requests from the public portal and broadcasts them immediately to the Admin dashboard without requiring a page refresh.
*   Implemented **JWT-based WebSocket guards** to ensure secure socket connections.

### 3. Automated Financial Transaction Engine
Built a "Quote-to-PDF" pipeline using **Puppeteer**. 
*   Users can build quotes using a searchable product inventory.
*   The system snapshots the `listPrice` at the moment of creation to prevent historical financial data from changing if product prices are updated later.

### 4. BI Dashboard & Weighted Forecasting
Engineered a Business Intelligence layer that calculates:
*   **Weighted Revenue Forecast:** `Amount * Probability` based on the Sales Pipeline stage.
*   **Win-Rate Metrics:** Real-time calculation of Closed-Won vs. Closed-Lost ratios.

## 🔒 Security & Optimization
*   **RBAC (Role-Based Access Control):** Implemented custom decorators and guards in NestJS to restrict access between `Admin`, `Manager`, and `Standard` roles.
*   **Global Search Engine:** Built a high-speed fuzzy search that queries across Leads, Contacts, Deals, and Products using PostgreSQL `insensitive` mode.

---
*Note: Source code is private property of AGI Group. I am authorized to demonstrate the architecture and UI/UX flow during technical interviews.*
