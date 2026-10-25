# Catatan Minggu 02: Struktur OOP: Class, Object, Encapsulation

## Yang saya kerjakan
Saya melengkapi kelas Aset: field kode, nama, status, dan kondisi dibuat private, lalu saya tambah konstruktor, getter, setter, dan validasi. Status awalnya TERSEDIA dan kondisi awalnya BAIK

## Keputusan desain
(Apa yang Anda putuskan dan kenapa. Rujuk docs/asumsi.md bila perlu.)

## Kendala
Saya rada ragu apakah field kondisi perlu dibuat public. Ternyata tidak, karena sudah ada getter dan setter, dan field public malah melanggar encapsulation. Saya juga memilih antara isBlank() dan trim()
## Penggunaan AI
- Alat yang dipakai: Claude
- Bagian yang dibantu AI: kelas Aset (konstruktor, getter/setter, validasi) dan draf catatan ini
- Prompt utama: saya menempelkan kerangka Aset.java berisi TODO minggu 2, bertanya apakah kondisi juga perlu diisi, lalu minta dibuatkan catatan sesuai format.
- Yang saya ubah atau tolak dari saran AI, dan alasannya: saya menulis ulang helper validasi dengan isBlank(), mengisi bisaDipinjam() sendiri, dan belum menjadikan Aset abstract karena minggu 3 dan 4 belum selesai.
- Satu hal yang saya pahami lebih baik sekarang: field private dengan setter yang divalidasi membuat objek tidak bisa berada dalam keadaan yang tidak valid.