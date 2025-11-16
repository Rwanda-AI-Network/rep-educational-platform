
<artifact identifier="rep-readme" type="text/markdown" title="Rwanda Education Platform - README.md">
# Rwanda Education Platform (REP)

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/python-3.11+-blue.svg)
![Next.js](https://img.shields.io/badge/next.js-14+-black.svg)
![Django](https://img.shields.io/badge/django-5.0+-green.svg)

**An AI-enabled digital learning platform transforming education across Rwanda**

The Rwanda Education Platform (REP) is an open-source initiative designed to democratize access to high-quality educational resources throughout Rwanda. By leveraging AI and official national curricula, REP provides students with intelligent tutoring and teachers with rapid content generation tools—all grounded in Ministry-approved materials.

---

## 📚 Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Architecture](#architecture)
- [Getting Started](#getting-started)
- [Documentation](#documentation)
- [Contributing](#contributing)
- [Roadmap](#roadmap)
- [Community](#community)
- [License](#license)

---

## Overview

### Mission

To provide equitable, AI-powered learning support to all Rwandan students and educators, starting with a focused MVP and scaling to a comprehensive national education platform.

### Problem Statement

Many Rwandan students—especially in rural areas—lack access to:
- Quality after-school academic support
- Clear explanations of complex concepts
- Practice materials aligned with national exams

Teachers face:
- Time-consuming quiz and test preparation
- Limited resources for explaining difficult topics
- Minimal access to structured past exam papers

### Solution

REP bridges these gaps through:
- **Student AI Assistant**: Provides step-by-step explanations, practice questions, and exam preparation based on official REB/NESA materials
- **Teacher AI Assistant**: Generates classroom-ready quizzes, tests, and teaching notes in minutes
- **Official Content Foundation**: All responses cite authoritative national educational resources

---

## Key Features

### MVP (Current Focus)

- ✅ **English-only support** for rapid deployment
- ✅ **Role-based access** (Students & Teachers)
- ✅ **AI-powered explanations** with source citations
- ✅ **Past exam question library** indexed by subject/level
- ✅ **Teacher quiz generation** with answer keys
- ✅ **Mobile-responsive web interface**

### Post-MVP Vision

- 🔜 **Multilingual support** (Kinyarwanda, French)
- 🔜 **National AI model** trained on local datasets
- 🔜 **Expanded roles** (Parents, Admins, Ministry Officials)
- 🔜 **Personalized learning paths** with progress tracking
- 🔜 **Offline access** for low-connectivity areas
- 🔜 **Analytics dashboards** for policy insights

See our [complete roadmap](docs/Post-MVP-Vision.md) for details.

---

## Architecture

REP is built as a modern, scalable monolithic application with clear separation of concerns.
```
┌─────────────────────────────────────────────────────────┐
│                     Frontend Layer                      │
│  Next.js 14+ (React, TypeScript, Tailwind CSS)          │
│  Mobile-first responsive design                         │
└─────────────────────┬───────────────────────────────────┘
                      │ REST API
┌─────────────────────▼───────────────────────────────────┐
│                    Backend Layer                        │
│  Django 5.0+ / Django REST Framework                    │
│  - Authentication & Authorization                       │
│  - Content Management API                               │
│  - AI Assistant Orchestration                           │
└─────────────────────┬───────────────────────────────────┘
                      │
        ┌─────────────┼─────────────┐
        │             │             │
┌───────▼──────┐ ┌───▼────┐ ┌─────▼──────────┐
│ PostgreSQL   │ │ Redis  │ │ AI Service     │
│ (Primary DB) │ │ Cache  │ │ (External MVP) │
└──────────────┘ └────────┘ └────────────────┘
```
## Key Components:

- Frontend: Next.js with server-side rendering,  optimized for low-bandwidth
- Backend: Django REST API with JWT authentication
- Database: PostgreSQL for relational data (users, content metadata)
- Cache: Redis for frequently accessed curriculum content
- AI Layer: External API integration (MVP), migrating to in-house model (Post-MVP)

→ [Full Architecture Documentation](docs/Architecture.md)


## Getting Started
### Prerequisites

- Python 3.11+
- Node.js 18+
- PostgreSQL 14+
- Redis 7+
- Git

## Quick Installation

```bash 
# Clone the repository
git clone https://github.com/rwanda-education/rep-platform.git
cd rep-platform

# Backend setup
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser

# Frontend setup
cd ../frontend
npm install
npm run dev

# Start backend (separate terminal)
cd backend
python manage.py runserver

# Access the application
# Frontend: http://localhost:3000
# Backend Admin: http://localhost:8000/admin
```
→ [Detailed Setup Guide](docs/Setup-and-Installation.md)

## Documentation
Our documentation is organized for easy navigation:
### For Contributors

- [Contributing Guide](docs/Contributing.md) - Start here!
- [Setup & Installation](docs/Setup-and-Installation.md)
- [Architecture Overview](docs/Architecture.md)
- [Backend Guide](docs/Backend.md)
- [Frontend Guide](docs/Frontend.md)

### For Project Managers

- [MVP Specification](docs/MVP.md)
- [Post-MVP Vision](docs/Post-MVP-Vision.md)
- [User Personas](docs/Personas.md)

### Technical Deep Dives

- [AI Model Strategy](docs/AI-Model-Strategy.md)
- [Content Intake Pipeline](docs/Content-Intake.md)


## Contributing
We welcome contributions from developers, educators, designers, and education policy experts!
### Quick Start for Contributors

1. **Fork** the repository
2. **Create a feature branch**: `git checkout -b feature/amazing-feature`
3. **Make your changes** following our [code style guide](docs/Contributing.md#code-style)
4. **Write tests** for new functionality
5. **Commit** with clear messages: git commit -m 'feat: add amazing feature'
6. **Push** to your fork: git push origin feature/amazing-feature
7. **Open a Pull Request** with a clear description

#### Contribution Areas

🐛 **Bug fixes** and performance improvements \
📝 **Documentation** enhancements \
🌍 **Localization** (Kinyarwanda, French translations) \
🎨 **UI/UX** design improvements  
🧪 **Testing** and quality assurance \
📊 **Content curation** (educational materials)

→ [Full Contributing Guide](docs/Contributing.md)

### Roadmap
#### Phase 1: MVP (Current - Q2 2025)

- Core authentication system
- Student AI assistant (English)
- Teacher quiz generator
- Public beta testing in 3 pilot schools
- Performance optimization for low-bandwidth

#### Phase 2: Expansion (Q3-Q4 2025)

- Kinyarwanda language support
- Mobile native apps (iOS/Android)
- Teacher assignment workflows
- Student progress tracking

#### Phase 3: National Scale (2026)

- National AI model deployment
- Ministry analytics dashboard
- Offline-first architecture
- Integration with national education databases

→ [Detailed Roadmap](docs/Post-MVP-Vision.md)

### Community
👉 **[Get Involved](https://github.com/orgs/Rwanda-AI-Network/discussions)**  
Join discussions, propose ideas, and collaborate with the REP community.


- 💬 **Discussions**: [GitHub Discussions](https://github.com/orgs/Rwanda-AI-Network/discussions)
- 🐛 **Bug Reports**: [Issue Tracker](https://github.com/orgs/Rwanda-AI-Network/discussions)
- 📧 **Email**: rwanda.ai.network@gmail.com 

**Recognition**
We believe in recognizing our contributors:

- All contributors are listed in [CONTRIBUTORS.md](CONTRIBUTORS.md)
- Significant contributions are highlighted in release notes
- Outstanding contributors may be invited to join the core team


## License
This project is licensed under the MIT [License](LICENSE) - see the LICENSE file for details.
#### Why Open Source?
REP is open source to:

Ensure **transparency** in educational AI systems
Enable **collaboration** with global education technology experts
Facilitate **customization** for other national contexts
Promote **innovation** in African edtech


## Acknowledgments

**Rwanda Education Board (REB)** for curriculum materials
**National Examinations and School Inspection Authority (NESA)** for past exam papers
**Ministry of Education** for project support and guidance
**All contributors** and **pilot school partners**


## Project Status  
#### 🟢 **Active Development** - MVP in progress
Current version: `0.1.0-alpha` \
Target MVP release: Q2 2025

---

<p align="center">
  <strong>Built with ❤️ for Rwandan learners</strong>
</p>
<p align="center">
  <a href="docs/Contributing.md">Contribute</a> •
  <a href="docs/Setup-and-Installation.md">Get Started</a> •
  <a href="docs/Architecture.md">Architecture</a>
</p>
</artifact>