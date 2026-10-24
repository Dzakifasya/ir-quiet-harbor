# IR-26-YDZYG · Operasi QUIET HARBOR
**Eksfiltrasi Data oleh Orang Dalam** — SEV-2 · Tinggi

Responder: **Dzaki Fasya** (110225165)  
Platform: Windows 11 Enterprise · Web proxy · File server SMB

## Situasi
Pukul **20:27:49 WIB**, sistem DLP dan web proxy DPM memicu alert: workstation
**WS-RND-030** (`10.41.40.172`) di divisi R&D mengunggah data dalam volume besar ke layanan penyimpanan
publik di luar jam kerja. Workstation tersebut dipakai oleh **novi.rahmawati**, engineer senior yang
minggu lalu mengajukan pengunduran diri dan akan bergabung dengan kompetitor.

Anda adalah **first responder** CSIRT. Pukul **21:01:44 WIB** Anda tiba di lantai R&D
bersama perwakilan HR. Workstation masih menyala dan tidak terkunci; sebuah flashdisk tergeletak
di meja. novi.rahmawati sedang berada di pantry dan belum mengetahui adanya investigasi.

## Log tindakan di TKP
| Waktu (WIB) | Catatan |
|---|---|
| 20:27 | DLP & proxy memicu alert: unggahan volume besar dari WS-RND-030 (10.41.40.172) ke layanan penyimpanan publik. |
| 21:01 | Tim CSIRT tiba di lantai R&D. WS-RND-030 menyala dan tidak terkunci; novi.rahmawati sedang di pantry. |
| 21:03 | Surat tugas investigasi ditandatangani Direktur, lingkup dibatasi pada aset perusahaan, dan Legal mendampingi tim. |
| 21:04 | Tanpa konfrontasi, live response dilakukan di WS-RND-030 dengan pendampingan HR selagi novi.rahmawati berada di pantry. HR & Legal diberi tahu. |
| 21:06 | Jam sistem WS-RND-030 menunjukkan 21:11:13, jam referensi tim 21:06:48. Selisih +00:04:25 (jam sistem − referensi) dicatat sebagai baris tersendiri. Jam sistem tidak diubah. |
| 21:11 | RAM WS-RND-030 (16 GB) diakuisisi dengan WinPmem ke media eksternal; hash SHA-256 dicatat. |
| 21:32 | Flashdisk difoto di posisinya, dimasukkan ke kantong anti-statis bersegel, dan dicatat di formulir chain of custody. Pemeriksaan dilakukan di lab melalui write blocker. |
| 22:31 | Seluruh bukti di-hash, disegel, dan diserahkan ke evidence custodian. |

## Bukti
| ID | Bukti | Sumber | Status |
|---|---|---|---|
| `EV-001` | Log web proxy (UTC) | PROXY-01 | Diamankan |
| `EV-002` | Audit akses share RnD | FS-RND-01 | Diamankan |
| `EV-003` | Log instalasi perangkat | WS-RND-030 | Diamankan |
| `EV-004` | Daftar proses + command line | WS-RND-030 | Diamankan |
| `EV-005` | Strings dari image RAM (16 GB) | WS-RND-030 | Diamankan |
| `EV-006` | Listing isi flashdisk | Flashdisk di meja | Diamankan |

Catatan format waktu: log yang berasal dari host memakai **jam host** (belum dikoreksi). Lihat `CATATAN_RESPONDER.txt` untuk selisih jam bila tercatat.

## Pertanyaan analisis
| ID | Pertanyaan |
|---|---|
| **F1** | Akun yang membaca folder Rahasia di luar jam kerja (format DOMAIN\akun) |
| **F2** | Host tujuan eksfiltrasi |
| **F3** | Total byte yang diunggah (jumlah kolom cs-bytes) dari IP workstation ke host tujuan |
| **F4** | Nama file rahasia pertama yang dibaca pelaku malam itu |
| **F5** | Nomor seri flashdisk yang dicolokkan malam itu |
| **F6** | Waktu flashdisk itu pertama kali dicolokkan, WIB terkoreksi clock drift (HH:MM:SS) |
| **F7** | Nama proses alat eksfiltrasi dan PID-nya (contoh `nama.exe 1234`) |
| **F8** | Password arsip 7-Zip yang dipakai pelaku |

## Verifikasi integritas
Hitung SHA-256 setiap file di `bukti/` dan bandingkan dengan `MANIFEST_AKUISISI.json`.

```bash
sha256sum bukti/*
```

```powershell
Get-FileHash .\bukti\* -Algorithm SHA256 | Format-Table Hash, Path
```

## Format laporan
Kirim sebagai komentar pada issue kasus Anda:

```yaml
/submit
temuan:
  F1: 
  F2: 
  F3: 
  F4: 
  F5: 
  F6: 
  F7: 
  F8: 
integritas:
  bukti_bermasalah: EV-00?
  sha256_aktual: 
catatan: |
  Ringkasan singkat analisis Anda (opsional, dicetak di laporan insiden).
```
