# مثال: مشروع Masar API

> هذا مثال حقيقي - عدّله حسب مشروعك

## معلومات المشروع

- **الاسم**: Masar API
- **الوصف**: REST API لنظام إدارة العقارات
- **الإصدار**: 1.0.0

## لغة البرمجة الرئيسية

- اللغة: Python 3.11+
- Framework: FastAPI
- Database: PostgreSQL + SQLite

## هيكل المشروع

```
masar-api/
├── app/
│   ├── __init__.py
│   ├── main.py              # FastAPI app
│   ├── api/
│   │   ├── __init__.py
│   │   ├── v1/
│   │   │   ├── endpoints/    # API endpoints
│   │   │   └── router.py
│   ├── core/
│   │   ├── config.py         # Settings
│   │   ├── security.py       # Auth
│   │   └── database.py
│   ├── models/               # SQLAlchemy models
│   ├── schemas/              # Pydantic schemas
│   └── services/             # Business logic
├── tests/
│   ├── unit/
│   ├── integration/
│   └── fixtures/
├── alembic/                  # Migrations
├── docs/
├── scripts/
├── requirements.txt
└── README.md
```

## قواعد المساهمة

1. اتبع نمط الكود الموجود في `app/models/` و `app/api/`
2. أضف اختبارات لكل ميزة جديدة في `tests/`
3. التزم بـ Conventional Commits
4. اكتب docstrings باللغة الإنجليزية

## معايير الكود

- طول السطر: 100 حرف كحد أقصى
- المسافات: 4 مسافات ( spaces)
- أسماء الدوال والمتغيرات: snake_case
- أسماء الكلاسات: PascalCase
- الثوابت: UPPER_SNAKE_CASE
- التعليقات: docstrings للنماذج والدوال العامة

## هيكل API

- Base URL: `/api/v1`
- Auth: JWT Bearer Token
- Response Format: JSON
- Pagination: Page-based
