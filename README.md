# הזמנות לסין

יישום ליצירת הזמנות למפעל ולהורדת קובץ אקסל בפורמט הקבוע.

- דגם עם מספר סידורי, תיאור, וקומבואים (A, B, C…)
- חלוקת מידות לחבילה (ברירת מחדל 9 יחידות בחבילה) ומספר חבילות לכל קומבו
- עלות ליחידה ב-RMB או בדולר, והמרה לשקלים לפי שער עדכני
- סיכום חי של ההזמנה בראש המסך
- ההזמנה נשמרת בדפדפן, ואפשר לשמור ולטעון אותה כקובץ

## פריסה ב-CapRover

הפרויקט כולל `captain-definition` ו-`Dockerfile` (nginx). כל דחיפה לענף `main` נפרסת אוטומטית דרך GitHub Actions (`.github/workflows/deploy.yml`).

הגדרה חד-פעמית:
1. ב-CapRover: אפליקציה בשם `china-orders` ← Deployment ← Enable App Token, ולהעתיק את הטוקן.
2. ב-GitHub: Settings ← Secrets and variables ← Actions, ולהוסיף:
   - `CAPROVER_SERVER`: כתובת לוח הבקרה, למשל `https://captain.example.com`
   - `CAPROVER_APP_TOKEN`: הטוקן מהשלב הקודם

אם שם האפליקציה בקפרובר שונה, יש לעדכן את `CAPROVER_APP` בקובץ ה-workflow.

## הרצה מקומית

פותחים את `public/index.html` בדפדפן, או:

```bash
docker build -t china-orders . && docker run -p 8080:80 china-orders
```
