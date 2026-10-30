// tessting-claude

install diterminal bawaan
```bash
curl -fsSL https://claude.ai/install.sh | bash
```
Lalu muat ulang shell supaya PATH terbaca:
```bash
source ~/.bashrc   # atau: source ~/.zshrc
claude --version
```
kalo kamu mau npm (butuh Node.js 18+):
```bash
npm install -g @anthropic-ai/claude-code
```
Di terminal Codespace:
``bash
echo ${ANTHROPIC_API_KEY:+terdeteksi}
claude
```
Cek variabel terdeteksi
```bash
echo ${ANTHROPIC_API_KEY:+terdeteksi}
```

kalo ada.tambahakan kunci API-KEY
```bash
export ANTHROPIC_API_KEY="sk-isi api-key"
claude
```
Kalau mau Manual jalankan ini
``json
{
  "permissions": {
    "defaultMode": "default"
  }
}
``
