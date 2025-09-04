# Panduan Git dalam Bahasa Indonesia

## Mengatasi Masalah Remote Repository yang Berbeda

**Pertanyaan**: "Gimana caranya saya kan sebelumnya sudah punya repo ini tapi remotenya bukan ke sini, terus saya ingin mengambil lagi repo yang ini untuk di pull gimana caranya?"

### Solusi Cepat

Jika Anda sudah punya repository ini di lokal tapi remote-nya mengarah ke tempat lain, ikuti langkah berikut:

1. **Cek remote saat ini**:
   ```bash
   git remote -v
   ```

2. **Ubah remote URL ke repository yang benar**:
   ```bash
   git remote set-url origin https://github.com/Has-Law/Haslaw-user.git
   ```

3. **Pull perubahan terbaru**:
   ```bash
   git pull origin main
   ```

### Alternatif: Clone Ulang

Jika cara di atas tidak berhasil atau Anda ingin mulai bersih:

1. **Backup perubahan lokal** (jika ada):
   ```bash
   git stash
   ```

2. **Clone repository ke folder baru**:
   ```bash
   git clone https://github.com/Has-Law/Haslaw-user.git haslaw-user-baru
   cd haslaw-user-baru
   ```

3. **Kembalikan perubahan** dari backup jika diperlukan:
   ```bash
   git stash pop
   ```

### Mengatasi Konflik

Jika muncul konflik saat pull:
1. Lihat file yang konflik: `git status`
2. Edit file tersebut untuk menyelesaikan konflik
3. Tandai sebagai selesai: `git add .`
4. Commit: `git commit -m "Selesaikan konflik merge"`

### Setup Development

Setelah repository berhasil diupdate:

```bash
# Install dependencies
npm install

# Jalankan development server
npm run dev

# Build project
npm run build
```

Untuk panduan Git yang lebih lengkap, lihat [GIT_WORKFLOW.md](./GIT_WORKFLOW.md).