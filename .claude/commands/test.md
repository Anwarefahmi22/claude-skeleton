# كتابة الاختبارات

## الاستخدام
```
اكتب اختبارات لـ [الملف/الدالة]
المتوقع:
- [السلوك1]
- [السلوك2]

القيود:
- استخدم [pytest/jest/...]
- التزم بالهيكل في [tests/]
- غطِّ الحالات:
  - ✅ Happy Path
  - ⚠️ Edge Cases
  - ❌ Error Cases
```

## قالب اختبار

```python
# Python / pytest
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
        
    def test_[description]_failure(self):
        """اختبار: [وصف الفشل]"""
        with pytest.raises([ExpectedException]):
            [function](invalid_input)
```

```javascript
// JavaScript / Jest
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
