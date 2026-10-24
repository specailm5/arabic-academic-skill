# مهارة الكتابة الأكاديمية
### (Arabic Academic Writing Skill)

<p align="center">
  <a href="https://github.com/specailm5/arabic-academic-skill/blob/master/LICENSE"><img alt="License" src="https://img.shields.io/github/license/specailm5/arabic-academic-skill?style=flat-square"></a>
  <a href="https://github.com/specailm5/arabic-academic-skill/commits/master"><img alt="Last commit" src="https://img.shields.io/github/last-commit/specailm5/arabic-academic-skill?style=flat-square"></a>
  <a href="https://specailm5.github.io/arabic-academic-skill/"><img alt="Docs" src="https://img.shields.io/badge/docs-live-brightgreen?style=flat-square"></a>
  <img alt="Agent Skills" src="https://img.shields.io/badge/Agent%20Skills-compatible-5B21B6?style=flat-square">
</p>

**Arabic academic writing skill for AI agents** — turns a topic into a researchable question and thesis, builds the plan and IMRaD structure, documents sources, and diagnoses the draft against quality criteria: `«أثر التعليم الإلكتروني»` ← `«هل يختلف الأثر باختلاف التنظيم الذاتي؟»`. Works with Claude Code, Codex, Antigravity and VS Code agent harnesses.

🔗 **الموقع المرجعي (التصميم والبنية والأسلوب والنماذج): [specailm5.github.io/arabic-academic-skill](https://specailm5.github.io/arabic-academic-skill/)**

> مهارة برمجية ولغوية لنماذج الذكاء الاصطناعي والمحررات الذكية (Codex، Claude Code، Antigravity IDE، VS Code Agent Harness) لبناء البحث العربي وتحريره وتقييمه، استناداً إلى **«الكتابة الأكاديمية»** لمحمود جلال الدين سليمان، و**«أصول البحث العلمي ومناهجه»** لوجيه محجوب، و**«أصول كتابة البحث العلمي ومناهجه»** ليوسف المرعشلي.

---

## 📖 ما هي المهارة؟

أكثر ما يُسمّى بحثاً هو موضوع مُعاد ترتيبه: لا سؤال، ولا فجوة، ولا منهج، ولا توثيق. والنتيجة فقرات أكاديمية الشكل، خالية من الحجة.

تُمكِّنُ هذه المهارةُ الوكيلَ الذكيَّ من:

1. **تحويل الموضوع إلى سؤال** قابل للبحث، ثم إلى أطروحة قابلة للدفاع.
2. **تحديد الفجوة** التي يملؤها البحث، وصياغتها في ثلاث جمل.
3. **بناء الخطة والبنية:** مقدمة، منهج، نتائج، مناقشة، خاتمة، فهارس.
4. **ضبط الأسلوب الأكاديمي:** الموضوعية، الدقة، التحوط، الفقرة.
5. **التوثيق والأمانة:** الاقتباس، إعادة الصياغة، الانتحال، أنظمة التوثيق.
6. **تقييم المسودة** في ثمانية محاور، مع سلم خطورة وتقرير قابل للتنفيذ.

**القواعد الأربع:**
> **سؤال قابل للبحث. أطروحة قابلة للدفاع. دليل قابل للتحقق. توثيق قابل للتتبع.**

---

## 🚀 التثبيت

```bash
npx skills add specailm5/arabic-academic-skill -g -y
```

<details>
<summary>تثبيت يدوي، أو لبيئة واحدة فقط</summary>

**لبيئات محددة:**

```bash
npx skills add specailm5/arabic-academic-skill -a claude-code -a codex
```

**Windows (PowerShell):**

```powershell
$src = "skills\arabic-academic-skill"

New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\skills\arabic-academic-skill"
Copy-Item -Recurse -Force "$src\*" "$env:USERPROFILE\.claude\skills\arabic-academic-skill\"

New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.agents\skills\arabic-academic-skill"
Copy-Item -Recurse -Force "$src\*" "$env:USERPROFILE\.agents\skills\arabic-academic-skill\"

New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.gemini\config\skills\arabic-academic-skill"
Copy-Item -Recurse -Force "$src\*" "$env:USERPROFILE\.gemini\config\skills\arabic-academic-skill\"
```

**macOS / Linux:**

```bash
src=skills/arabic-academic-skill

mkdir -p ~/.claude/skills/arabic-academic-skill
cp -r "$src/." ~/.claude/skills/arabic-academic-skill/

mkdir -p ~/.agents/skills/arabic-academic-skill
cp -r "$src/." ~/.agents/skills/arabic-academic-skill/

mkdir -p ~/.gemini/config/skills/arabic-academic-skill
cp -r "$src/." ~/.gemini/config/skills/arabic-academic-skill/
```

**داخل مشروع واحد (VS Code):**

```powershell
New-Item -ItemType Directory -Force -Path ".agents\skills\arabic-academic-skill"
Copy-Item -Recurse -Force "path\to\skills\arabic-academic-skill\*" ".agents\skills\arabic-academic-skill\"
```

**بدون بيئة برمجية:** انسخ محتوى [`skills/arabic-academic-skill/SKILL.md`](skills/arabic-academic-skill/SKILL.md) إلى التعليمات المخصصة أو System Prompt.

</details>

---

## ⚡ كيف تعمل المهارة؟

### سبعة أسئلة قبل الكتابة

<table dir="rtl" align="right">
<thead>
<tr>
<th align="right">السؤال</th>
<th align="right">لماذا؟</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>ما نوع العمل؟</strong></td>
<td>بحث / ورقة / رسالة / مراجعة / ملخص</td>
</tr>
<tr>
<td><strong>ما التخصص والمنهج؟</strong></td>
<td>يحدد المصطلح والمنهج</td>
</tr>
<tr>
<td><strong>ما دليل الأسلوب؟</strong></td>
<td>يحدد التوثيق والخطة</td>
</tr>
<tr>
<td><strong>ما المرحلة؟</strong></td>
<td>خطة / مسودة / مراجعة</td>
</tr>
<tr>
<td><strong>من القارئ؟</strong></td>
<td>لجنة / محكّم / متخصص</td>
</tr>
<tr>
<td><strong>ما اللغة والمصطلح؟</strong></td>
<td>يحدد المعجم</td>
</tr>
<tr>
<td><strong>ما المحظور؟</strong></td>
<td>بيانات / أخلاقيات / تمويل</td>
</tr>
</tbody>
</table>
<br clear="all">

### الأنواع في سطر

<table dir="rtl" align="right">
<thead>
<tr>
<th align="right">النوع</th>
<th align="right">الوظيفة</th>
<th align="right">الطول</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>ورقة بحثية</strong></td>
<td>إضافة محدودة</td>
<td>٥–١٢ ألف كلمة</td>
</tr>
<tr>
<td><strong>رسالة/أطروحة</strong></td>
<td>إسهام أصيل</td>
<td>٨٠–٣٠٠ صفحة</td>
</tr>
<tr>
<td><strong>مراجعة أدبيات</strong></td>
<td>تنظيم المعرفة والفجوة</td>
<td>٥–١٥ ألف</td>
</tr>
<tr>
<td><strong>ملخص</strong></td>
<td>تكثيف البحث</td>
<td>١٥٠–٣٠٠ كلمة</td>
</tr>
<tr>
<td><strong>تقرير بحثي</strong></td>
<td>عرض ما جرى</td>
<td>متغيّر</td>
</tr>
<tr>
<td><strong>عرض أكاديمي</strong></td>
<td>نقل النتيجة</td>
<td>١٠–٢٠ شريحة</td>
</tr>
</tbody>
</table>
<br clear="all">

### مسار العمل

<pre dir="rtl"><code>
① النوع والقارئ والدليل
        ↓
② السؤال البحثي
        ↓
③ الأطروحة والفجوة
        ↓
④ الخطة: مقدمة، منهج، نتائج، خاتمة
        ↓
⑤ المادة والدراسات السابقة
        ↓
⑥ المسودة
        ↓
⑦ التوثيق والمراجعة
        ↓
⑧ اللغة والاتساق
</code></pre>

### قبل/بعد

<table dir="rtl" align="right">
<thead>
<tr>
<th align="right">قبل</th>
<th align="right">بعد</th>
<th align="right">السبب</th>
</tr>
</thead>
<tbody>
<tr>
<td>«يعد التعليم الإلكتروني من أهم الموضوعات»</td>
<td>«بعد توسّع التعليم الإلكتروني تباينت النتائج»</td>
<td>ظاهرة بدل عمومية</td>
</tr>
<tr>
<td>«مجموعة من الطلاب»</td>
<td>«٢٤٠ طالباً في ثلاث مدارس»</td>
<td>عينة قابلة للتكرار</td>
</tr>
<tr>
<td>«أثر كبير»</td>
<td>«ر = ٠٫٥٨، ٣١٪ تباين»</td>
<td>نتيجة قابلة للتحقق</td>
</tr>
<tr>
<td>«الاهتمام والتطوير»</td>
<td>«تدريب على التنظيم الذاتي»</td>
<td>توصية قابلة للتنفيذ</td>
</tr>
</tbody>
</table>
<br clear="all">

---

## 📚 المراجع والاعتماد

* **«الكتابة الأكاديمية: ضوابط الأداء، إجراءات التحسين، معايير الجودة»** — محمود جلال الدين سليمان — وكالة الصحافة العربية، ٢٠٢٣:
  <https://archive.org/details/AAskZad-1294251>
* **«أصول البحث العلمي ومناهجه»** — وجيه محجوب — دار المناهج، عمّان:
  <https://archive.org/details/00063-pdf>
* **«أصول كتابة البحث العلمي ومناهجه ومصادر الدراسات الإسلامية»** — يوسف المرعشلي — دار المعرفة، بيروت، ٢٠١٦:
  <https://archive.org/details/20240107_20240107_2358>

> **إقرار بالفضل:** هذه المهارة صياغة تعليمية مستقلة لمبادئ الكتب الثلاثة، مع نقل اقتباسات محدودة بإسنادها إلى صفحاتها. ولا يتضمّن المستودع نسخاً كاملة من الكتب، ولا يُغني عن الرجوع إلى الأصل.

---

## 🤝 المساهمة

نرحب بالمساهمات التي تحسّن المادة أو التحرير أو التوثيق. اقرأ [CONTRIBUTING.md](CONTRIBUTING.md) قبل فتح طلب سحب، والتزم بـ[قواعد السلوك](CODE_OF_CONDUCT.md).

---

## 🛡️ الأمان

إن وجدت مشكلة أمنية، فلا تفتح قضية عامة؛ راجع [SECURITY.md](SECURITY.md).

---

## 📄 سجل التغييرات

راجع [CHANGELOG.md](CHANGELOG.md) لمعرفة ما أُضيف في كل إصدار.

---

## 📬 الدعم

للأسئلة والاقتراحات: [افتح قضية](https://github.com/specailm5/arabic-academic-skill/issues).

---

## 📜 الترخيص (License)

هذه المهارة مفتوحة المصدر تحت رخصة [MIT](LICENSE)، ومتاحة للاستخدام الشخصي والتجاري والبحثي لدعم اللغة العربية.

