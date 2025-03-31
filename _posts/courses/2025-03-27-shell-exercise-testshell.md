---
title: Exercise 01 - testShell.
description: Shell 00 da 9 ta mashq bor. 
author: MrKakharov
date: 2025-03-27 01:01:00 +0500
categories: [21-IT Maktab - School 21, Shell 00]
tags: [Basseyn - C Piscine, Shell 00]
image:
  path: /bash-transparent.png
  lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
  alt: Bash - Bourne Again Shell.
media_subpath: '/assets/posts/courses/2025-03-26-tugallangan-c-piscine/'
---

# shell 00 Mashq 01

>`testDay00` nomli fayl yarating va unga quyidagi talab qilingan xususiyatlarni o'rnating:
{: .prompt-warning .shadow }

#### Ushbu buyruq bilan tekshirganda

```bash
ls -l
```

#### Natija quyidagidek bo'lishi kerak.

```bash
total 1
-r--r-xr-x 1 XX XX 40 Jun 1 23:42 testShell00
```

***

#### XX o'rniga nima bo'lishidan xavotir olmang.
#### Faylning vaqt belgisi o'rniga yil qabul qilinadi.
#### 1) `testDay00` nomli fayl yaratamiz va vaqtni o'rnatamiz:

```bash
touch testDay00
```

#### 2) Hujjat hajmi 40 bayt bo'lishi kerak, unga ma'lumot yozamiz:

```bash
printf "1234567890123456789012345678901234567890" > ./testShell00
```

(Agar ma'lumotni "echo" orqali yuborsangiz, 39 ta belgi yozishingiz kerak, chunki har biri 1 bayt "og'irlik" qiladi va avtomatik ravishda hujjatga yana bitta bayt qo'shiladi) = 40

```bash
echo "123456789012345678901234567890123456789" >> ./testShell00
```

#### 3) Vaqtni o'rnatamiz:

```bash
touch -c -t 06012342 testShell00
```

#### 4) O'qish/yozish/ishga tushirish huquqlarini o'rnatamiz:

```bash
chmod 455 ./testShell00
```

Izoh:

Har bir raqam `chmod` buyrug'idan keyin faylga huquqlarni uch xonali son shaklida belgilaydi.

Kerakli huquqlarni ishlatib:

- 4 bu o'qish
- 2 bu yozish
- 1 bu ishga tushirish

Ularni birlashtirishimiz mumkin. Masalan:

- 4 + 2 + 1 = 7 (7 - hamma narsa mumkin: o'qish, yozish va ishga tushirish)
- 4 + 2 = 6 (faqat o'qish va yozish mumkin, ishga tushirish emas)
- 4 + 1 = 5 (faqat o'qish va ishga tushirish mumkin, yozish emas)
- 1 + 2 = 3 (faqat ishga tushirish va yozish mumkin, o'qish emas)

Ushbu soddalashtirilgan shaklda fayllar uchun huquqlar o'qiladi va o'zgartiriladi.
Har bir raqam - bu birlashtirilgan huquqlar to'plami bo'lib, biz ularni faylga qo'llashimiz mumkin.

#### 5) Tekshirish:

```bash
ls -l ./testShell00
```

#### 6) Oldingi qadamlarni bajargandan so'ng, yuborish uchun fayl yaratish uchun quyidagi buyruqni bajaramiz:

```bash
tar -cf testShell00.tar testShell00
```

## Foydali manbalar:

- [`Tugallangan С piscine` maqolasiga qaytish](../tugallangan-c-piscine/)
- [Fayllarni yaratish va ularning vaqtini boshqarish:](https://itproffi.ru/sozdanie-fajlov-v-linux-komanda-touch/){:target="_blank"}
- [O'qish, yozish, ishga tushirish huquqlarini o'rnatish:](https://habr.com/ru/post/469667/){:target="_blank"}
- [Faylga ma'lumot yozish:](https://linux-notes.org/vstavit-tekst-v-fajl-v-unix-linux/){:target="_blank"}
- [Joker belgilar:](https://habr.com/ru/post/99827/){:target="_blank"}
