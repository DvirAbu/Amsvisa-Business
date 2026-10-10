# AmsVisa — עמוד נחיתה B2B

עמוד נחיתה לשירותי ויזות ואשרות כניסה לעובדי חברות, מבית **אמסלם ניהול נסיעות עסקיות**.

דף יחיד, עצמאי לחלוטין (`index.html`) — ללא תלות ב-build step, ללא npm. כל ה-CSS וה-JS מוטבעים בקובץ, והלוגואים מוטמעים כ-`data:` URI כדי שהעמוד יעבוד מכל מקום, כולל GitHub Pages, ללא קבצים נוספים.

## הרצה מקומית

פתחו את `index.html` בדפדפן — זהו, אין build ואין שרת נדרש.

```bash
# אופציונלי: שרת סטטי מקומי
python3 -m http.server 8000
# ואז גלשו אל http://localhost:8000
```

## פרסום עם GitHub Pages

1. Settings → Pages
2. Source: **Deploy from a branch**
3. Branch: `main`, תיקייה: `/ (root)`
4. שמרו — תוך דקה-שתיים האתר יהיה זמין בכתובת `https://<username>.github.io/amsvisa-landing/`

## מבנה

- `index.html` — הדף כולו (HTML + CSS + JS מוטבעים, פונטים מ-Google Fonts, לוגואים מוטבעים כ-base64)

## טופס הלידים

הטופס מחובר ל-[Formspree](https://formspree.io) ושולח פניות ל-`https://formspree.io/f/mrpekawz`. ודאו שכתובת המייל שתרצו לקבל אליה פניות מאומתת בחשבון ה-Formspree (Dashboard → הטופס → Verify Email).

כדי לחבר את הטופס ל-endpoint אחר (למשל חשבון Formspree אחר): בקובץ `index.html` מחפשים את תגית ה-`<form>` ומחליפים את כתובת ה-`action` בכתובת החדשה.

יש גם שדה honeypot מוסתר (`_gotcha`) שמסנן חלק מהספאם האוטומטי, ושדה `_subject` שקובע את נושא המייל שיתקבל.
