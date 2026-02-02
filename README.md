
---

# 📑 Project Documentation: REZCODE Official Website

Dokumentasi ini memberikan panduan teknis mendalam mengenai pengembangan, struktur, dan pemeliharaan website resmi **REZCODE**.

---

## 🏗️ Architecture Overview

Website ini dibangun menggunakan **Astro Island Architecture**, yang memisahkan elemen statis dan interaktif untuk mencapai performa maksimal.

### Core Stack

* **Framework:** Astro v4.x
* **Styling:** Tailwind CSS v4 (Alpha/Experimental)
* **Icons:** Lucide React & FontAwesome
* **Animation:** AOS.js, Custom CSS Keyframes
* **Data Handling:** JSON-driven components

---

## 📂 Directory Structure

Memahami organisasi file sangat penting untuk skalabilitas.

```bash
├── public/                # File statis (Favicon, Logo, Gambar Tim)
├── src/
│   ├── components/
│   │   └── Astro/         # Komponen UI utama (Hero, About, dll)
│   ├── data/
│   │   ├── site.json      # Metadata situs global
│   │   └── team.json      # Konfigurasi data anggota tim
│   ├── layouts/
│   │   └── MainLayout.astro # Template utama, SEO, & Global Scripts
│   ├── styles/
│   │   └── global.css     # Tailwind v4 @theme & Custom Animations
│   └── pages/
│       └── index.astro    # Entry point halaman utama
└── package.json           # Dependensi & Scripts

```

---

## 🔧 Technical Implementations

### 1. Global State & Interaction

Kami menggunakan fungsi JavaScript murni yang didaftarkan ke objek `window` untuk menangani interaksi global seperti **Coming Soon Modal**. Ini memungkinkan data dari JSON memicu UI tanpa perlu *state management* yang berat.

### 2. Performance Optimization

* **Content Visibility:** Menggunakan properti CSS `content-visibility: auto` pada bagian bawah halaman untuk mempercepat render awal.
* **Throttled Mouse Tracking:** Efek *Glow Card* menggunakan `requestAnimationFrame` dan `IntersectionObserver` agar tidak membebani CPU (terutama pada perangkat mobile).

### 3. Tailwind v4 @theme configuration

Sistem desain kami didefinisikan secara deklaratif di dalam `global.css`:

```css
@theme {
  --color-brand-dark: #0c0f19;
  --color-brand-primary: #3b65a4;
  --font-display: "Outfit", sans-serif;
}

```

---

## 🚀 Workflow Pengembangan

### Prasyarat

* Node.js (v18.0 atau lebih baru)
* NPM / PNPM / Bun

### Perintah Utama

| Command | Action |
| --- | --- |
| `npm run dev` | Menjalankan server lokal di `localhost:4321` |
| `npm run build` | Membangun situs untuk produksi (output di folder `dist/`) |
| `npm run preview` | Meninjau hasil build secara lokal |

---

## 👥 Maintenance & Contribution

### Menambah Anggota Tim Baru

Cukup tambahkan objek baru ke dalam `src/data/team.json`. Jika link sosial media belum tersedia, gunakan value `"#"` untuk memicu modal otomatis.

```json
{
  "name": "New Member",
  "role": "Position",
  "linkedin": "#", 
  "instagram": "#"
}

```

### Standar Penulisan Kode

* Gunakan **Astro Components** untuk elemen yang tidak memerlukan JS berat.
* Gunakan **Utility First** (Tailwind) untuk styling.
* Pastikan setiap gambar diproses melalui komponen `<Image />` dari `astro:assets`.

---

## 📄 Identitas & Lisensi

* **Owner:** Farell Rhezky Alvianto (FA)
* **Agency:** REZCODE
* **License:** MIT License

---

<p align="center">
<b>REZCODE</b> - <i>Crafting the future, one pixel at a time.</i>
</p>

---
