# বাংলাদেশি পাসপোর্ট ফটো মেকার

বাংলা ভাষার একটি browser-based photo tool। ছবি আপলোডের পর `@imgly/background-removal` দিয়ে ব্যাকগ্রাউন্ড আলাদা করে ডিফল্ট নীল রং বসায়। মুখের বৈশিষ্ট্য জেনারেট বা retouch করা হয় না; মূল ছবির পিক্সেল থেকেই foreground রাখা হয়।

## লোকাল কম্পিউটারে চালানো

Node.js 20 বা পরের সংস্করণ ইনস্টল করুন।

```bash
npm install
npm run dev
```

## Cloudflare Pages-এ ফ্রি Deploy

1. ZIP ফাইল Extract করুন।
2. পুরো `bd-passport-photo-maker` ফোল্ডারটি GitHub repository-তে Upload করুন।
3. Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git নির্বাচন করুন।
4. Build settings:
   - Framework preset: `Vite`
   - Build command: `npm run build`
   - Build output directory: `dist`
5. Deploy চাপুন।

## কী কী আছে

- JPG / PNG / WEBP আপলোড
- Browser-এ AI background removal
- Default blue background এবং custom color picker
- Crop zoom ও vertical position adjustment
- 35 × 45 mm অনুপাতের single JPG download
- A4 (300 DPI) print sheet, 1–30 copies
- A4 JPG download এবং browser Print / Save as PDF

## গুরুত্বপূর্ণ

- প্রথমবার background removal-এর সময় AI মডেল ইন্টারনেট থেকে নামতে পারে; তাই কিছু সময় লাগবে।
- ছবি আপনার ব্রাউজারেই প্রসেস হয়। তবে ব্যবহৃত লাইব্রেরির মডেল ফাইল CDN থেকে ডাউনলোড হয়।
- 35 × 45 mm একটি সাধারণ passport-photo print size হিসেবে সেট করা হয়েছে। কোনো নির্দিষ্ট সরকারি আবেদন/ডকুমেন্টের আলাদা ছবি-নিয়ম থাকলে সেটি যাচাই করে নিন।
- প্রিন্টের সময় Actual size / 100% নির্বাচন করুন; Fit to page বন্ধ রাখুন।
- AI background removal চুল বা পোশাকের কিনারা সব ছবিতে নিখুঁতভাবে কাটতে নাও পারে। ব্যবহারের আগে preview যাচাই করুন।
