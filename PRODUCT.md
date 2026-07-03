# Product

## Register

brand

## Users

**ผู้ซื้อไวน์ทั่วไป** — ลูกค้าที่รู้จัก Alees ผ่าน Line@ และต้องการดู catalog สินค้าอย่างละเอียดก่อนสั่งซื้อ ใช้งานทั้งบน desktop และ mobile เท่าๆ กัน ขั้นตอนหลักคือ ดูสินค้า → สนใจ → ส่ง order request หรือติดต่อกลับผ่าน Line เว็บไซต์เป็น catalog companion ไม่ใช่ทดแทน Line@

**Admin / เจ้าของแบรนด์** — จัดการสินค้า เนื้อหา และรับ email notification เมื่อมีคำสั่งซื้อใหม่ ต้องการ CMS เบื้องต้นที่ใช้งานง่าย ไม่ซับซ้อน

## Product Purpose

เว็บไซต์ e-catalog ไวน์แบรนด์ Alees — ช่วยให้ลูกค้าที่มาจาก Line@ ดูรายละเอียดสินค้า ราคา และข้อมูลแบรนด์ได้อย่างครบถ้วน พร้อม order request flow สำหรับผู้ที่พร้อมสั่ง ระบบไม่มี payment gateway — admin รับ notification ทาง email แล้วดำเนินการผ่าน Line ต่อ ความสำเร็จวัดจากภาพลักษณ์แบรนด์ที่น่าเชื่อถือ และ order requests ที่เพิ่มขึ้น

## Brand Personality

**Earthy · Confident · Inviting**

แบรนด์ Alees มีสีประจำตัวเป็นแดงเลือดหมู (oxblood) — ลึก หนักแน่น มีน้ำหนัก ไม่ฉาบฉวย ความหรูหราของ Alees ไม่ใช่ความเย็นชา แต่เป็นความอบอุ่นที่ชวนเข้าหา เหมือนห้องเก็บไวน์ที่ไฟแสงเทียนกำลังส่องขวดไวน์ที่ดี อารมณ์ที่ต้องการ: ความมั่นใจในคุณภาพ + ความอยากได้ + ความรู้สึกว่า "ซื้อได้เลย"

## Color Strategy

**Committed** — oxblood แดงเลือดหมูครอง 30–50% ของ surface (hero, section backgrounds, primary buttons) บน bg เข้มใกล้ดำ ทอง/amber เป็น accent สำหรับราคา, highlights, secondary CTAs

Palette seed (OKLCH) — primary sampled from official Alees catalog PDF (#6C3533):
- `--color-bg`:      oklch(1.000 0.000 0)     /* homepage ground start — a soft, capped-low oxblood wash builds in on scroll, staying light-mode throughout; see DESIGN.md "The Pour Ground" */
- `--color-surface`: oklch(0.972 0.005 23)    /* warm surface for cards/panels */
- `--color-primary`: oklch(0.400 0.079 23.4)  /* actual brand color #6C3533 */
- `--color-accent`:  oklch(0.680 0.115 78)    /* warm gold — price, reward moments only */
- `--color-ink`:     oklch(0.140 0.008 23)    /* near-black body text on white */
- `--color-muted`:   oklch(0.420 0.008 23)    /* secondary text — ≥4.5:1 on white */
- `--color-ink-on-primary`: oklch(0.940 0.008 60) /* warm near-white for text on brand fills */

## Anti-references

- Generic Shopify / WooCommerce template ที่ดูเหมือน marketplace ทั่วไป — Alees ต้องมี identity ของตัวเอง
- Wine sites ที่ใช้พื้นหลังสีครีม/เบจ + สีเขียวใบไม้ (vineyard cliché)
- ดีไซน์ที่ cold luxury — ขาว เงิน เย็นชา ไม่รู้สึก inviting
- Grid สินค้าที่ดูแบน ไม่ให้ความรู้สึก premium — ราวกับ spreadsheet ใส่รูป

## Design Principles

1. **The catalog is the brand** — หน้า wine listing ต้องรู้สึก premium เท่ากับหน้า brand story ทุก product card ต้องสื่อถึงคุณภาพ ไม่ใช่แค่แสดงข้อมูล
2. **Warmth that converts** — ความอบอุ่นทุกจุดต้องนำไปสู่ purchase path ปุ่ม CTA ต้องชัด ขั้นตอนสั้น friction น้อย ทั้งบน desktop และ mobile
3. **Show, don't describe** — ใช้รูปและ typography ทำงานแทน bullet point คุณภาพของไวน์ต้องรู้สึกได้จากการดู ไม่ใช่แค่อ่าน
4. **Catalog companion, not a replacement** — ลูกค้ามาจาก Line@ เว็บต้องตอบคำถาม "มีอะไรบ้าง เท่าไหร่" ได้ทันที ก่อนที่เขาจะกลับไปคุยต่อบน Line
5. **Legibility is luxury** — ฟอนต์ขนาดเหมาะสม contrast ผ่าน WCAG AA ทุกจุด ทั้ง desktop และ mobile ดีไซน์หรูไม่ได้แปลว่าอ่านยาก

## Accessibility & Inclusion

- WCAG 2.1 AA เป็นขั้นต่ำ (contrast ≥ 4.5:1 สำหรับ body text, ≥ 3:1 สำหรับ large text)
- รองรับ reduced motion — ทุก animation มี `@media (prefers-reduced-motion: reduce)` fallback
- รองรับภาษาไทยและอังกฤษ — font ที่เลือกต้องรองรับ Thai script ได้ดี
- ไม่พึ่ง color เพียงอย่างเดียวในการสื่อ state (error, success ต้องมี icon / text ด้วย)