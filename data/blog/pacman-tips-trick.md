---
title: 'Tips dan Trik Perintah Pacman (Package Manager Arch Linux)'
date: '2021-08-01'
lastmod: '2021-08-01'
tags: ['guide', 'tips&trik', 'pacman']
draft: false
summary: 'Di artikel ini saya mendokumentasikan tips dan trik menggunakan perintah pacman'
images: ['/static/images/canada/mountains.jpg', '/static/images/canada/toronto.jpg']
---

# Introduction

Sebelum tau apa itu pacman, coba baca dulu wiki arch ini <a href="https://wiki.archlinux.org/title/pacman">pacman</a>







Mencari semua paket yang tersedia dan infonya, lalu `enter` untuk menginstall paket yang dipilih :
```
pacman -Slq | fzf --multi --preview 'pacman -Si {1}' | xargs -ro sudo pacman -Sy
```

Mencari semua paket yang terinstall, dan `enter` untuk me-remove paket yang dipilih :
```
pacman -Qq | fzf --multi --preview 'pacman -Qi {1}' | xargs -ro sudo pacman -Rns
```

```
pacman -Slq | fzf --multi --preview 'cat <(pacman -Si {1}) <(pacman -Fl {1} | awk "{print \$2}")' | xargs -ro sudo pacman -S
```



