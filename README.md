# Analisis Kerentanan WebGoat

Dokumentasi analisis keamanan pada instance WebGoat `webgoat.ilkom.unej.ac.id/WebGoat` menggunakan pendekatan black-box dan white-box.

## Ruang Lingkup

- Target: `https://webgoat.ilkom.unej.ac.id/WebGoat`
- Source code pembanding: [WebGoat/WebGoat](https://github.com/WebGoat/WebGoat)
- Tools: Nuclei, Naabu, Burp Suite, FFUF

## Temuan

### Nuclei

- `addeventlistener-detect`: informasi penggunaan `addEventListener`.
- `missing-cookie-samesite-strict`: cookie sesi terdeteksi menggunakan `SameSite=None`, meski telah memakai `Secure` dan `HttpOnly`.
- `ssl-issuer`: sertifikat TLS diterbitkan Let's Encrypt.
- `ssl-dns-names`: sertifikat mencakup hostname target.

### Analisis Source Code

Dokumentasi/source code WebGoat menunjukkan materi atau skenario terkait:

- Session hijacking dan penyalahgunaan cookie sesi.
- Path traversal.
- SQL injection.
- Modifikasi atau pengujian HTTP method/header.

### Port Scanning

Hasil pemindaian berbeda berdasarkan waktu pengujian. Catatan laporan mencatat empat port terbuka pada satu pengujian dan tujuh port terbuka pada pengujian lain. Hasil ini perlu divalidasi ulang sebelum dianggap final.

## Catatan Etika

WebGoat memang dibuat sebagai aplikasi latihan keamanan. Pengujian pada target lain wajib memiliki izin tertulis, scope jelas, rate limit, dan prosedur pelaporan. Jangan gunakan cookie, kredensial, atau data pengguna nyata.

## Referensi

- [OWASP WebGoat](https://github.com/WebGoat/WebGoat)
- [OWASP CSRF Prevention](https://owasp.org/www-community/attacks/csrf)
- [MDN `SameSite` cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie/SameSite)

## Sumber Dokumentasi

Laporan asli tersedia pada file [`Analisis Kerentanan atau VULN Pada Web webgoat.docx`](./Analisis%20Kerentanan%20atau%20VULN%20Pada%20Web%20webgoat.docx).
