# SEO Report — น้ำพริกแม่ปู (xn--s3cl7e3azb.com)
> จัดทำ: 2026-05-09 | เว็บไซต์: https://maepu-website.vercel.app (live)

---

## 1. สรุปงาน Phase 1–6

| Phase | Commit | สิ่งที่ทำ |
|---|---|---|
| Phase 1 | `cbd37f7` | SEO Audit — ตรวจสอบ 7 จุดวิกฤต (ไม่มี meta, Schema, alt text, sitemap ฯลฯ) |
| Phase 2 | `cbd37f7` | Technical SEO — Title, Description, Schema JSON-LD (FoodEstablishment+Products+Breadcrumb), OG/Twitter Card, robots.txt, sitemap.xml, vercel.json |
| Hotfix | `ccaafe2` | แก้ Punycode วิกฤต: xn--m3ci2a4e → xn--s3cl7e3azb (37 occurrences, 7 files) |
| Phase 3 | `158061f` | On-Page SEO — H1/H2/H3 keywords, alt text 17 รูป, lazy loading, internal CTA links, NAP ทุกหน้า, แก้ redirect loop ใน vercel.json |
| Phase 4 | `ab42eb0` | Image Optimization — แปลง 23 รูป → WebP (-94% รวม), `<picture>` fallback, originals backup |
| Phase 5 | `01ee8b6` | Local Trust — Google Maps iframe embed, "ดูเส้นทาง" link, NAP ใน franchise + free-review |
| Phase 6 | `2e2c040` | Performance — Font Awesome + AOS CSS deferred (print trick), preload hero WebP, WebP hero CSS |

---

## 2. Before / After

### Title Tags
| หน้า | ก่อน | หลัง |
|---|---|---|
| index.html | `น้ำพริกแม่ปู` (3 คำ) | `น้ำพริกแม่ปู \| น้ำพริกปลาสลิด-ปลาซิวแก้ว ระยอง สูตรต้นตำรับ` |
| franchise.html | ไม่มี | `แฟรนไชส์น้ำพริกแม่ปู \| ลงทุนธุรกิจอาหาร ระยอง คืนทุนไว` |
| free-review.html | ไม่มี | `รับน้ำพริกฟรี รีวิวแลกสินค้า \| MAEPU Creator Program ระยอง` |

### H1 Tags
| หน้า | ก่อน | หลัง |
|---|---|---|
| index.html | `น้ำพริกแม่ปู` | `น้ำพริกแม่ปู — น้ำพริกปลาสลิด & ปลาซิวแก้ว สูตรโฮมเมดจากระยอง` |
| franchise.html | `แฟรนไชส์ข้าวราดน้ำพริกแม่ปู` | `แฟรนไชส์น้ำพริกแม่ปู ระยอง — เปิดร้านง่าย คืนทุนไว` |

### Schema.org
| ก่อน | หลัง |
|---|---|
| ไม่มี | FoodEstablishment + Product×2 + BreadcrumbList |
| ไม่มี geo | GPS 12.6809386/101.2386401, TH-21 |
| ไม่มี hours | openingHoursSpecification 16:30–01:00 daily |
| aggregateRating (ผิดเจ้าของ) | ลบออก (ป้องกัน penalty) |

### ขนาดรูปภาพ
| ก่อน | หลัง | ลด |
|---|---|---|
| maepu-signature.png 5.1 MB | maepu-signature.webp 38 KB | **-99%** |
| milestone-now.jpg 6.4 MB | milestone-now.webp 185 KB | **-97%** |
| milestone-booth.png 4.6 MB | milestone-booth.webp 238 KB | **-94%** |
| product-ปลาสลิด.png 3.2 MB | product-ปลาสลิด.webp 146 KB | **-95%** |
| **รวม 23 รูป: ~36 MB** | **รวม ~2 MB** | **-94%** |

### Validation Live (maepu-website.vercel.app — 2026-05-09)
| ตรวจ | ผล |
|---|---|
| JSON-LD valid | ✅ 4 types (FoodEstablishment, Product×2, BreadcrumbList) |
| Punycode (xn--m3ci2a4e ต้องเป็น 0) | ✅ 0 occurrences |
| Punycode ใหม่ (xn--s3cl7e3azb) | ✅ 14 occurrences |
| canonical URL | ✅ https://xn--s3cl7e3azb.com/ |
| geo.region | ✅ TH-21 |
| og:url | ✅ https://xn--s3cl7e3azb.com/ |
| `<picture>` tags (WebP fallback) | ✅ 21 tags |
| loading="lazy" images | ✅ 20 images |
| WebP references | ✅ 23 files |

---

## 3. TODO — งานที่ต้องทำเอง

### 🔴 Critical (ทำก่อน)
- [ ] **Vercel Dashboard → Settings → Domains**: เพิ่ม `xn--s3cl7e3azb.com` เป็น primary domain
  - เหตุผล: ตอนนี้ Vercel redirect non-www → www (308) ทำให้ loop
  - วิธี: ไปที่ Vercel Dashboard → project → Settings → Domains → Add `xn--s3cl7e3azb.com` → ตั้งเป็น primary → เพิ่ม `www.xn--s3cl7e3azb.com` เป็น redirect
  - DNS: ต้องเพิ่ม A record `76.76.21.21` หรือ CNAME `cname.vercel-dns.com`

### 🟡 SEO ที่ต้องทำเอง (ไม่ใช่งาน code)
- [ ] **Google Search Console**: เพิ่มเว็บไซต์ → Submit sitemap.xml ที่ `https://xn--s3cl7e3azb.com/sitemap.xml`
- [ ] **Google Business Profile**: อัปเดต/สร้าง Profile
  - เพิ่มสินค้า: น้ำพริกปลาสลิด (180 บาท), น้ำพริกปลาซิวแก้ว (100 บาท)
  - เพิ่มรูปสินค้า ≥ 5 รูป
  - เพิ่ม URL เว็บไซต์: `https://xn--s3cl7e3azb.com`
- [ ] **Bing Webmaster Tools**: ส่ง sitemap ที่ https://www.bing.com/webmasters
- [ ] **Google Analytics 4**: ใส่ tracking code (แนะนำ Google Tag Manager)
- [ ] **Facebook Pixel**: ใส่ Pixel ID ที่ `<script>window.fbq = window.fbq || function(){};</script>` (ใน index.html บรรทัด 61)
- [ ] **รีวิว Google Maps**: ขอลูกค้า ≥ 10 รีวิว (สำคัญมากสำหรับ Map Pack)

### 🟢 Content (ระยะยาว)
- [ ] สร้างหน้า `/เกี่ยวกับเรา` — เล่าเรื่องแม่ปู เพิ่ม E-E-A-T signals
- [ ] สร้างหน้า `/วิธีสั่งซื้อ` — ขั้นตอนสั่งออนไลน์
- [ ] เพิ่มรูปสินค้าจริง (อาหาร, แพ็คเกจ) ≥ 3 รูปต่อสินค้า
- [ ] Blog หรือ FAQ section — "น้ำพริกปลาสลิดทานกับอะไรอร่อย?" ฯลฯ

---

## 4. แผนงาน 30 วัน (วันละ 20 นาที)

### สัปดาห์ที่ 1 — ปูพื้นฐาน
| วัน | งาน |
|---|---|
| 1 | แก้ Vercel custom domain (เพิ่ม `xn--s3cl7e3azb.com` เป็น primary) |
| 2 | สร้าง/อัปเดต Google Business Profile — ใส่ URL, ชั่วโมงทำการ, รูป |
| 3 | Google Search Console — verify domain, submit sitemap.xml |
| 4 | เพิ่มสินค้าใน Google Business Profile (ปลาสลิด 180, ปลาซิวแก้ว 100) |
| 5 | Bing Webmaster Tools — เพิ่มเว็บ, submit sitemap |
| 6-7 | Google Analytics 4 setup + ทดสอบ |

### สัปดาห์ที่ 2 — Content & Reviews
| วัน | งาน |
|---|---|
| 8-9 | ขอลูกค้า 5 คนรีวิว Google Maps (ส่ง link ตรง) |
| 10 | เพิ่มรูปสินค้าจริงใน Google Business Profile |
| 11-12 | เขียนหน้า "เกี่ยวกับเรา" — 300+ คำ |
| 13-14 | อัปเดต TikTok/Instagram ลิงก์เว็บในทุก bio |

### สัปดาห์ที่ 3 — Local Citations
| วัน | งาน |
|---|---|
| 15-16 | ลงข้อมูลใน Wongnai (ชื่อ, ที่อยู่, เบอร์ — ต้องตรงกับเว็บ) |
| 17-18 | ลงข้อมูลใน Foursquare/yelp (optional แต่ช่วย citation) |
| 19-20 | ตรวจว่า NAP ตรงกันทุกที่ (เว็บ, GMB, Wongnai) |
| 21 | ขอลูกค้าอีก 5 คนรีวิว Google Maps |

### สัปดาห์ที่ 4 — Monitor & Optimize
| วัน | งาน |
|---|---|
| 22-23 | ตรวจ Search Console — impressions, clicks, errors |
| 24-25 | ตรวจ Google Analytics — traffic source, bounce rate |
| 26-27 | ตอบรีวิว Google Maps ทุกรีวิว (สำคัญมากสำหรับ ranking) |
| 28-30 | ปรับ content ตาม keyword ที่เริ่มติดอันดับ |

---

## 5. วิธี Validate (เครื่องมือฟรี)

| เครื่องมือ | URL | ใช้ตรวจอะไร |
|---|---|---|
| Google Rich Results Test | https://search.google.com/test/rich-results | Schema JSON-LD |
| Schema Validator | https://validator.schema.org/ | Schema syntax |
| PageSpeed Insights | https://pagespeed.web.dev/ | LCP, CLS, FID, Core Web Vitals |
| Google Search Console | https://search.google.com/search-console | Index status, errors |
| MobileFriendly Test | https://search.google.com/test/mobile-friendly | Mobile SEO |

---

## 6. คาดการณ์ผลลัพธ์

| ช่วงเวลา | ผลที่คาด |
|---|---|
| 1–2 สัปดาห์ | Google crawl index ครบ 3 หน้า |
| 2–4 สัปดาห์ | ติดอันดับ long-tail: "น้ำพริกปลาสลิดระยอง", "น้ำพริกแม่ปู" |
| 1–2 เดือน | หน้าแรก keyword เฉพาะ (long-tail 3-4 คำ) |
| 2–3 เดือน | Top 10 "น้ำพริกแม่ปู" หน้าแรก Google |
| 3–6 เดือน | **Map Pack 3-pack** "น้ำพริกระยอง" (ต้องมีรีวิว ≥ 10) |

---

## 7. Validation Results (2026-05-09)

```
URL: https://maepu-website.vercel.app/
Status: 200 OK
HTML size: 100,469 bytes

JSON-LD:
  FoodEstablishment  punycode=OK ✅
  Product (ปลาสลิด)  punycode=OK ✅
  Product (ปลาซิวแก้ว) punycode=OK ✅
  BreadcrumbList     punycode=OK ✅

Meta Tags:
  title:      น้ำพริกแม่ปู | น้ำพริกปลาสลิด-ปลาซิวแก้ว ระยอง สูตรต้นตำรับ ✅
  canonical:  https://xn--s3cl7e3azb.com/ ✅
  geo.region: TH-21 ✅
  og:url:     https://xn--s3cl7e3azb.com/ ✅

Images:
  <picture> tags:    21 ✅
  loading=lazy:      20 ✅
  WebP references:   23 ✅

Punycode:
  xn--m3ci2a4e (wrong): 0 ✅ (must be 0)
  xn--s3cl7e3azb (correct): 14 ✅
```

---

*รายงานนี้จัดทำโดย Claude Code — สำหรับคำถามหรือการอัปเดต SEO ครั้งต่อไปโปรดดู checklist TODO ข้างบน*
