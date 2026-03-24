# HemenHesap.com | Teknik Mimari ve Showcase 🚀

**HemenHesap.com**, Next.js 16 (App Router), React 19, TypeScript ve Supabase ekosistemi üzerine kurulu; hız, SEO ve ölçeklenebilirliği merkeze alan **Modüler Monolith (FSD)** mimarili modern bir web platformudur.

> **Not:** Bu depo, projenin sadece mimari yapısını ve dökümantasyonunu sergilemek için oluşturulmuştur. Ana kod tabanı gizlidir.

---

## 🛠️ Mimari Öne Çıkanlar

### 1. Modüler Monolith & FSD (Architecture)
Platform, **Feature-Sliced Design (FSD)** prensiplerini takip eden modüler bir yapıya sahiptir. Tüm iş mantığı `features/` klasörü altında dikey dilimlenmiş (vertical slicing) modüllerden oluşur. Bu yapı; dairesel bağımlılıkları sıfırlarken, yüzlerce hesaplama aracının birbirine zarar vermeden geliştirilmesine olanak tanır.
*   **Layered Architecture:** Features, Core, Shared ve App katmanları arasında kesin bir hiyerarşi mevcuttur.
*   **Discovery Pattern:** Yeni bir hesaplama aracı eklemek, sadece konfigürasyon bazlıdır ve build motoru tarafından otomatik tanıtan (`generate-calculators.ts`) bir sistemle çalışır.

### 2. Hibrit Vektörel Arama (AI-Powered Search)
Kullanıcılara sadece "keyword" değil, "niyet" bazlı arama sunmak için **OpenAI Embeddings** ve **Supabase pgvector** entegrasyonu sağladım. 
*   **Akıllı Eşleşme:** "Nakit ihtiyacı" yazan birine kredi hesaplayıcılarını anında getirir.
*   **3 Katmanlı Fallback:** Vector Search → Text Search → Static JSON Map.

### 3. Programmatik SEO (pSEO)
Taksi ücretleri ve finansal araçlar için binlerce dinamik sayfayı **Next.js ISR (Incremental Static Regeneration)** ile milisaniyeler içinde sunan dinamik bir yapı kurguladım. Her araç için JSON-LD (Structured Data) ve FAQ şemaları build aşamasında otomatik üretilir.

### 4. Enterprise-Grade Güvenlik & Performans
*   **Edge Runtime Security:** Bot saldırıları ve abuse girişimleri, henüz sunucuya yük binmeden **Vercel Edge Network** seviyesinde engellenir.
*   **Rate Limiting:** Upstash Redis üzerinde kurgulanmış "Sliding Window" algoritmalı istek sınırlama.
*   **Memory Management:** React taraflı (useEffect cleanup) ve server-side (Map clearing) bellek yönetimi optimizasyonları.

---

## 📉 Performans Metrikleri (Core Web Vitals)
*   **Lighthouse Performance:** 98-100/100
*   **TTFB (Time to First Byte):** < 100ms
*   **CLS (Cumulative Layout Shift):** 0

---

## 🏗️ Kullanılan Teknoloji Yığını
- **Frontend:** React 19, Next.js 16, Tailwind CSS, Recharts, React-Leaflet
- **Backend/DB:** Supabase (PostgreSQL), Upstash Redis, Next-Auth
- **Data & AI:** Python (Scrapers), OpenAI API (Embeddings), Llama-3 (Local Content Gen)
- **DevOps:** GitHub Actions, Aws, Docker

---

## 🔗 Canlı Uygulama
Projeyi incelemek için: [https://hemenhesap.com](https://hemenhesap.com)
