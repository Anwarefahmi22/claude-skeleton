# أوامر سريعة: كتابة الاختبارات

## الاستخدام

```
اكتب اختبارات لـ [الدالة/الملف]
القيود:
- استخدم [pytest/jest/...]
- غطِّ الحالات:
  - ✅ Happy Path
  - ⚠️ Edge Cases
  - ❌ Error Cases
```

## قالب الاختبار (Python/pytest)

```python
import pytest
from [module] import [function]

class Test[FunctionName]:
    """اختبارات لـ [FunctionName]"""
    
    def test_[description]_success(self):
        """اختبار: [وصف النجاح]"""
        # Arrange
        input_data = [...]
        
        # Act
        result = [function](input_data)
        
        # Assert
        assert result == expected
        
    def test_[description]_error(self):
        """اختبار: [وصف الخطأ]"""
        with pytest.raises([ExpectedException]):
            [function](invalid_input)
```

## قالب الاختبار (JavaScript/Jest)

```javascript
describe('[FunctionName]', () => {
  it('should [expected behavior]', () => {
    const result = functionName(input);
    expect(result).toBe(expected);
  });
  
  it('should throw [Error] for [invalid input]', () => {
    expect(() => functionName(invalid)).toThrow([Error]);
  });
});
```
