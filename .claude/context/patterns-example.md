# مثال: أنماط البرمجة في Masar API

> هذا مثال حقيقي - عدّله حسب مشروعك

## نمط التصميم

**Clean Architecture** مع:
- API Layer (endpoints)
- Service Layer (business logic)
- Repository Layer (data access)
- Model Layer (database)

## أنماط معتمدة

### 1. Repository Pattern
```python
# app/repositories/base.py
class BaseRepository:
    def __init__(self, model, db: Session):
        self.model = model
        self.db = db
    
    def get(self, id: int) -> Optional[Model]:
        return self.db.query(self.model).filter(self.model.id == id).first()
    
    def get_all(self, skip: int = 0, limit: int = 100) -> List[Model]:
        return self.db.query(self.model).offset(skip).limit(limit).all()
```

### 2. Service Layer
```python
# app/services/base.py
class BaseService:
    def __init__(self, repository: BaseRepository):
        self.repository = repository
    
    def get(self, id: int) -> Optional[Model]:
        return self.repository.get(id)
```

### 3. Schema Validation
```python
# app/schemas/user.py
from pydantic import BaseModel, EmailStr

class UserBase(BaseModel):
    email: EmailStr
    name: str

class UserCreate(UserBase):
    password: str

class UserResponse(UserBase):
    id: int
    is_active: bool
    
    class Config:
        from_attributes = True
```

### 4. Error Handling
```python
# app/core/exceptions.py
class NotFoundException(Exception):
    pass

class ValidationException(Exception):
    pass
```

## قواعد الـ API

### Response Format
```python
{
    "data": {...},
    "message": "Success",
    "status": 200
}
```

### Error Format
```python
{
    "detail": "Error description",
    "status": 400
}
```

## قواعد الاختبار

- اسماء الدوال: `test_<functionality>_<expected_result>`
- لكل endpoint: اختبار success + error cases
- استخدم fixtures للمعطيات المتكررة
