---
author: Athan's Dad
title: Ujicoba Post dan Featured Image
date: 2021-09-07T01:30:53.305Z
description: Ujicoba Post dan Featured Image lagi
categories:
  - Tutorial
tags:
  - Testing
image: slide1.png
license: Free
---
## Ujicoba Featured Image dan Post Lagi

Ujicoba featured image sebelumnya belum berhasi padahal file `config.yml` sudah dicek dan nampaknya tidak ada error lagi.

Berikut file `config.yml` pada ujicoba `featured image` sebelumnya

```yaml
media_folder: 'content/post/{{slug}}/' # Folder where user uploaded files should go
public_folder: '/img'
```

Setelah ditelusuri ketemulah kemungkinan penyebab kenapa `featured image` tidak mau muncul. Tema [`stack`](https://docs.stack.jimmycai.com/) yang saya gunakan akan melakukan `render` pada setiap post dengan format nama `index.md` yang ada di folder `content\post`.

Pengaturan ujicoba featured image sebelum ini tidak mengubah nama file post menjadi `index.md` melainkan tetap sesuai dengan `slug`-nya.

Sehingga untuk mengubah nama setiap post menjadi index, kita perlu melakukan konfigurasi ulang file `config.yml` menjadi berikut ini.

```yaml
media_folder: 'content/post/{{slug}}/' # Folder where user uploaded files should go
public_folder: '/img'

collections: 
  - name: 'post'
    label: 'Post'
    folder: 'content/post'
    path: '{{slug}}/index'
    media_folder: ''
    public_folder: ''
    create: true
    fields:
```

Semoga kali ini file konfigurasinya benar benar sehingga baik featured image maupun struktur postnya bisa muncul sesuai dengan keinginan.

Cheers.
