# SEO Audit — น้ำพริกแม่ปู (xn--m3ci2a4e.com)
**วันที่ตรวจ:** 2026-05-08  
**ผู้ตรวจ:** Claude Code (Phase 1 Audit)

---

## 1. โครงสร้างไฟล์ปัจจุบัน

```
maepu-website/
├── index.html          ← หน้าหลัก
├── franchise.html      ← หน้าแฟรนไชส์
├── free-review.html    ← หน้าโครงการ Influencer / รับน้ำพริกฟรี
├── franchise.html.txt  ← ⚠️ ไฟล์ขยะ ควรลบ
├── images/             ← รูปภาพทั้งหมด
└── videos/             ← ไฟล์วิดีโอ concept-video.mp4
```

**ไฟล์ที่ขาดหายทั้งหมด (ต้องสร้างใหม่):**
| ไฟล์ | สถานะ | ผลกระทบ |
|------|--------|---------|
| `robots.txt` | ❌ ไม่มี | Googlebot ไม่รู้ขอบเขตการ crawl |
| `sitemap.xml` | ❌ ไม่มี | Google ไม่รู้ว่ามีหน้าอะไรบ้าง |
| `vercel.json` | ❌ ไม่มี | ไม่มี security headers / cache |
| `manifest.json` | ❌ ไม่มี | ไม่รองรับ PWA / Add to Home Screen |

---

## 2. วิเคราะห์ทุกหน้า HTML

### 2.1 index.html (หน้าหลัก)

#### Meta Tags ปัจจุบัน
| Tag | ค่า | ปัญหา |
|-----|-----|--------|
| `<html lang>` | `th` ✅ | ถูกต้อง |
| `<meta charset>` | `UTF-8` ✅ | ถูกต้อง |
| `<meta viewport>` | มี ✅ | ถูกต้อง |
| `<title>` | "น้ำพริกแม่ปู - Original Homemade" ❌ | ไม่มีคำว่า "ระยอง" และ keyword หลัก ยาว 36 ตัวอักษร (ดี แต่ควรปรับ) |
| `<meta description>` | ❌ ไม่มี | **วิกฤต** — Google จะสร้าง description เองซึ่งไม่ optimal |
| `<meta keywords>` | ❌ ไม่มี | — |
| `<link canonical>` | ❌ ไม่มี | เสี่ยง duplicate content |
| `<meta robots>` | ❌ ไม่มี | — |
| `<meta geo.region>` | ❌ ไม่มี | ขาด Local SEO signal |
| `Open Graph` | ❌ ไม่มีเลย | แชร์ใน Facebook/LINE ไม่มีรูป Preview |
| `Twitter Card` | ❌ ไม่มีเลย | — |
| `Schema.org JSON-LD` | ❌ ไม่มีเลย | **วิกฤต** — Google ไม่รู้ว่านี่คือร้านค้าในระยอง |

#### Heading Structure
```
H1: "น้ำพริกแม่ปู"  ✅ (มีเพียง 1 H1 — ถูกต้อง)
H2: "สินค้าแนะนำ"
H2: "เสียงจากลูกค้าตัวจริง"
H2: "รีวิวจาก Influencer"
H2: "น้ำพริกปลาสลิด"   ← ดี! มี keyword
H2: "Connecting the DOTs"  ← ❌ ไม่มี keyword ไทย/ระยอง
H2: "เส้นทางและความฝัน"
H2: "หากสนใจสามารถติดต่อได้"
H3: "น้ำพริกปลาสลิด"
H3: "น้ำพริกปลาซิวแก้ว"
H3: "ยำถั่วลิสงปลาสลิด"
```
**ปัญหา:** H2/H3 ส่วนใหญ่ไม่มีคำว่า "ระยอง" หรือ "น้ำพริก" ทำให้ขาด keyword density

#### รูปภาพ & Alt Text
| รูป | Alt Text ปัจจุบัน | ปัญหา |
|-----|-------------------|--------|
| product-ปลาสลิด.png | "น้ำพริกปลาสลิด" | ❌ ไม่มี "ระยอง" |
| product-ปลาซิวแก้ว.jpg | "น้ำพริกปลาซิวแก้ว" | ❌ ไม่มี "ระยอง" |
| product-ยำถั่วลิสงปลาสลิด.png | "ยำถั่วลิสงปลาสลิด" | ❌ ไม่มี "ระยอง" |
| review-1.jpg | "Capture รีวิวลูกค้า" | ❌ ไม่ descriptive |
| review-2.jpg | "Capture รีวิวลูกค้า" | ❌ ไม่ descriptive |
| review-3.jpg | "Capture รีวิวลูกค้า" | ❌ ไม่ descriptive |
| signature-น้ำพริกปลาสลิด.jpg | "น้ำพริกปลาสลิด" | ❌ ไม่มี "ระยอง" |
| pi-card.jpg | "About Maepu" | ❌ ไม่ descriptive |
| customer-collage-1,2,3.jpg | "Customer Review 1,2,3" | ❌ ขาด keyword |
| milestone-*.jpg/png | "Order แรก", "Tour Leader Market" ฯลฯ | พอใช้ได้ |
| logo-chob-pochana-1.jpg | "สาขาจันทบุรี" | ✅ ดี |
| logo-chob-pochana-2.jpg | "สาขาระยอง" | ✅ ดี |

**ทุกรูป:** ❌ ไม่มี `loading="lazy"` บนรูปที่อยู่ใต้ fold  
**ทุกรูป:** ❌ ไม่มี `width`/`height` attribute (เสี่ยง CLS)

#### ปัญหาอื่นใน index.html
- ❌ **Facebook Pixel ID** ยังเป็น placeholder: `ใส่_FACEBOOK_PIXEL_ID_ที่นี่` — ต้องใส่ ID จริง
- ❌ **ไม่มี NAP** (Name, Address, Phone) ในรูปแบบ structured text ใน footer — มีแค่เบอร์โทร
- ❌ **ไม่มีที่อยู่ร้าน** ระยองอย่างชัดเจน
- ❌ **ไม่มีเวลาเปิด-ปิด**
- ⚠️ Copyright ระบุ "2024" แต่ปีปัจจุบัน 2026

---

### 2.2 franchise.html (หน้าแฟรนไชส์)

| Tag | ค่า | ปัญหา |
|-----|-----|--------|
| `<html lang>` | `th` ✅ | ถูกต้อง |
| `<title>` | "แฟรนไชส์ข้าวราดน้ำพริกแม่ปู - สร้างอาชีพ สร้างฝัน" | ⚠️ ยาว 48 ตัวอักษร พอใช้ แต่ไม่มี "ระยอง" |
| `<meta description>` | ❌ ไม่มี | วิกฤต |
| `<link canonical>` | ❌ ไม่มี | — |
| `Open Graph` | ❌ ไม่มีเลย | — |
| `Schema.org` | ❌ ไม่มีเลย | — |

**Heading:**
```
H1: "แฟรนไชส์ข้าวราดน้ำพริกแม่ปู"  ✅
H2: "ทำไมต้อง 'ข้าวราดน้ำพริก'?"
H2: "โครงสร้างราคาและกำไร"
H2: "ลองคำนวณจุดคุ้มทุน (ROI)"
H2: "แพ็คเกจลงทุน: แม่ปู Partner"
H2: "เราไม่ได้ขายแค่แฟรนไชส์ แต่เราหา 'ครอบครัว'"
```

---

### 2.3 free-review.html (หน้า Influencer)

| Tag | ค่า | ปัญหา |
|-----|-----|--------|
| `<html lang>` | `th` ✅ | ถูกต้อง |
| `<title>` | "โครงการ Influencer หน้าใหม่ - น้ำพริกแม่ปู" | ❌ "หน้าใหม่" ไม่ควรอยู่ใน title, ไม่มี "ระยอง" |
| `<meta description>` | ❌ ไม่มี | วิกฤต |
| `<link canonical>` | ❌ ไม่มี | — |
| `Open Graph` | ❌ ไม่มีเลย | — |
| `Schema.org` | ❌ ไม่มีเลย | — |

**Heading:**
```
H1: "อย่าแค่กินให้อร่อย... เปลี่ยนความอร่อยให้เป็นโอกาส"  ← ❌ ไม่มี keyword
H2: "ง่ายๆ แค่ 3 ขั้นตอน"
H2: "Inspiration Hall"
H3: "สั่งซื้อ & ชิมจริง"  etc.
```

---

## 3. ปัญหา Image SEO (รูปใหญ่เกินไป ต้องบีบอัดก่อน deploy)

| ไฟล์ | ขนาดปัจจุบัน | เป้าหมาย | ลำดับความเร่งด่วน |
|------|-------------|---------|------------------|
| `grand-banner.mp4` | 21 MB | < 5 MB | 🔴 วิกฤต |
| `milestone-now.jpg` | 6.4 MB | < 300 KB | 🔴 วิกฤต |
| `maepu-signature.png` | 5.1 MB | < 300 KB | 🔴 วิกฤต (ใช้เป็น Hero BG!) |
| `product-ยำถั่วลิสงปลาสลิด.png` | 4.6 MB | < 200 KB | 🔴 วิกฤต |
| `milestone-booth.png` | 4.6 MB | < 300 KB | 🔴 วิกฤต |
| `product-ปลาสลิด.png` | 3.2 MB | < 200 KB | 🔴 วิกฤต |
| `milestone-shop.jpg` | 2.5 MB | < 300 KB | 🟠 สูง |
| `milestone-future.png` | 2.3 MB | < 300 KB | 🟠 สูง |
| `rice-siu-kaew.png` | 1.6 MB | < 200 KB | 🟠 สูง |
| `rice-salid.png` | 1.5 MB | < 200 KB | 🟠 สูง |
| `logo-chic.png` | 1.4 MB | < 100 KB | 🟠 สูง |
| `customer-collage-3.jpg` | 1.0 MB | < 300 KB | 🟡 กลาง |
| `customer-collage-2.jpg` | 1.0 MB | < 300 KB | 🟡 กลาง |
| `customer-collage-1.jpg` | 898 KB | < 300 KB | 🟡 กลาง |
| `logo-chob-pochana-1.jpg` | 789 KB | < 200 KB | 🟡 กลาง |
| `milestone-start.jpg` | 231 KB | < 200 KB | 🟢 ต่ำ |

**เครื่องมือแนะนำสำหรับบีบอัด:**
- [Squoosh.app](https://squoosh.app) — บีบอัด PNG/JPG และแปลงเป็น WebP ฟรี
- [HandBrake](https://handbrake.fr) — สำหรับบีบอัดไฟล์ MP4

---

## 4. ปัญหา Performance ที่กระทบ SEO (Core Web Vitals)

| ปัญหา | ผลกระทบ |
|--------|---------|
| รูปขนาดใหญ่มาก (Hero BG = 5.1MB) | LCP สูงมาก (> 4 วินาที) — Google จะลดอันดับ |
| ไม่มี `loading="lazy"` บนรูปล่าง | โหลดทุกรูปพร้อมกัน — ช้า |
| ไม่มี `width`/`height` บนรูป | Layout shift (CLS) — ผู้ใช้เห็นหน้าเด้ง |
| AOS.js โหลดแบบ sync | Render-blocking — ชะลอการแสดงผล |
| ไม่มี `preconnect` ไปยัง Google Fonts, cdnjs | DNS lookup ช้า |
| ไม่มี cache headers | ทุก request โหลดซ้ำใหม่ |

---

## 5. สรุปปัญหา SEO ทั้งหมด (เรียงลำดับความสำคัญ)

### 🔴 วิกฤต (ต้องแก้ก่อน)
1. ไม่มี `<meta name="description">` ทุกหน้า
2. ไม่มี Schema.org LocalBusiness JSON-LD
3. ไม่มี robots.txt
4. ไม่มี sitemap.xml  
5. ขนาดรูปใหญ่มาก (Hero BG 5.1MB ทำให้ LCP พัง)
6. Facebook Pixel ID เป็น placeholder (ทำให้เกิด JS error ในทุก session)

### 🟠 สำคัญ
7. Title tag ทุกหน้าไม่มีคำว่า "ระยอง"
8. ไม่มี `<link rel="canonical">`
9. ไม่มี Open Graph tags (แชร์บน LINE/Facebook ไม่มีรูป preview)
10. ไม่มี geo meta tags (TH-21)
11. ไม่มี NAP (ที่อยู่ร้าน) ใน footer
12. Alt text รูปภาพไม่มี keyword "ระยอง"

### 🟡 ปรับปรุง
13. ไม่มี `loading="lazy"` บนรูปใต้ fold
14. ไม่มี `width`/`height` attribute
15. AOS.js โหลดแบบ sync (ควรใช้ defer)
16. ไม่มี preconnect สำหรับ Google Fonts, Font Awesome, cdnjs
17. ไม่มี vercel.json (security headers, cache)
18. Title ของ free-review.html มีคำว่า "หน้าใหม่"
19. Copyright ระบุ "2024" แต่ปีปัจจุบัน 2026
20. ชื่อไฟล์รูปเป็นภาษาไทย (SEO-unfriendly บน URL)

---

## 6. สิ่งที่ทำได้ดีแล้ว ✅

- `<html lang="th">` ครบทุกหน้า
- `<meta charset="UTF-8">` ครบ
- `<meta viewport>` ครบ
- H1 มีเพียงอันเดียวต่อหน้า
- มี TikTok Pixel ติดตั้งแล้ว (index.html)
- มี Social links (Instagram, LINE OA, TikTok)
- เบอร์โทรมี `href="tel:..."` — crawlable
- Internal links ระหว่างหน้า (navbar)
- Responsive design

---

## 7. ขั้นตอนถัดไป (Phase 2-6)

เมื่อผมยืนยัน Audit แล้ว จะดำเนินการตามลำดับ:

| Phase | งาน | ไฟล์ที่แก้ |
|-------|-----|-----------|
| **2** | Technical SEO (robots, sitemap, meta tags, Schema, vercel.json) | ทุกไฟล์ HTML + สร้างใหม่ |
| **3** | On-Page SEO (Title, Description, Keywords ทุกหน้า) | index.html, franchise.html, free-review.html |
| **4** | Image SEO (alt text, lazy loading, width/height) | index.html, franchise.html |
| **5** | Content & Local Trust (NAP ใน footer, ปรับเนื้อหา) | index.html |
| **6** | Performance (preconnect, AOS defer, cache headers) | ทุกไฟล์ HTML + vercel.json |
| **7** | สร้าง SEO_REPORT.md สรุปสุดท้าย + checklist | — |

---

*หากมีข้อมูลเพิ่มเติม เช่น ที่อยู่ร้านที่แน่นอน, พิกัด GPS, เวลาเปิดปิด, Facebook Page ID — กรุณาแจ้งก่อนทำ Phase 2 เพื่อใส่ใน Schema.org ให้ถูกต้อง*
