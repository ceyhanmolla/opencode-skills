# opencode-skills

A collection of custom OpenCode skills for advanced development workflows.

This repository serves as documentation for a set of powerful OpenCode skills that enhance the AI coding assistant's capabilities. These skills provide specialized guidance for frontend design, security auditing, and web page development.

## Skills Overview

### 1. Design Taste Frontend

**Skill name:** `design-taste-frontend`

**Description:** Senior UI/UX Engineer. Architect digital interfaces overriding default LLM biases. Enforces metric-based rules, strict component architecture, CSS hardware acceleration, and balanced design engineering.

**Key Capabilities:**
- Configurable design dials (DESIGN_VARIANCE, MOTION_INTENSITY, VISUAL_DENSITY)
- Deterministic typography with premium font stacks (Geist, Outfit, Cabinet Grotesk, Satoshi)
- Color calibration limiting to 1 accent color (<80% saturation)
- Advanced motion patterns (magnetic buttons, staggering, layout transitions)
- Perpetual micro-interactions using Framer Motion
- Liquid Glass refraction effect for premium UI
- Bento 2.0 architecture with 5 specific card archetypes
- Strict performance guardrails (hardware acceleration, z-index restraint)
- Anti-slop patterns to avoid generic AI designs

**Use when:** Building premium interfaces, modern SaaS dashboards, or any project requiring high-end, non-generic design.

---

### 2. Security Audit

**Skill name:** `security-audit`

**Description:** Security audit and vulnerability assessment skill for code review. Use when performing security audits, identifying vulnerabilities, checking for hardcoded secrets, reviewing authentication/authorization logic, analyzing dependency vulnerabilities, or providing security hardening recommendations. Covers OWASP Top 10, secret detection, credential auditing, and security best practices.

**Key Capabilities:**
- Systematic vulnerability documentation with exploit scenarios
- Severity classification (Critical, High, Medium, Low)
- Secret & credential audit (API keys, database credentials, encryption keys)
- Security hardening checklist (rate limiting, CSP, CORS, HTTPS, etc.)
- Dependency & supply chain vulnerability scanning
- Coverage of injection vulnerabilities, XSS, CSRF, broken authentication/authorization
- Common vulnerability pattern examples with secure fixes

**Use when:** Performing security code reviews, assessing application security posture, or needing security hardening guidance.

---

### 3. Web Page Design

**Skill name:** `web-page-design`

**Description:** A comprehensive skill for creating modern, high-performance web pages with video backgrounds, glassmorphic effects, and cinematic animations.

**Key Capabilities:**
- Video background system with seamless fade loops and HLS streaming (`hls.js`)
- Liquid Glass CSS implementation (backdrop-blur with inner border refraction)
- HSL-based color theming system
- Animation patterns (GSAP for scrolltelling, Framer Motion for UI)
- Component blueprints: Navbar, Hero, CardGrid, Marquee, etc.
- Performance optimization (video playback, animation best practices)
- Responsive design patterns and typography scales
- Project structure guidelines (React + TypeScript + Vite + Tailwind CSS v4)

**Use when:** Building modern landing pages, portfolios, or marketing sites with cinematic visual effects.

## Installation & Usage

These skills are designed for use with **OpenCode**. To install:

1. Place each skill directory in your OpenCode skills folder:
   ```
   ~/.config/opencode/skills/
   ```

2. Restart OpenCode or reload skills.

3. Skills will activate automatically based on your task description. You can also explicitly request a skill: "Use the [skill-name] skill to help me..."

Each skill's full specification is contained in its `SKILL.md` file.

## Repository Structure

This repository contains:
- `README.md` - This documentation file
- (Skill implementation files are located in `~/.config/opencode/skills/`)

## License

MIT. Use freely.
