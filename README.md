# JuaraTKA Content Repository

Repositori konten untuk aplikasi JuaraTKA.

## Struktur

```
juaratka-content/
├── config.json                       # Metadata versi + jumlah konten
├── materi/
│   ├── matematika.json               # 20 materi Matematika
│   └── indonesia.json                # 8 materi Bahasa Indonesia
└── soal-latihan/
    ├── matematika-bilangan.json
    ├── matematika-geometri.json
    ├── matematika-pengukuran.json
    ├── matematika-data.json
    ├── indonesia-tekstual.json
    ├── indonesia-inferensial.json
    └── indonesia-evaluasi.json
```

## Cara Menambah Soal

Buka file JSON topik yang mau ditambah (misal `soal-latihan/matematika-bilangan.json`).

Struktur file:
```json
{
  "mapel": "matematika",
  "topik": "bilangan",
  "count": 10,
  "updated": "2026-01-15",
  "soal": [
    {
      "question": "Pertanyaan...",
      "options": ["A", "B", "C", "D"],
      "answer": 0,
      "explanation": "Pembahasan...",
      "level": "dasar"
    }
  ]
}
```

Field wajib:
- `question` (string) — teks soal
- `options` (array) — pilihan jawaban
- `answer` (integer) — index jawaban benar (0-based)
- `explanation` (string) — pembahasan
- `level` (string) — "dasar", "rutin", atau "ujian"

Setelah edit:
1. Save file
2. Commit + push ke GitHub
3. jsDelivr auto-update dalam 5-10 menit

## Update Rutin

Setiap tambah soal, update field `count` dan `updated` di JSON header.

## CDN URL

Setelah repo di-push, file bisa diakses via:
```
https://cdn.jsdelivr.net/gh/USERNAME/juaratka-content@latest/soal-latihan/FILE.json
```
