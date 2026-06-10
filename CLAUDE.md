# RenderAI Frontend

## Tek dosya: `index.html` (~2800+ satır)
Vercel'de host: renderai-frontend.vercel.app
Backend API: https://web-production-8c34d.up.railway.app

## Renk teması
- Body: #E8E4DC, Panels: #FAFAF8, Header: #1A1A16
- Terracotta accent: #9A6558, Sage: #7A8B6A

## Sekmeler
1. **Render** — GPT interior/exterior render (startRender())
2. **Kat Planı** — Gemini/NanoBanana floor plan (startFloorPlan())
3. **Büyüt** — upscale (startUpscale())
4. **Geliştir** — enhance (startEnhance())
5. **Mevsimler** — seasons (startSeasons())
6. **Video** — animate (startVideo())

## Kritik fonksiyon
`resizeIfNeeded(file, maxDim=2048)` — Canvas API ile büyük görseli yüklemeden önce küçült.
**Tüm formData.append('image', ...) satırlarından önce çağrılmalı.**
- startRender() → YAPILDI
- startFloorPlan() (fpFile, ~satır 2331) → YAPILMADI
- startUpscale(), startEnhance(), startSeasons(), startVideo() → YAPILMADI

## Interior presets
- Işık, Atmosfer, Malzeme sekmeleri (zemin/duvar override prompts)

## Exterior presets  
- Mevsim, Zaman, Hava, Gökyüzü, Işık, Çevre, Görüntü, Malzeme sekmeleri

## Kural
Bir şeyi değiştirmeden önce "bunu değiştireceğim, onaylıyor musun?" diye sor.
Sadece istenen kısmı değiştir — başka hiçbir şeye dokunma.
