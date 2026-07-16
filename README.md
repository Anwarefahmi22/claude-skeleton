# Claude Skeleton

> قالب هيكل أساسي (Skeleton) لتحسين استخدام Claude AI في مشاريعك البرمجية

## ✨ المميزات

- 📁 **هيكل منظم** لمجلد `.claude/` مع سياق جاهز
- 🎯 **أوامر سريعة** لمحاولات متكررة
- 📝 **قوالب Prompts** لمهام شائعة
- 💰 **تقليل استهلاك التوكن** بنسبة تصل إلى 75%

## 🚀 البدء السريع

### استنساخ للمشروع الجديد

```bash
git clone https://github.com/YOUR_USERNAME/claude-skeleton.git my-project
cd my-project
rm -rf .git
git init
```

### إضافته لمشروع موجود

```bash
# في مجلد مشروعك
cp -r claude-skeleton/.claude ./
cp claude-skeleton/CLAUDE.md ./
```

## 📂 الهيكل

```
.claude/
├── commands/          # أوامر سريعة
│   ├── analyze.md     # تحليل الكود
│   ├── review.md      # مراجعة الكود
│   └── test.md        # كتابة اختبارات
├── context/           # السياق المسبق
│   ├── project.md     # معلومات المشروع
│   ├── stack.md       # التقنيات
│   └── patterns.md    # أنماط البرمجة
└── templates/         # قوالب Prompts
    ├── feature.md     # إضافة ميزة
    ├── bugfix.md      # إصلاح خطأ
    └── refactor.md    # إعادة هيكلة
```

## 📖 القراءة

اقرأ [CLAUDE.md](./CLAUDE.md) للحصول على دليل شامل.

## 🤝 المساهمة

المساهمات مرحب بها! افتح Issue أو Pull Request.

## 📄 الترخيص

MIT License
