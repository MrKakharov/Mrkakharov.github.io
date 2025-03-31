---
title: Exercise 08 - clean, find.
description: Shell 00 da 9 ta mashq bor. 
author: MrKakharov
date: 2025-03-27 01:08:00 +0500
categories: [21-IT Maktab - School 21, Shell 00]
tags: [Basseyn - C Piscine, Shell 00]
image:
  path: /bash-transparent.png
  lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
  alt: Bash - Bourne Again Shell.
media_subpath: '/assets/posts/courses/2025-03-26-tugallangan-c-piscine/'
---

# shell 00 Mashq 08

>`clean` nomli faylda quyidagi buyruq qatorini joylashtiring, u barcha fayllarni - joriy katalogda va uning ichki kataloglarida - `~` va `/` bilan tugaydigan yoki `#` bilan boshlanadigan yoki tugaydigan barcha fayllarni qidiradi. Buyruq qatori barcha topilgan fayllarni ko'rsatadi va o'chiradi. Faqat bitta buyruqga ruxsat beriladi: `;`, `&&` yoki boshqa hiylalardan foydalanish mumkin emas.
{: .prompt-warning .shadow }

#### man find

***

#### 1) Fayl yarating

```bash
touch clean
```

#### 2) quyidagi mazmun bilan

```bash
find . \( -name "*~.*" -o -name "#*#" -o -name "#*#.*" -o -name "*~" \) -print -delete
```

#### YOKI quyidagisi bilan

```bash
find . -name "*~" -print -delete -or -name "#*#" -print -delete -or -name "#" -print -delete
```

## Foydali manbalar:

- [`Tugallangan С piscine` maqolasiga qaytish](../tugallangan-c-piscine/)
- [man find buyrug'i haqida maqola](https://linux-faq.ru/page/komanda-file)
