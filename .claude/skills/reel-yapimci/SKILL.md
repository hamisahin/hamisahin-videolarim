---
name: reel-yapimci
description: Remotion ile Reels/Shorts ya da YouTube videosu üretir. Metin, ses kaydı ya da uzun video verilince kullan.
---

# Reel yapımcısı

# Önce netleştir
- Platform: Reels/Shorts 1080x1920 · YouTube 1920x1080 · 30 fps
- Videoyu tek cümleyle yaz: "Bu video: ___."

# Akış
1. Metni sahnelere böl: her cümle bir sahne, 2–4 sn.
2. Ses kaydı varsa public/ klasörüne koy, kelime zamanlarını çıkar (@remotion/install-whisper-cpp), sahneleri sese hizala.
3. Her sahne ayrı bileşen; <Series> ile diz.
4. Animasyon sadece useCurrentFrame + interpolate / spring. CSS animation ve transition kullanma.
5. Altyazı alt üçte birde, en fazla 3 kelime, konuşulan kelime vurgulu.
6. Uzun videodan klip: önce transkript, en güçlü 30–45 sn bölümü seç, <Video trimBefore> ile kes.
7. Sahne başına 1 hareket (zoom, kayma, sayaç, beliren kart). Ekran hiçbir an boş kalmasın.

# Kontrol
- Render'dan önce 4–6 kare:
  npx remotion still src/index.ts <Ad> kare.png --frame=<N>
- Yazı taşmıyor, altyazı sesle aynı anda.
- Render: npx remotion render src/index.ts <Ad> out/video.mp4

# Kurallar
- Telifli müzik ya da başkasının videosunu koyma.
- Ekrana yazılan her sayı metinden gelsin.
