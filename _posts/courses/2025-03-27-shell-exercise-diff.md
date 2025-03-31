---
title: Exercise 07 - diff.
description: Shell 00 da 9 ta mashq bor. 
author: MrKakharov
date: 2025-03-27 01:07:00 +0500
categories: [21-IT Maktab - School 21, Shell 00]
tags: [Basseyn - C Piscine, Shell 00]
image:
  path: /bash-transparent.png
  lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
  alt: Bash - Bourne Again Shell.
media_subpath: '/assets/posts/courses/2025-03-26-tugallangan-c-piscine/'
---

# shell 00 Mashq 07

> `b` faylini yarating. Ishlash uchun bizga eski versiyasi saqlangan `a` fayli va yangi o'zgarishlar haqidagi ma'lumotlarni saqlovchi `sw.diff` fayli taqdim etiladi.
{: .prompt-warning .shadow }

> [Resurslar faylini yuklab olish (PDF)](https://github.com/MrKakharov/mrkakharov.github.io/blob/main/_posts/courses/shell00/Exercise%2007(diff)/resources.tar.gz){: target="_blank" }
{: .prompt-tip .shadow }




***

#### `cat` dasturidan `-e` flagi bilan foydalanib, `a` faylining mazmuni quyidagicha ko'rinadi:

```bash
%>cat -e a
```

#### Natija

```bash
STARWARS$
Episode IV, A NEW HOPE It is a period of civil war.$
$
Rebel spaceships, striking from a hidden base, have won their first victory against the evil
Galactic Empire.$
During the battle, Rebel spies managed to steal secret plans to the Empire s ultimate weapon, the
DEATH STAR,$
an armored space station with enough power to destroy an entire planet.$
$
Pursued by the Empire s sinister agents, Princess Leia races home aboard her starship, custodian of
the stolen plans that can save her people and restore freedom to the galaxy...$
$
```

#### 1) `a` va `sw.diff` fayllarini o'z ichiga olgan arxivni ochamiz:

```bash
tar -xf ./'resources.tar.gz'
```

#### 2) `patch` dasturidan foydalanamiz. Ushbu dastur `sw.diff` faylidan yangi o'zgarishlar haqidagi ma'lumotlarni olib, ularni `a` faylidagi matn bilan birlashtiradi va yangi o'zgarishlarni o'z ichiga olgan `b` faylini yaratadi:

```bash
patch ./a  -o ./b < ./sw.diff
```

#### `a` faylidagi o'zgarishlarni bekor qilish uchun terminalda quyidagini kiriting:

```bash
patch ./a -R < ./sw.diff
```

#### `b` faylining mazmuni (`cat` dasturidan `-e` flagi bilan foydalanib ko'rilganida) quyidagicha bo'ladi:

```bash
cat -e ./b
```

#### Natija
```bash
Episode V, A NEW H0PE It is a period of civil war$
Rebel spaceships, striking from a hidden base, have won their first victory against the evil Galactic Empire. $
During the battle, Rebel spies managed to steal secret plans to the Empire's ultimate weapon, the STAR DEATH, an armored space station with enough power to destroy an entire planet.$
$
$
Pursued by the Empire's sinister agents,$
Princess Mehdi races home aboard her starship, custodian of the stolen plans that can save her people and restore the dictatorship to the galaxie..$
$
$
$
$
```

#### 3) Tekshirishni amalga oshiramiz. `sw.diff` faylini va `patch` dasturi yordamida `a` va `b` fayllarini solishtirib yaratilgan `sw.diff2` faylini taqqoslaymiz. Agar `sw.diff` va `sw.diff2` fayllarini taqqoslash natijasida dastur hech qanday chiqish bermasa, demak fayllar bir xil va yangi versiyani tiklash muvaffaqiyatli amalga oshirilgan:

```bash
diff ./a ./b > ./sw.diff2
```

```bash
diff ./sw.diff ./sw.diff2
```

## Foydali manbalar:

- [`Tugallangan С piscine` maqolasiga qaytish](../tugallangan-c-piscine/)
- [Diff haqida Wikipedia maqolasi](https://ru.wikipedia.org/wiki/Diff){:target="_blank"}
- [Patch haqida man sahifasi](https://man7.org/linux/man-pages/man1/patch.1.html){:target="_blank"}

***

### **`patch ./a -o ./b < ./sw.diff` qanday ishlaydi?**

Ushbu buyruq `patch` dasturidan foydalanib, `sw.diff` faylidagi o‘zgarishlarni `a` fayliga qo‘llaydi va natijani `b` fayliga yozadi. Endi uning ishlash jarayonini **qadam-baqadam** tushuntirib chiqamiz.

## **1. Buyruqning asosiy qismlari**

```bash
patch ./a -o ./b < ./sw.diff
```

Bu yerda:
- **`patch`** – `diff` faylidan o‘zgarishlarni qo‘llash uchun ishlatiladigan Linux/Unix dasturi.
- **`./a`** – dastlabki (manba) fayl, o‘zgarishlar unga qo‘llanadi.
- **`-o ./b`** – natija `b` fayliga yoziladi (manba fayl `a` o‘zgarmaydi).
- **`< ./sw.diff`** – `sw.diff` faylidan farqlar (`diff`) olinadi.

## **2. `patch` qanday ishlaydi?**

`patch` quyidagi bosqichlarda ishlaydi:

### **Bosqich 1: `sw.diff` faylini o‘qish**
`patch` dasturi `sw.diff` faylini qabul qilib, uning tarkibini tahlil qiladi.

#### **Misol: `sw.diff` faylining tarkibi**

```diff
--- a
+++ a
@@ -1,3 +1,3 @@
 Salom, dunyo!
-Bu eski versiya.
+Bu yangi versiya.
 Bu yana bir qator.
```

Bu `diff` fayli **`a` faylidagi `Bu eski versiya.` qatorini `Bu yangi versiya.` bilan almashtirish kerakligini bildiradi**.

### **Bosqich 2: Manba fayl (`a`) bilan taqqoslash**
`patch` dasturi:
1. `a` faylini ochadi.
2. `@@ -1,3 +1,3 @@` qatoriga qarab, **1-qatordan boshlab 3-qatorgacha** bo‘lgan joyni solishtiradi.
3. `-` belgisi bilan berilgan qator (`Bu eski versiya.`) **o‘chirilishi kerak** deb tushunadi.
4. `+` belgisi bilan berilgan qator (`Bu yangi versiya.`) **qo‘shilishi kerak** deb tushunadi.

---

### **Bosqich 3: O‘zgarishlarni qo‘llash va natija faylni yaratish**
- `patch` `a` faylida o‘zgarishlarni amalga oshiradi.
- Lekin, chunki `-o ./b` opsiyasi ishlatilgan, **o‘zgarishlar natijasi `b` fayliga yoziladi**.
- **`a` fayli hech qanday o‘zgarishga uchramaydi.**

---

## **3. Natijaviy holat**
Agar `a` fayli quyidagicha bo‘lsa:

**`a` fayli (dastlabki holat)**
```txt
Salom, dunyo!
Bu eski versiya.
Bu yana bir qator.
```

**Patch qo‘llangandan keyin `b` fayli quyidagicha bo‘ladi:**
```txt
Salom, dunyo!
Bu yangi versiya.
Bu yana bir qator.
```

`a` fayli esa **o‘zgarishsiz qoladi**, chunki `patch` natijani `b` fayliga yozdi.

---

## **4. `patch` dasturining muhim jihatlari**
- **Agar `-o ./b` opsiyasi ishlatilmasa, `patch` bevosita `a` faylini o‘zgartiradi.**
- **Agar `patch` noto‘g‘ri formatdagi `diff` faylini uchratsa yoki `a` faylidagi satrlar mos kelmasa, u xatolik chiqaradi yoki `.rej` fayl yaratadi.**
- **Agar `patch` qaysi faylga qo‘llanishini aniqlay olmasa, `-pN` opsiyasi bilan katalog tuzilishini boshqarish kerak.**

---

## **5. Xulosa**
- `patch` `sw.diff` faylidagi farqlarni **`a` fayliga qo‘llaydi**.
- `-o ./b` opsiyasi tufayli **o‘zgarishlar `b` fayliga yoziladi**, `a` fayli esa o‘zgarmaydi.
- `patch` **`diff` faylidagi qator tartibi va kontekstga qarab** o‘zgarishlarni qo‘llaydi.
- Agar `diff` noto‘g‘ri yoki eski bo‘lsa, `patch` uni qo‘llay olmasligi mumkin.

## Foydali manbalar:

- [`Tugallangan С piscine` maqolasiga qaytish](../tugallangan-c-piscine/)
- [Diff haqida Wikipedia maqolasi](https://ru.wikipedia.org/wiki/Diff){:target="_blank"}
- [Patch haqida man sahifasi](https://man7.org/linux/man-pages/man1/patch.1.html){:target="_blank"}