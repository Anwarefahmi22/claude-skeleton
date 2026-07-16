# مثال: تقنيات Masar API

> هذا مثال حقيقي - عدّله حسب مشروعك

## التقنيات الأساسية

### Backend
- **Language**: Python 3.11+
- **Framework**: FastAPI 0.104+
- **ORM**: SQLAlchemy 2.0
- **Database**: PostgreSQL 15 (production) / SQLite (development)

### Authentication
- **JWT**: python-jose
- **Password**: passlib[bcrypt]

### API Documentation
- **Swagger**: auto-generated via FastAPI
- **ReDoc**: available at /docs

### Testing
- **Framework**: pytest
- **Coverage**: pytest-cov
- **Fixtures**: pytest fixtures

## أدوات التطوير

| الأداة | الإصدار | الغرض |
|--------|---------|-------|
| black | 23.x | تنسيق الكود |
| isort | 5.x | ترتيب الواردات |
| flake8 | 6.x | فحص الكود |
| mypy | 1.x | فحص الأنواع |

## بيئات التشغيل

| البيئة | Database | Port |
|--------|----------|------|
| Development | SQLite | 8000 |
| Staging | PostgreSQL | 8001 |
| Production | PostgreSQL | 8000 |

## متغيرات البيئة المطلوبة

```bash
DATABASE_URL=postgresql://user:pass@localhost:5432/masar
SECRET_KEY=your-secret-key-here
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30
```
