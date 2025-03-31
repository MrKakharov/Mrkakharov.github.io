---
title: Exercise 05 - git commit.
description: Shell 00 da 9 ta mashq bor. 
author: MrKakharov
date: 2025-03-27 01:05:00 +0500
categories: [21-IT Maktab - School 21, Shell 00]
tags: [Basseyn - C Piscine, Shell 00]
image:
  path: /bash-transparent.png
  lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
  alt: Bash - Bourne Again Shell.
media_subpath: '/assets/posts/courses/2025-03-26-tugallangan-c-piscine/'
---

# Shell 00 Mashq 05

> `Git repozitoriya`ngizning so'nggi `5 ta commit` identifikatorlarini ko'rsatadigan shell skript yarating:
{: .prompt-warning .shadow }

#### Natija quyidagidek bo'lishi kerak.

```
05cb017fddb87b588f015fbd3b44ac9b96cba760
90f900418ec48052a51a674963e6d5688fa2fe29
6bdaf71595ff90e987398059071b8f668f29abb6
26be13667edd1a882ad5093725d962bc056a9c9f
4caf2adc0b34c02c4c616e2e2673b25bad9cd2e4
```

***

**RTFM!**

### Amalga oshirish bosqichlari:

1. **Fayl yarating:**

```bash
touch git_commit.sh
```

2. **Faylga quyidagi kodni qo'shing:**

```bash
#!/bin/sh
git log -n 5 --pretty=format:"%H"
```

## Foydali manbalar:

- [`Tugallangan С piscine` maqolasiga qaytish](../tugallangan-c-piscine/)
- [Git documentlari sahifasi:](https://git-scm.com/doc){:target="_blank"}
