# DSTEP Enterprise v0.1.0-alpha

**Direct Supply and Transaction Electronic Platform**

A secure, modular B2B electronic platform designed to facilitate international commerce between enterprises.

## Project Status

- **Version**: v0.1.0-alpha
- **Phase**: Sprint 1 - Foundation
- **Environment**: Development
- **Domain**: www.dstepglobal.com

## Quick Start

### Prerequisites

- Docker & Docker Compose
- Git
- Ubuntu 20.04+ or Linux Mint

### Installation

```bash
git clone https://github.com/Alpha-Pro1/dstep-enterprise.git
cd dstep-enterprise
cp .env.example .env
./install.sh
```

### Access Points

Once running, access the platform at:

- **Business Portal**: http://localhost:3000
- **Control Center**: http://localhost:3001
- **API**: http://localhost:8000/api/
- **Django Admin**: http://localhost:8000/admin/
- **Swagger**: http://localhost:8000/api/schema/swagger/
- **Health Check**: http://localhost:8000/api/health/

### Default Credentials

```
Email: superadmin@dstepglobal.com
Password: SuperAdmin123!@#
```

## Project Structure

```
dstep-enterprise/
├── backend/              # Django 5 REST API
├── frontend-business/    # React Business Portal
├── frontend-control/     # React Control Center
├── infrastructure/       # Docker & Nginx configs
├── docs/                 # Documentation
├── docker-compose.yml    # Development environment
└── install.sh           # Installation script
```

## Architecture

### Backend Stack

- **Python 3.11+**
- **Django 5.0**
- **Django REST Framework**
- **PostgreSQL 15**
- **Redis 7**
- **Celery 5**
- **JWT Authentication**

### Frontend Stack

- **React 18**
- **TypeScript**
- **Vite**
- **Material UI**
- **TanStack Query**

### Infrastructure

- **Docker & Docker Compose**
- **Nginx Reverse Proxy**
- **GitHub Actions CI/CD**
- **Ubuntu Server**

## Roles & Permissions

The platform manages the following roles:

```
USER
COMPANY_MEMBER
COMPANY_MANAGER
COMPANY_ADMIN
COMPANY_OWNER
SUPPORT_AGENT
COMPLIANCE_ANALYST
PLATFORM_ADMIN
SUPER_ADMIN
```

### Access Rules

| Role | Business Portal | Control Center | Django Admin | Swagger |
|------|-----------------|-----------------|-------------|---------|
| USER | ✅ | ❌ | ❌ | ❌ |
| COMPANY_MEMBER | ✅ | ❌ | ❌ | ❌ |
| COMPANY_OWNER | ✅ | ❌ | ❌ | ❌ |
| PLATFORM_ADMIN | ✅ | ✅ | ❌ | ❌ |
| SUPER_ADMIN | ✅ | ✅ | ✅ | ✅ |

## Modules (Sprint 1)

### Foundation

- ✅ Authentication & Authorization
- ✅ User Management
- ✅ Company Management
- ✅ RBAC (Role-Based Access Control)
- ✅ Business Portal
- ✅ Control Center
- ✅ API Documentation
- ✅ Health Monitoring

## Commands

### Start Development

```bash
docker-compose up -d
```

### Run Migrations

```bash
docker-compose exec backend python manage.py migrate
```

### Create Superuser

```bash
docker-compose exec backend python manage.py createsuperuser
```

### Stop Services

```bash
docker-compose down
```

### View Logs

```bash
docker-compose logs -f backend
docker-compose logs -f frontend-business
docker-compose logs -f frontend-control
```

### Run Tests

Backend:
```bash
docker-compose exec backend pytest
```

Frontend:
```bash
docker-compose exec frontend-business npm test
docker-compose exec frontend-control npm test
```

## Documentation

- [Installation Guide](./docs/INSTALLATION.md)
- [API Documentation](./docs/API.md)
- [Architecture](./docs/ARCHITECTURE.md)
- [Development Guide](./docs/DEVELOPMENT.md)
- [Deployment Guide](./docs/DEPLOYMENT.md)

## Sprint 1 Checklist

- [x] Project structure initialized
- [x] Docker & Docker Compose configured
- [x] Django backend setup
- [x] React frontends setup
- [x] Authentication (JWT)
- [x] User & Company models
- [x] RBAC system
- [x] Business Portal interface
- [x] Control Center interface
- [x] Health checks
- [x] Tests configured
- [x] CI/CD workflows
- [ ] Initial deployment

## Environment Configuration

See `.env.example` for all available configuration options.

### Key Variables

```
DEBUG=True
SECRET_KEY=your-secret-key-here
ALLOWED_HOSTS=localhost,127.0.0.1
DATABASE_URL=postgresql://user:password@db:5432/dstep
REDIS_URL=redis://redis:6379/0
```

## Security

⚠️ **Important**

- Never commit `.env` file to repository
- Never expose API keys or secrets
- Always use HTTPS in production
- Enable CORS only for trusted domains
- Validate and sanitize all inputs
- Use JWT tokens with appropriate expiration

## License

Proprietary - DSTEP Global, Inc.

## Support

For issues, feature requests, or documentation updates, please contact the development team.

## Roadmap

### Sprint 2: Catalogue & Marketplace
- Product catalog
- Service listings
- Search & filters
- Categories & subcategories

### Sprint 3: RFQ & Offers
- Request for Quote workflow
- Offer management
- Negotiation tools
- Expiry management

### Sprint 4: Transactions & Contracts
- Transaction lifecycle
- Contract management
- Document handling
- Status tracking

### Sprint 5: Wallet & Financial Rules
- Internal wallet system
- Commission management
- Fee structures
- Financial reporting

### Sprint 6: Compliance & Trust
- KYB/KYC workflows
- Document verification
- Enterprise Passport
- Transaction Passport

### Sprint 7: Communication & Notifications
- Messaging system
- Email notifications
- Real-time notifications
- WebSocket support

### Sprint 8: Logistics & Reporting
- Shipment tracking
- Carrier management
- Reporting dashboards
- Export capabilities

---

**Version**: v0.1.0-alpha  
**Last Updated**: 2026-07-23  
**Status**: In Development
