# PROMPT — Copywriting Rebalance
# Lanjutan dari: prompt-solo-software-house.md
# Tujuan: rebalance tone copy yang sudah di-generate agent — lebih punchy,
# meyakinkan, tapi tidak kehilangan rasa respectful ke calon klien.

---

## CONTEXT (jangan skip ini)

Copy ini untuk landing page solo software house yang dibangun dengan Astro.
Pemiliknya satu orang, developer, menggunakan AI-assisted workflow (vibe coding).
Target pembaca: founder startup, pemilik bisnis, atau decision maker di perusahaan
— mereka sibuk, skeptis terhadap klaim kosong, dan menghargai kejujuran.

Copy yang sudah ada (dari build prompt sebelumnya) punya karakter:
- Menggunakan "gue/lo" secara konsisten → terasa casual tapi kadang terlalu
  santai untuk konteks bisnis yang serius
- Beberapa kalimat terlalu panjang untuk headline atau subtext
- Nada di beberapa bagian condong ke "bro culture" yang bisa mengecualikan
  sebagian audiens
- Kejujuran di FAQ sudah bagus — jangan diubah substansinya

Tujuan rebalance ini bukan mengubah karakter — tapi menyempurnakan register-nya
agar terasa seperti orang yang percaya diri dan kompeten, bukan orang yang
perlu membuktikan diri.

---

## TONE TARGET

Bayangkan dua ujung spektrum:

  [terlalu casual]                                    [terlalu korporat]
  "Gue satu orang, tapi gue bisa kok"    vs    "Kami berkomitmen memberikan solusi"

Target ada di 70% ke kiri — tetap personal dan direct, tapi cukup padat dan
tenang untuk dibaca oleh seseorang yang mau mengeluarkan Rp 20–50 juta.

Konkretnya:
- PUNCHY: kalimat pendek, verb aktif, tidak ada kata pengantar yang tidak perlu
- MEYAKINKAN: klaim didukung angka atau mekanisme spesifik, bukan adjektif
- RESPECTFUL: tidak menggurui, tidak meremehkan agency lain, tidak hyperbolic

---

## ATURAN PER ELEMEN COPY

### Headlines (H1, H2)
- Maksimal 6 kata per baris
- Hindari pertanyaan retorik kecuali jawabannya langsung ada di baris berikutnya
- "Bukan X. Bukan Y." boleh dipakai tapi maksimal sekali di seluruh halaman
- Italic (Instrument Serif) dipakai untuk kontras emosional, bukan dekorasi

### Subtext / body copy
- Maksimal 2 kalimat per blok
- Satu ide per kalimat
- Kalimat pertama: fakta atau klaim. Kalimat kedua: konsekuensinya bagi klien.
- Jangan mulai dengan "Gue" — terlalu defensif sebagai pembuka
- Boleh pakai "Anda" jika konteksnya formal (pricing, CTA utama)

### CTA (Call to Action)
- Verb dulu: "Mulai dari sini", "Diskusikan proyek", "Kirim brief"
- Hindari "Yuk", "Ayo", "Cobain" — terlalu ringan untuk konteks transaksi ini
- Arrow (→) boleh dipakai, tapi tidak setiap tombol

### Service descriptions
- Pola: [apa yang dibuat] + [outcome konkret bagi klien]
- Jangan mulai dengan "Tambahin" atau "Bikin" — terlalu imperatif
- Stack names tetap apa adanya (Next.js, Supabase, dll.)

### FAQ answers
- Pertahankan kejujuran substansinya — ini bagian terkuat dari copy yang ada
- Boleh diperketat kalimatnya tapi jangan hilangkan pengakuan risiko
- "Gue" masih oke di FAQ — ini satu-satunya tempat yang beneran personal

### Testimonials
- Jangan rewrite — hanya tighten jika ada kata mubazir
- Pertahankan voice asli pembicara

### Meta description & JSON-LD descriptions
- Maksimal 155 karakter untuk meta description
- Bahasa netral, bukan casual — ini yang dibaca Google dan WhatsApp preview
- Tidak pakai "gue/lo"

---

## COPY YANG PERLU DIREVIEW

Berikut semua copy dari build prompt sebelumnya yang perlu di-rebalance.
Jangan ubah struktur data TypeScript-nya — hanya ubah nilai string yang
merupakan copy facing user.

### HERO
```
Badge:     "Available for project — [YEAR]"
H1:        "Software / built fast, / shipped real."
Subtext:   "Satu orang. Full-stack. Vibe coding dengan AI. Hasilnya bukan
            prototipe — tapi produk yang beneran jalan dan siap scale."
CTA 1:     "Cerita dulu →"
CTA 2:     "Lihat portofolio"
Stat desc: "MVP siap launch"
Stat desc: "Dari berbagai industri"
Status:    "Terbuka 1 slot project baru"
Status sub:"Estimasi mulai: awal bulan depan"
```

### ABOUT
```
H2:        "Bukan agency. / Bukan freelancer. / Sesuatu di antaranya."
Body 1:    "Gue satu orang — tapi dengan AI sebagai co-developer, output gue
            setara tim kecil. Vibe coding bukan berarti asal-asalan; ini tentang
            kecepatan yang terkontrol."
Body 2:    "Lo dapet komunikasi langsung ke pembuatnya, bukan account manager
            yang forward email. Revisi cepat. Prioritas jelas. Keputusan teknis
            yang bisa lo mengerti."
Body 3:    "Cocok untuk startup awal, bisnis yang mau digital, atau siapa pun
            yang butuh produk nyata dalam waktu singkat."
Process:   "Gue dengerin kebutuhan lo, tanya hal yang perlu ditanya, dan
            langsung kasih gambaran apakah ini bisa dibuat dan berapa lama."
Process:   "Gue kirim dokumen scope yang jelas: fitur apa yang dibuat, timeline
            per milestone, dan harga fixed — bukan estimasi."
Process:   "Lo dapet akses ke staging environment dari hari pertama. Update
            mingguan. Feedback langsung dieksekusi, bukan dimasukkin backlog."
Process:   "Deploy, dokumentasi, dan training singkat. Lo punya full ownership
            atas kode dan infrastruktur."
```

### SERVICES
```
Service desc 1: "Dari ide ke produk yang bisa dipakai user. Full-stack dengan
                 auth, database, payment, dan dashboard admin."
Service desc 2: "Tambahin AI ke produk lo yang sudah ada — chatbot, summarizer,
                 analyzer — bukan gimmick, tapi yang beneran berguna."
Service desc 3: "Yang convert. Bukan template — didesain khusus untuk cerita
                 bisnis lo dengan performa dan animasi yang proper."
Service desc 4: "CRM sederhana, inventory system, dashboard data — software
                 internal yang bikin tim lo lebih efisien."
Service desc 5: "REST API, webhook, integrasi third-party. Bisa standalone atau
                 sebagai backbone aplikasi lo."
Service desc 6: "Toko online dengan checkout yang smooth, manajemen produk, dan
                 integrasi payment gateway lokal."
```

### WORKS
```
Work desc 1: "Web app untuk manajemen karyawan dengan absensi QR, kalkulasi
              payroll otomatis, dan laporan bulanan."
Work desc 2: "Chatbot yang bisa jawab pertanyaan produk, cek status order, dan
              escalate ke CS manusia kalau perlu."
Work desc 3: "Site multi-halaman dengan galeri, kalkulator KPR, dan sistem
              booking kunjungan langsung terintegrasi WhatsApp."
Work desc 4: "Kasir digital tablet-friendly dengan tracking stok real-time,
              laporan harian, dan alert stok menipis."
```

### PRICING
```
Pricing desc 1: "Untuk landing page, company profile, atau produk digital yang
                 lingkupnya jelas dan terbatas."
Pricing desc 2: "Web app atau SaaS MVP dengan fitur yang proper. Yang kebanyakan
                 startup dan bisnis butuh."
Pricing desc 3: "Lo butuh developer yang bisa diandalkan tiap bulan — buat fitur
                 baru, bugfix, atau improvisasi."
```

### FAQ
```
Q1: "Vibe coding itu kualitasnya bisa dipercaya?"
A1: "Vibe coding bukan berarti asal prompt dan berharap. Gue tetap review setiap
     baris kode yang di-generate AI, debug secara manual, dan pastiin struktur
     proyeknya bersih dan maintainable. AI mempercepat prosesnya — bukan
     menggantikan judgment-nya."

Q2: "Gimana kalau lo sakit atau ada halangan?"
A2: "Ini risiko nyata dari kerja dengan satu orang. Makanya gue selalu kasih
     buffer waktu di setiap proyek, dan semua kode serta dokumentasi tersimpan
     di repo yang lo punya akses penuh — jadi kalau ada apa-apa, lo tidak
     tersandera."

Q3: "Kode-nya gue punya setelah proyek selesai?"
A3: "100%. Gue transfer full ownership — kode, repo, domain, hosting credentials.
     Lo bebas bawa ke developer lain, modifikasi sendiri, atau apapun. Tidak ada
     vendor lock-in."

Q4: "Bisa minta revisi setelah launch?"
A4: "Setiap paket punya periode support post-launch. Di luar itu, lo bisa masuk
     ke paket retainer atau kita buat kesepakatan per-revisi. Gue tidak
     menghilang setelah delivery."

Q5: "Bisa handle proyek dari luar kota?"
A5: "Ya, semua proyek dijalankan remote. Lo di Jakarta, Surabaya, Bali, atau
     bahkan luar negeri — tidak masalah. Komunikasi via WhatsApp, Notion, dan
     Google Meet."
```

### CTA & FOOTER
```
CTA H2:   "Punya ide? / Kita bikin nyata."
CTA sub:  "Drop email lo, gue biasanya balas dalam 24 jam. Kalau proyek lo
           cocok, kita bisa langsung discovery call minggu ini."
CTA btn:  "Kirim →"
Footer:   "© [YEAR] — Solo, tapi serius."
```

### META (SEO)
```
Title:       "[YOUR NAME] — Solo Software House"
Description: "Software house satu orang. Web app, SaaS MVP, dan AI integration
              dengan delivery 3–6 minggu. Vibe coding meets production quality."
```

---

## AGENCY NAME & MONOGRAM — APPLY EVERYWHERE

Nama resmi agency: **Kodacore**
Monogram: **KDCR**

### Aturan penulisan

| Konteks | Tampilan | Contoh |
|---|---|---|
| Nama penuh di heading, about, footer | `Kodacore` | "Ini Kodacore." |
| Logo / nav wordmark | `Kodacore` — weight 800, huruf pertama kapital saja | `Kodacore` |
| Monogram di nav (jika pakai versi singkat) | `KDCR` — semua kapital, letter-spacing 0.15em | `KDCR` |
| Meta title | `Kodacore — Solo Software House` | |
| JSON-LD `name` field | `Kodacore` | |
| Footer copyright | `© [YEAR] Kodacore` | |
| Domain placeholder | `kodacore.dev` atau `kodacore.id` (pilih salah satu, konsisten) | |

### Yang harus diupdate

Ganti semua instance `[YOUR NAME]`, `KD.`, dan `KD` di seluruh copy dan kode dengan:
- Nama panjang → `Kodacore`
- Monogram / singkat → `KDCR`
- Nav logo saat ini `KD.` → ubah ke `KDCR` dengan dot accent tetap pada karakter terakhir: `KDCR.`
  (dot warna `var(--accent)`, huruf `KDCR` warna `var(--fg)`)

### Jangan lakukan ini
- Jangan tulis `KodaCore` (C kapital di tengah) — salah
- Jangan tulis `kodacore` lowercase di headline atau nama resmi
- Jangan singkat jadi `Koda` di copy manapun kecuali ada instruksi eksplisit
- Monogram `KDCR` hanya untuk elemen UI compact (nav, favicon label, watermark)
  — jangan dipakai di body copy atau headline

---

## OUTPUT FORMAT

Kembalikan semua copy di atas dalam format yang sama persis —
struktur label yang sama, tapi nilai stringnya sudah direbalance.

Setelah setiap section, tambahkan satu baris:
→ RATIONALE: [max 15 kata, apa yang berubah dan kenapa]

Jangan tambahkan penjelasan panjang. Langsung copy-nya.

Jangan ubah apapun di luar string copy — struktur TypeScript, CSS variables,
nama komponen, dan tech stack tidak boleh untouchable.

---

*Prompt ini adalah lanjutan dari prompt-solo-software-house.md.
 Keduanya harus dijalankan secara berurutan: build dulu, rebalance copy sesudahnya.*
