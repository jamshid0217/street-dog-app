# STREET DOG — ishga tushirish

Endi buyurtmalar ilovadan **to'g'ridan-to'g'ri Telegramga emas, botingizdagi serverga** boradi.
Shuning uchun `bot.py` **doim ishlab turishi kerak** (kompyuter yoki hosting/VPS'da).

## 1. O'rnatish
```
pip install -r requirements.txt
```

## 2. Sozlash
`.env.example` faylini `.env` deb nusxalang va `BOT_TOKEN=` ga @BotFather bergan tokenni yozing.
(`index.html` va eski `bot.py` dagi tokenlar ochiq qolgan edi — @BotFather → `/revoke` bilan yangilang.)

## 3. Serverni internetga (HTTPS) chiqarish
Ilova (GitHub Pages, HTTPS) serverga faqat **HTTPS** orqali murojaat qila oladi.

Eng oson yo'l — Cloudflare Tunnel (bepul):
```
python bot.py                                   # 1-oyna
cloudflared tunnel --url http://localhost:8080  # 2-oyna
```
U `https://....trycloudflare.com` manzil beradi. Brauzerda ochsangiz
"Street Dog server ishlayapti ✅" yozuvi chiqishi kerak.

> Diqqat: bu vaqtinchalik manzil har safar o'zgaradi. Doimiy ishlash uchun
> Cloudflare'da o'z domeningiz bilan "named tunnel" yoki VPS/hosting (Render, Railway, Fly.io...) ishlating.

## 4. Ilovaga manzilni yozish
`index.html` ichida:
```js
const API_URL = "https://github.com/jamshid0217/street-dog-app.git";
```
ni o'z manzilingizga almashtiring (oxirida `/` bo'lmasin) va `index.html` ni GitHub Pages'ga yuklang.

## 5. Menyuni o'zgartirsangiz
Narx yoki yangi taom qo'shsangiz, **ikkala joyni** yangilang: `index.html` dagi `products`
va `bot.py` dagi `PRODUCTS` (narxni server tekshiradi, shuning uchun bir xil bo'lishi shart).

## Admin buyruqlari
`/ochish`, `/yopish [izoh]`, `/stop` (tugagan taomlar), `/stats`, `/broadcast matn`

## Mijoz buyruqlari
`/start`, `/help`, `/aloqa`, `/manzil`
