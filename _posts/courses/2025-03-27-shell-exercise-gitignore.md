---
title: Exercise 06 - gitignore.
description: Shell 00 da 9 ta mashq bor. 
author: MrKakharov
date: 2025-03-27 01:06:00 +0500
categories: [21-IT Maktab - School 21, Shell 00]
tags: [Basseyn - C Piscine, Shell 00]
image:
  path: /bash-transparent.png
  lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
  alt: Bash - Bourne Again Shell.
media_subpath: '/assets/posts/courses/2025-03-26-tugallangan-c-piscine/'
---

# Shell 00 Mashq 06

> Ushbu mashqda siz qisqa shell skript yozasiz, u sizning `Git` repozitoriyingiz tomonidan e'tiborga olinmaydigan barcha mavjud fayllarni ro'yxatlaydi. 
{: .prompt-warning .shadow }

#### Misol:

```bash
bash gitignore.sh | cat -e
```

#### Natija

```bash
.DS_Store$
mywork.c~$
```

***

#### RTFM!

#### 1) Fayl yarating

```bash
touch gitignore.sh
```

#### 2) quyidagi mazmun bilan:

```bash
#!/bin/sh
find . -exec git check-ignore {} + | xargs -I{} basename {}
```

## Foydali manbalar:

- [`Tugallangan С piscine` maqolasiga qaytish](../tugallangan-c-piscine/)
- [Git documentlari sahifasi:](https://git-scm.com/doc){:target="_blank"}
