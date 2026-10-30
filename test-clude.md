## Rebuild-codespace-claude

Project ini memberi anda sedikit workflow membangun dan setup claude ai di lingkungan codespace github,dengan nama proyek yang sudah di arsipkan `Rebuild-codespace-claude`.

## Struktur folder

```
Rebuild-codespace-claude/
├── .devcontainer/
│   └── devcontainer.json      # setup Codespace + Claude Code
├── .claude/
│   └── settings.json          # pengaturan Claude Code untuk proyek (opsional)
├── docs/
│   └── setup.md               # catatan setup dan troubleshooting
├── src/                       # kode sumber proyek
├── tests/                     # file test
├── .gitignore
├── CLAUDE.md                  # instruksi proyek untuk Claude
└── README.md                  # dokumentasi untuk manusia
```

## File inti

**`.devcontainer/devcontainer.json`**

```json
{
  "name": "Rebuild Codespace Claude",
  "image": "mcr.microsoft.com/devcontainers/javascript-node:20",
  "features": {
    "ghcr.io/anthropics/devcontainer-features/claude-code:1.0": {}
  },
  "mounts": [
    "source=claude-code-config-${devcontainerId},target=/home/node/.claude,type=volume"
  ]
}
```

**`CLAUDE.md`** (dibaca Claude di awal sesi sebagai konteks proyek)

```markdown
# Rebuild-codespace-claude

## Tentang proyek
[Jelaskan singkat proyek ini dan tujuannya]

## Teknologi
- Bahasa/framework: [isi]
- Package manager: [npm / pip / dll.]

## Perintah penting
- Install dependensi: `npm install`
- Jalankan: `npm run dev`
- Test: `npm test`

## Aturan kerja
- Jangan ubah folder `.devcontainer/` tanpa konfirmasi
- Jangan commit file `.env` atau API key
- Tulis test untuk setiap fitur baru
- Jangan push sebelum saya review

## Struktur
- `src/` : kode utama
- `tests/` : test
- `docs/` : dokumentasi
```

**`README.md`**

```markdown
# Rebuild-codespace-claude

[Deskripsi singkat proyek]

## Memulai

1. Buka repo di GitHub → **Code → Codespaces → Create codespace**
2. Tunggu setup selesai
3. Jalankan `claude` di terminal

## Prasyarat

Simpan `ANTHROPIC_API_KEY` sebagai Codespaces secret:
GitHub → Settings → Codespaces → Secrets (beri akses ke repo ini).

## Pengembangan

    npm install
    npm run dev

## Lisensi

[Isi lisensi]
```

**`.gitignore`**

```
node_modules/
.env
.env.*
.claude/settings.local.json
```

## Catatan

- **`CLAUDE.md` paling berpengaruh** ke hasil kerja Claude. Isi dengan perintah build/test dan aturan yang spesifik untuk proyek Anda, bukan penjelasan umum.
- **Jangan menaruh API key** di file mana pun dalam repo. Cukup lewat Codespaces secret.
- Folder `src/`, `tests/`, dan perintah di `CLAUDE.md` perlu Anda sesuaikan dengan bahasa proyek Anda.

