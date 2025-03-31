---
title: Exercise 03 - connect me.
description: Shell 00 da 9 ta mashq bor. 
author: MrKakharov
date: 2025-03-27 01:03:00 +0500
categories: [21-IT Maktab - School 21, Shell 00]
tags: [Basseyn - C Piscine, Shell 00]
image:
  path: /bash-transparent.png
  lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
  alt: Bash - Bourne Again Shell.
media_subpath: '/assets/posts/courses/2025-03-26-tugallangan-c-piscine/'
---

# shell 00 Mashq 03

> Sizda amal qiluvchi (muddati tugamagan) `Kerberos` chiptasi borligiga ishonch hosil qiling. Agar hali yo'q bo'lsa, uni oling. 
> Kamida bitta `Kerberos` chiptasini olganingizdan so'ng, barcha chiptalaringiz ro'yxatini `klist.txt` nomli faylga yozing. 
> Fayl nomi bejiz tanlanmagan. 
> Bu buyruqlar keyinchalik kerak bo'ladi, shuning uchun ularni eslab qolishga harakat qiling!
{: .prompt-warning .shadow }

***

#### Bu topshiriqni bajarishning taxminiy varianti!

#### Endi mijozda tarmoq va `Kerberos`ni to'g'ri sozlaganligimizni tekshirish mumkin:

#### Yangi chipta (`Kerberos ticket`) olamiz va uni faylga yo'naltiramiz, uni qator oxiriga qo'shamiz (agar qator bo'lsa, agar hujjat bo'sh bo'lsa, unda yangi yozuv paydo bo'ladi):

```bash
kinit >> klist.txt
```

#### Foydalanuvchi parolini kiritamiz:

```bash
kinit testuser@AKTIV-TEST.RU
```

#### Va berilgan chiptani ko'ramiz:

```bash
klist
```

#### Shundan so'ng uni quyidagi buyruq yordamida o'chirish mumkin:

```bash
kdestroy
```

## Foydali manbalar:

- [`Tugallangan С piscine` maqolasiga qaytish](../tugallangan-c-piscine/)
- [Kerberos buyruqlari bo'yicha qo'llanma](https://uit.stanford.edu/service/kerberos/user_guide/commands)
- [Kerberos protokoli haqida Vikipediya maqolasi](https://en.wikipedia.org/wiki/Kerberos_%28protocol%29)
- [Kerberos haqida Aktiv kompaniya blogi](https://habr.com/ru/company/aktiv-company/blog/170829/)
- [Linux: LDAP va Active Directory haqida ma'lumot](https://www.f-notes.info/linux:ldap_ad)
