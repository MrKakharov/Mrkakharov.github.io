---
title: Exercise 02 - exo to tar.
description: Shell 00 da 9 ta mashq bor. 
author: MrKakharov
date: 2025-03-27 01:02:00 +0500
categories: [21-IT Maktab - School 21, Shell 00]
tags: [Basseyn - C Piscine, Shell 00]
image:
  path: /bash-transparent.png
  lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
  alt: Bash - Bourne Again Shell.
media_subpath: '/assets/posts/courses/2025-03-26-tugallangan-c-piscine/'
---

# shell 00 Mashq 02

> `Kerakli nomdagi fayllar va kataloglarni yarating`; 
> Ularga skrinshotda ko'rsatilgan xususiyatlar va hajmni baytlarda belgilang;
{: .prompt-warning .shadow }

#### Ushbu buyruq bilan tekshirganda

```bash
$> ls -l
```

#### Natija quyidagidek bo'lishi kerak.

```bash
total 42
drwx--xr-x 2 XX XX XX Jun 1 20:47 test0
-rwx--xr-- 1 XX XX  4 Jun 1 21:46 test1
dr-x---r-- 2 XX XX XX Jun 1 22:45 test2
-r-----r-- 2 XX XX  1 Jun 1 23:44 test3
-rw-r----x 1 XX XX  2 Jun 1 23:43 test4
-r-----r-- 2 XX XX  1 Jun 1 23:44 test5
lrwxr-xr-x 1 XX XX  5 Jun 1 22:20 test6 -> test0
$>
```

***

#### XX o'rniga nima bo'lishidan xavotir olmang.

#### Fayl vaqt belgisi o'rniga yil qabul qilinadi.

#### 1) `test0` nomli ikkita katalog yaratamiz:

```bash
mkdir test0
```

```bash
mkdir test2
```

#### 2) `test` nomli 4 ta fayl yaratamiz:

```bash
touch test{1,3,4}
```

#### 3) `test0` katalogiga `test6` nomli simvolik havola yaratamiz:

```bash
ln -s test0 test6
```

#### va `test3` fayliga `test5` nomli qattiq havola yaratamiz:

```bash
ln test3 test5
```

#### 4) Kerakli hajmdagi hujjatlarni belgilaymiz - ularga ma'lumot yozamiz:

```bash
printf "1234" > ./test1
```

```bash
printf "1" > ./test3
```

```bash
printf "12" > ./test4
```

#### 5) Fayllar va kataloglarga sana belgilaymiz:

```bash
touch -t 06012047 test0

touch -t 06012146 test1

touch -t 06012245 test2

touch -t 06012344 test3

touch -t 06012343 test4

touch -t 06012344 test5

touch -t 06012220 test6
```

#### 6) `o'qish`/`yozish`/`bajarish` huquqlarini o'rnatamiz:

```bash
chmod 715 ./test0

chmod 714 ./test1

chmod 504 ./test2

chmod 404 ./test3

chmod 641 ./test4
```

#### 7) Tekshirish:

```bash
ls -l
```

#### 8) Oldingi qadamlarni bajarganingizdan so'ng, ushbu katalogdagi barcha fayllardan yuborish uchun fayl yaratish uchun quyidagi buyruqni bajaring:

```bash
tar -cf exo2.tar *
```

## Foydali manbalar:

- [`Tugallangan С piscine` maqolasiga qaytish](../tugallangan-c-piscine/)
- [Fayllarni yaratish va ularning vaqtini boshqarish:](https://itproffi.ru/sozdanie-fajlov-v-linux-komanda-touch/){:target="_blank"}
- [O'qish, yozish, ishga tushirish huquqlarini o'rnatish:](https://habr.com/ru/post/469667/){:target="_blank"}
- [Faylga ma'lumot yozish:](https://linux-notes.org/vstavit-tekst-v-fajl-v-unix-linux/){:target="_blank"}
- [Joker belgilar:](https://habr.com/ru/post/99827/){:target="_blank"}
