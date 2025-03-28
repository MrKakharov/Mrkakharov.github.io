---
title: Git: "This diff contains a change in line endings from 'LF' to 'CRLF'" muammosi
authors: [cotes, MrKakharov]
date: 2025-03-26 02:04:00 +0500
categories: [Chirpy, O'rganish]
tags: [Chirpy, Github]
pin: true
render_with_liquid: false
---

## **Git: "This diff contains a change in line endings from 'LF' to 'CRLF'" muammosi va uning yechimi**  

### **Muammo tushuntirilishi**  
Git foydalanuvchilar matnli fayllar bilan ishlaganda, qator oxiri belgilarini (`line endings`) avtomatik ravishda almashtirishi mumkin.  

- **LF (Line Feed)** – Linux, macOS va boshqa Unix tizimlarida qator oxiri sifatida ishlatiladi.  
- **CRLF (Carriage Return + Line Feed)** – Windows tizimida qator oxiri sifatida ishlatiladi.  

Agar Git sizga **"This diff contains a change in line endings from 'LF' to 'CRLF'"** xabarini chiqarsa, bu degani Git faylning qator oxirlarini Windows (`CRLF`) formatiga avtomatik o‘zgartirib yuborgan.  

---

## **Muammoni qanday hal qilish mumkin?**  

### **1. Git sozlamalarini tekshirish**  
Avval Git qanday qator oxiri sozlamalaridan foydalanayotganini tekshiring:  

```sh
git config --global core.autocrlf
```

- Agar natija **`true`** bo‘lsa – Git avtomatik ravishda **LF → CRLF** ga almashtirishi mumkin.  
- Agar **`false`** bo‘lsa – Git qator oxirlarini o‘zgartirmaydi.  
- Agar **`input`** bo‘lsa – Git faqat Windows `CRLF` ni `LF` ga o‘tkazadi, lekin aksincha emas.  

**Tavsiya etiladigan sozlama:**  
```sh
git config --global core.autocrlf input
```
Bu Git-ga **faqat Windows formatidagi `CRLF` qatorlarini `LF` ga o‘tkazishga ruxsat beradi**, ammo aksincha bo‘lishiga yo‘l qo‘ymaydi.  

---

### **2. `.gitattributes` faylida `LF` ni majburlash**  
Agar siz barcha matnli fayllarni faqat `LF` formatida saqlamoqchi bo‘lsangiz, loyiha katalogida `.gitattributes` faylini yaratib, quyidagilarni qo‘shing:  

```ini
* text=auto
* text eol=lf
```
Bu Git-ga barcha matnli fayllarni **faqat `LF` formatida saqlashni** buyuradi.  

---

### **3. Barcha fayllarni `LF` formatiga qaytarish**  
Agar ba’zi fayllar allaqachon `CRLF` formatiga o‘zgargan bo‘lsa, ularni `LF` formatiga qaytarish uchun quyidagi buyruqdan foydalaning:  

```sh
find . -type f -exec dos2unix {} +
```

Agar `dos2unix` mavjud bo‘lmasa, uni o‘rnatish kerak:  
- **Ubuntu/Debian:** `sudo apt install dos2unix`  
- **MacOS:** `brew install dos2unix`  
- **Windows (Git Bash yoki WSL):** `sudo apt install dos2unix`  

Barcha fayllar `LF` formatiga o‘tgandan so‘ng, Git-ga qayta yuklash:  

```sh
git add .
git commit -m "Normalize line endings to LF"
```

---

### **4. Git keshini tozalash va qayta yuklash**  
Agar Git fayllarni allaqachon `CRLF` formatida eslab qolgan bo‘lsa, quyidagi buyruqlar bilan keshni tozalab, `LF` formatida qayta yuklang:  

```sh
git rm --cached -r .
git reset --hard
git add .
git commit -m "Fix line endings to LF"
```

🚨 **Ogohlantirish:** `git reset --hard` barcha saqlanmagan o‘zgarishlarni o‘chirib tashlaydi. Agar avval saqlab qo‘yish kerak bo‘lsa, `git stash` ishlating.  

---

## **Xulosa**  
- **Git sozlamalarini tekshiring:** `core.autocrlf` ni `input` ga o‘rnating.  
- **`.gitattributes` faylida `LF` ni majburlang.**  
- **Barcha fayllarni `LF` formatiga qaytaring** (`dos2unix` yoki `find` yordamida).  
- **Git keshini tozalang va o‘zgarishlarni qayta yuklang.**  

Shu usullar yordamida siz Git-da **"This diff contains a change in line endings from 'LF' to 'CRLF'"** muammosidan qutulishingiz mumkin. 🚀

**Barcha kataloglar va ularning ichidagi fayllardagi qator oxirlarini (`CRLF` → `LF`) avtomatik tuzatish uchun** siz allaqachon to‘g‘ri buyruq ishlatyapsiz:  

```sh
find . -type f -exec dos2unix {} +
```

Bu joriy katalog (`.`) ichidagi barcha **fayllarni**, shu jumladan **barcha ichki kataloglar** va ularning ichidagi fayllarni ham `dos2unix` orqali `LF` formatiga o‘tkazadi. **Shuning uchun qo‘shimcha hech narsa qilish shart emas.**  

---

### **Qanday qilib ishonch hosil qilish mumkin?**  
Agar barcha fayllar qayta ishlanganiga ishonch hosil qilishni istasangiz, quyidagilarni tekshirib ko‘ring:  

#### **1. `file` buyrug‘i bilan tekshirish**
Bu buyruq barcha fayllarning qator oxiri qanday ekanini ko‘rsatadi:  
```sh
find . -type f -exec file {} +
```
Agar natijada **"CRLF"** yozuvi bo‘lsa, bu fayllar hali ham Windows formatida ekanini bildiradi.  

#### **2. Git-da tekshirish**
Agar siz Git ishlatayotgan bo‘lsangiz, qaysi fayllar o‘zgarganini tekshirish uchun:  
```sh
git status
```
Agar ko‘plab fayllar o‘zgargan bo‘lsa, Git ularni `CRLF` dan `LF` ga o‘tgan deb hisoblagan bo‘lishi mumkin.  

---

### **Qo‘shimcha: faqat matnli fayllarni to‘g‘rilash**  
Ba’zi binar fayllar (masalan, rasmlar yoki PDF fayllar) buzilmasligi uchun faqat matnli fayllarni o‘zgartirish mumkin. Quyidagi buyruq faqat `.txt`, `.md`, `.sh`, `.py` va `.c` kabi fayllarni `LF` formatiga o‘tkazadi:  

```sh
find . -type f -exec file {} + | grep text | cut -d: -f1 | xargs dos2unix
```

Bu buyruq:  
1. **`file`** yordamida barcha fayllarni tahlil qiladi.  
2. **`grep text`** faqat matnli fayllarni tanlaydi.  
3. **`cut -d: -f1`** fayl nomlarini ajratib oladi.  
4. **`xargs dos2unix`** – har bir matnli faylni `LF` ga o‘tkazadi.  

---

✅ **Xulosa:**  
- **`find . -type f -exec dos2unix {} +`** allaqachon barcha kataloglar va ichidagi fayllarni ham `LF` formatiga o‘tkazadi.  
- **Agar faqat matnli fayllarni o‘zgartirish kerak bo‘lsa, `file` va `grep` yordamida filtrlash mumkin.**  
- **Git ishlatilsa, `git status` va `git diff` bilan natijani tekshirish tavsiya etiladi.**