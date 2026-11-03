# Catatan Minggu 03: Inheritance

## Yang saya kerjakan
Minggu ini saya mengisi tiga kelas turunan dari Aset, yaitu Laptop, Ruang, dan AlatLab. Di tiap kelas, saya menambahkan field baru, mengisinya lewat konstruktor, lalu membuat getter-nya. Konstruktor nya juga saya beri pengecekan, jadi kalau datanya tidak valid akan melempar IllegalArgumentException. Terakhir saya meng-override getJenis() supaya tiap kelas mengembalikan jenisnya sendiri.

## Keputusan desain
- Validasi saya taruh di konstruktor, jadi objek yang datanya salah tidak akan pernah terbentuk.
- Untuk teks yang tidak boleh kosong (spesifikasi, nomor inventaris, laboratorium), saya cek null dan juga string yang isinya cuma spasi, makanya pakai trim().isEmpty().
- Untuk Ruang, kapasitas harus lebih dari 0, sesuai komentar di soal.
- Untuk AlatLab, tingkatRisiko tidak boleh null karena nanti kemungkinan dipakai untuk menghitung denda.
- Semua field saya buat private dan hanya bisa dibaca lewat getter, supaya nilainya tidak diubah sembarangan dari luar kelas.
- getJenis() saya tulis dengan @Override supaya kalau namanya atau tipenya salah, langsung ketahuan saat kompilasi.
## Kendala
saya rada ragu apakah getJenis() boleh ditulis tanpa public. Setelah dicari tahu, ternyata method yang di-override tidak boleh punya akses yang lebih sempit dari method di kelas induknya. Kalau di Aset sudah public, di kelas turunan juga harus public, kalau tidak akan error. Satu lagi, saya belum yakin TingkatRisiko itu enum atau kelas biasa, jadi saya cek dulu file-nya sebelum memakainya di AlatLab.
## Penggunaan AI
- Alat yang dipakai: Claude
- Bagian yang dibantu AI: konstruktor, getter, dan getJenis() di kelas Laptop, Ruang, dan AlatLab
- Prompt utama: Saya tempelkan kerangka kelas Laptop yang masih berisi TODO minggu 3, lalu hal yang sama untuk Ruang dan AlatLab
- Yang saya ubah atau tolak dari saran AI, dan alasannya:versi pertama kodenya memakai final, isBlank(), dan trim() saat menyimpan nilai. Saya minta disederhanakan karena belum belajar semuanya di kelas, jadi diganti dengan trim().isEmpty() dan field biasa. Pesan error juga saya minta dipersingkat.
- Satu hal yang saya pahami lebih baik sekarang:kenapa validasi sebaiknya ada di konstruktor, dan aturan bahwa method yang di-override tidak boleh lebih tertutup aksesnya daripada method di kelas induk.
