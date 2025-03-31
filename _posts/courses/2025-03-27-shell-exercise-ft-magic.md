---
title: Exercise 09 - ft_magic.
description: Shell 00 da 9 ta mashq bor. 
author: MrKakharov
date: 2025-03-27 01:09:00 +0500
categories: [21-IT Maktab - School 21, Shell 00]
tags: [Basseyn - C Piscine, Shell 00]
image:
  path: /bash-transparent.png
  lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
  alt: Bash - Bourne Again Shell.
media_subpath: '/assets/posts/courses/2025-03-26-tugallangan-c-piscine/'
---

# shell 00 Mashq 09

> `ft_magic` nomli sehrli fayl yarating, u 42-fayl turlarini aniqlash uchun mos ravishda formatlangan bo'lib, 42-baytda "42" qatori bilan qurilgan fayllarni aniqlaydi.
{: .prompt-warning .shadow }

> [Ft_magic faylini yuklab olish (PDF)](https://github.com/MrKakharov/mrkakharov.github.io/blob/main/_posts/courses/shell00/Exercise%2009(ft_magic)/ft_magic.42){: target="_blank" }
{: .prompt-tip .shadow }

#### man file

***

#### 1) Faylni yarating

```bash
    touch ft_magic
```

#### 2) Vazifani bajarish uchun men bir nechta variantlarni topdim, bu faylni quyidagi mazmun bilan to'ldirish usullari:

```bash
    42 string 42 42 file
```

#### YOKI BUNDAY

```bash
    42	string	42	42 file
```

#### YOKI BUNDAY

```bash
    \00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\00\0042
```

#### YOKI BUNDAY

```bash
    42	string	42	42 File Type
```

#### YOKI BUNDAY

```bash
    =0x2A    string    42
```

#### YOKI BUNDAY

```bash
    !:mime    42 file
```

#### Tekshirish uchun buyruq:

```bash
    file -i ft_magic
```

#### Linux terminalida quyidagi buyruqni kiritib, faylning o'n oltilik ko'rinishini ko'rishimiz mumkin:

```bash
    xdd ft_magic
```

#### Faylning sehrli raqamlarini o'zgartirish:

```bash
    hexedit ft_magic
```

## Foydali manbalar:

- [`Tugallangan С piscine` maqolasiga qaytish](../tugallangan-c-piscine/)
- [man find buyrug'i haqida maqola](https://linux-faq.ru/page/komanda-file)
