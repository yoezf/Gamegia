# Lumina Rift — Legenda Penjaga Kristal

Game browser 2D **side-scrolling Action RPG** dalam **satu file** (`index.html`): HTML5 Canvas + JavaScript murni. Tanpa backend, tanpa library, tanpa aset gambar. Semua sprite, efek, dan suara digambar atau dibuat lewat kode.

**Main sekarang:** https://yoezf.github.io/Gamegia/
**Main lokal:** buka `index.html` di browser (tidak perlu server).

Semua nama, karakter, desain, dan musik di game ini orisinal.

## Fitur

- **4 hero bisa dimainkan:** Kael (pendekar pedang), Lyra (penyihir), Noir (ksatria pedang raksasa), dan Niken (idol fantasi Jawa dengan dua stance).
- **4 stage:** Hutan Sylvaris, Kastil Aurelion, Dungeon Kristal, dan Takhta Bayangan (boss Valgor, dengan fase 2 mengamuk). Tiap stage punya gelombang monster dan portal ke stage berikutnya.
- **Combat real-time:** combo, 4 skill + ultimate per hero, critical, hit stun, knockback, hit stop, screen shake, partikel.
- **Sistem RPG:** EXP dan level, koin, inventory ramuan, toko, upgrade status permanen.
- **Simpan progress** otomatis dan manual (localStorage), menu utama, pause, layar menang/kalah.
- **Dukungan HP/tablet:** kontrol layar sentuh muncul otomatis.

### Karakter khusus

- **Noir** — movement lewat urutan arah (tanpa tombol dash): Dash, Backstep, Rocket, Step, Shadow Step, Demon Step, Platform Step, plus Block/Counter dan Charged Slash. Ada **Mode Latihan** di menu Pause (panel teknik, log input, jendela waktu input bisa diatur).
- **Niken** — dua stance yang bisa diganti kapan saja dengan **Shift**:
  - *Performance Mode* (mic-staff): heal, regenerasi, buff ATK/DEF/kecepatan serang/pengurang damage untuk party.
  - *Fighting Mode* (Lumina Rings): combo cepat, akrobatik, Flying Kick, Counter.
  - Bermain dengan dua rekan AI (Kael dan Lyra) agar efek support benar-benar berfungsi.

## Kontrol (keyboard)

| Tombol | Fungsi |
|---|---|
| A / D | Gerak kiri / kanan |
| W | Lompat (tekan 2x = double jump) |
| S | Turun dari platform |
| J | Serang (tekan berulang = combo) |
| K / L / U | Skill 1 / 2 / 3 |
| I | Ultimate |
| Space | Dash (Kael, Lyra) / lompat (Noir, Niken) |
| Z | Tambahan: ketuk = serang, tahan lalu lepas tahap 1–4 = Skill 1–4 |
| 1 / 2 | Ramuan HP / MP |
| Esc atau P | Pause |
| M | Suara on/off |

**Noir dan Niken:** Dash = ketuk **→ →** (atau **← ←**), Backstep = **↓ lalu arah belakang**, **E** = Block (J setelah Block = Counter).
**Noir:** Rocket = **→ lalu →+↑**, Step = **→ , →+↑ , ↓**, Shadow Step = **(→+↑) ↔ (→+↓)** berulang, Demon Step = Step kanan lalu Step kiri, Platform Step = Step + **↑** di akhir.
**Niken:** **Shift** = ganti Performance ⇄ Fighting.

## Kontrol sentuh

Di perangkat sentuh muncul tombol ◀ ▼ ▶, SERANG, LOMPAT, DASH, K, L, U, ULT, MODE (Niken), BLOK (Noir/Niken), ⏸, serta tombol ramuan HP dan MP. Mode landscape disarankan. Di desktop, tambahkan `?touch=1` ke alamat untuk mencobanya.

Belum tersedia di versi sentuh: Z tahan-lepas, Backstep, dan teknik gerak Noir yang butuh urutan arah.

## Catatan teknis

- Satu file, ±210 KB; `requestAnimationFrame` dengan langkah waktu tetap 60 Hz.
- Fisika platformer (gravitasi, platform satu arah, double jump), hitbox/hurtbox terpisah, input buffering, jendela combo/cancel, sistem partikel, efek glow lewat sprite cache.
- Animasi karakter digambar prosedural di Canvas (rangka, pose, dan transisi dihitung di kode).
- Musik dan efek suara dihasilkan lewat Web Audio API.
- Save disimpan di `localStorage` dengan kunci `luminaRift.save.v1`.

## Menjalankan dan mengembangkan

Tidak perlu build. Edit `index.html`, lalu muat ulang browser. Untuk server lokal opsional:

```bash
python -m http.server 8765
```

lalu buka http://localhost:8765.
