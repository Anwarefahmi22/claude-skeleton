# قالب: إعادة هيكلة

## قبل الطلب

1. حدد بالضبط ما الذي يحتاج إعادة هيكلة
2. فهل الهدف (أداء؟ صيانة؟ قراءة؟)
3. راجع الأنماط المعتمدة في المشروع

## القالب

```
أعد هيكلة: [ما الذي ستُعاد هيكلته]

## الهدف
- [ ] تحسين الأداء
- [ ] تحسين القراءة
- [ ] تقليل التكرار (DRY)
- [ ] تطبيق نمط تصميم
- [ ] تقليل التعقيد

## الكود الحالي
الملف: [path/to/file]

```[language]
[الكود الحالي]
```

## المشاكل المحددة
1. [مشكلة 1]
2. [مشكلة 2]

## الهيكل/النمط المطلوب
[وصف ما تريده بالضبط]

## القيود
- حافظ على الوظيفة الحالية
- لا تغير الـ API/الواجهة
- اجعل التغييرات تدريجية
- أضف اختبارات

## معايير النجاح
- جميع الاختبارات تمر
- الأداء أفضل بـ [نسبة]%
- الكود أوضح وأسهل في القراءة
```

## مثال

```
أعد هيكلة: validate_user_data function

## الهدف
- [x] تحسين القراءة
- [x] تقليل التكرار
- [ ] تطبيق نمط تصميم

## الكود الحالي
الملف: src/validators/user.py

```python
def validate_user_data(data):
    errors = []
    if 'name' not in data:
        errors.append("Name required")
    elif len(data['name']) < 2:
        errors.append("Name too short")
    elif len(data['name']) > 50:
        errors.append("Name too long")
    
    if 'email' not in data:
        errors.append("Email required")
    elif '@' not in data['email']:
        errors.append("Invalid email")
    
    if 'age' in data:
        if not isinstance(data['age'], int):
            errors.append("Age must be number")
        elif data['age'] < 0 or data['age'] > 150:
            errors.append("Invalid age")
    
    return errors
```

## المشاكل المحددة
1. دالة طويلة مع منطق مكرر
2. كل validation hard-coded
3. صعبة في الاختبار والصيانة

## الهيكل المطلوب
- دوال صغيرة منفصلة لكل حقل
- استخدام decorator أو class-based validator
- رسائل خطأ موحدة
```
