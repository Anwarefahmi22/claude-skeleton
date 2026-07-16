# أنماط البرمجة المعتمدة - عدّله حسب مشروعك

## نمط التصميم

- [ ] MVC (Model-View-Controller)
- [ ] Repository Pattern
- [ ] Service Layer
- [ ] Clean Architecture
- [ ] hexagonal / Ports & Adapters

## أنماط معتمدة في المشروع

### 1. Error Handling
```python
# Python
try:
    result = do_something()
except SpecificError as e:
    logger.error(f"خطأ محدد: {e}")
    raise CustomException("رسالة واضحة") from e
```

### 2. Async/Await
```javascript
// JavaScript
async function fetchData() {
  try {
    const data = await api.get('/endpoint');
    return data;
  } catch (error) {
    console.error('فشل في جلب البيانات:', error);
    throw error;
  }
}
```

### 3. Dependency Injection
```typescript
// TypeScript
class Service {
  constructor(private repository: IRepository) {}
  
  async findById(id: string) {
    return this.repository.findOne({ id });
  }
}
```

## قواعد الـ Code Review

1. لا أكثر من 400 سطر لكل PR
2. كل دالة/فنكشن لها مسؤولية واحدة
3. استخدم أسماء واضحة ومعبرة
4. اختبارات تغطي الـ Happy Path والـ Edge Cases
