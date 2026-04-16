# SENTINEL OSINT (formerly Overpass Radar)

### [ENG]

**Sentinel OSINT** is a personal portfolio project born out of my deep interest in the defense industry and geopolitical intelligence systems. Building upon my earlier "Base Scan" architecture, this dashboard explores how publicly accessable Open-Source Intelligence (OSINT) APIs can be aggregated into a single analytical map.

I developed this system purely driven by curiosity, integrating easily accessible open data sources (such as global flight transponders, public satellite streams, and geographic databases) while utilizing AI resources to better parse, understand, and map the gathered information.

---

## Features

### Radar Controls
*   **Military Bases:** Automatically queries and plots secretive or public military installations, airbases, and barracks using complex bounding-box detection algorithms.
*   **Aircraft Tracking:** Hooks into the OpenSky API to stream live global aircraft. Includes a "Military Only" filter to isolate tactical flights globally.
*   **Ports & Shipyards:** Maps strategic naval infrastructure, dry docks, and major ports for maritime intelligence.
*   **Tactical Ruler:** A built-in targeting system. Click two points on the map to calculate the exact distance (KM) and estimate the time of arrival (ETA) based on dynamic Mach speeds (Mach 1 to Mach 5).

### OSINT Intelligence
*   **NASA Thermal Anomalies (FIRMS):** Overlays live thermal heat signatures straight from NASA satellite data to detect active fires, explosions, or industrial thermal spikes.
*   **Live Weather Layers:** Integrates RainViewer WMS to project real-time precipitation and heavy storm clouds over operational areas.
*   **Spy Satellites:** Connects to Celestrak TLE streams to map the real-time orbital positions of actively tracked satellites above the selected country.
*   **Seismic Radar:** Integrates USGS API to plot recent significant seismic events and earthquake clusters.
*   **Local Intel (Wiki Geo-Leak):** Cross-references geographical coordinates with Wikipedia database leaks to extract highly specific local operational data (barracks history, local entities).
*   **Energy / Power Grid:** Maps Highly Valuable Targets (HVT) such as power plants, nuclear reactors, and major electrical substations.
*   **National Networks & Global Submarine Cables:** Discovers physical communication backbones. Maps inland fiber optics (Telecom Exchanges) and global underwater submarine landing stations.

---

## Tech Stack & Architecture

*   **Frontend:** React.js, Vite, Leaflet, React-Leaflet, Lucide-React.
*   **Backend:** Node.js, Express, Axios.

### Public APIs Utilized:
*   **Overpass API (OSM):** Extracts coordinates and dimensions for global military bases, infrastructure (HVTs), and communication networks.
*   **OpenSky Network API:** Tracks worldwide transponder streams for finding active flight paths and military aircraft classification.
*   **USGS GeoJSON API:** Provides real-time and historical global earthquake and seismic anomaly data.
*   **Celestrak TLE Data:** Fetches Two-Line Element sets for real-time tracking of active satellite constellations.
*   **NASA FIRMS & RainViewer WMS:** Map layering protocols for thermal hot-spots and real-time precipitation mapping.
*   **MediaWiki API (Wikipedia):** Cross-references geographical zones to pull classified/leaked unit histories and base information.

*   **Architecture & Stability:** The backend uses dynamic query rotating and auto-retry algorithms for standard OpenStreetMap queries to circumvent Rate Limits (HTTP 429) and Bad Gateway (HTTP 502/504) crashes, keeping the app production-ready. However, please note that performance lag or browser freezing may occur when querying extremely large country datasets, which is a known architectural limitation at this time.

---

## Installation & Running

1. **Clone the repository:**
   ```bash
   git clone https://github.com/hasanerman/sentinel-osint.git
   cd sentinel-osint
   ```
2. **Start the Express Backend:**
   ```bash
   cd backend
   npm install
   node server.js
   ```
3. **Start the Vite Frontend:**
   ```bash
   cd frontend
   npm install
   npm run dev
   ```

*(Disclaimer: This project uses publicly available Open-Source Intelligence data strictly for educational mapping purposes. Do not use this tool for actual military operations.)*

---
---

### [TR]

# SENTINEL OSINT

**Sentinel OSINT**, savunma sanayii ve istihbarat sistemlerine olan kisisel ilgim dogrultusunda gelistirdigim bir cografi analiz ve vizyon projesidir. Daha onceden yaptigim basit bir askeri us (base scan) tarama sistemi uzerine dusunerek, bu projeyi tamamen acik kaynakli (OSINT) kamuya acik API'ler kullanarak bir adim oteye tasidim.

Sistemi tamamen kendi merakim ve ogrenme surecim cercevesinde gelistirdim; internette erisilmesi kolay olan acik veritabanlarini, acik sismik uyarilari ve ucus sinyallerini tek bir haritaya entegre ettim. Bu egitim projesini kodlarken ve kargasali verileri analiz ederken AI referanslarindan ve yonlendirmelerinden de bolca faydalandim.

## Ozellikler

### Radar Kontrolleri 
*   **Askeri Usler:** Gelismis sinir tanima algoritmalari ile hedeflenen ulkedeki kamuya acik ya da gizli askeri tesisleri, hava uslerini ve kislalari haritaya dokerek analiz imkani sunar.
*   **Canli Ucus Takibi:** OpenSky API ile dunya capindaki ucaklari canli izler. Ozel "Military Only" filtresiyle sivil ucaklari haritadan silip yalnizca askeri ucaklari filtreleyebilirsiniz.
*   **Limanlar ve Tersaneler:** Deniz istihbarati icin stratejik donanma altyapilarini, tersaneleri ve ana limanlari tespit eder.
*   **Taktiksel Cetvel:** Dahili hedef kitleme sistemi. Haritada belirlenen iki nokta arasindaki mesafeyi (KM) ve secilen MACH (Ses hizi 1-5) degerine gore tahmini varis suresini (ETA) anlik olarak hesaplar. Şeffaf arayuz tasarimi harita okumasini engellemez.

### OSINT Istihbarati
*   **NASA Termal Anomalileri:** NASA uydularindan alinan canli verilerle yeryuzundeki aktif yangin, patlama veya siddetli endustriyel termal radyoaktivite artislarini gosterir.
*   **Canli Hava Durumu:** Operasyon bolgesindeki canli yagis/firtina bulutlarini haritaya yansitir.
*   **Casus Uydular:** Celestrak uzerinden aldigi yorunge (TLE) verilerini isleyerek secili ulkenin uzerinden gecen aktif uydu takimyildizlarini gosterir.
*   **Sismik Radar:** USGS API uzerinden yakin zamanli siddetli depremleri ve sismik patlamalari gosterir.
*   **Yerel Sizinti Istihbarati:** Yalnizca harita koordinatlarini kullanarak Wikipedia veritabanini tarar ve tiklanilan bolge/us hakkindaki sizdirilmis tarihceleri (Orn: us gecmisi) ceker.
*   **Stratejik Enerji Agi:** Nukleer santraller, enerji tesisleri ve devasa elektrik trafolari gibi "Yuksek Degerli Hedefleri (HVT)" haritalar.
*   **Ulusal ve Kuresel Fiber Aglari:** Guck ve kuresel iletisim omurgasini analiz eder. Ulkelerin icinden gecen kara fiber optik aglarini ve Kitalararasi Denizalti Veri Kablolarini stratejik olarak cizer.

## Teknik Mimari

### Kullanilan API Altyapilari:
*   **Overpass API (OSM):** Ulkemizin ve dunya capindaki uslerin, kislalarin ve devasa fiber aglarin acik kaynak konumlarini haritalamak icin.
*   **OpenSky Network API:** Dunyadaki butun transponder sinyallerini toplayip "Sadece Askeri Ucaklar" siniflandirmasi yapmak icin.
*   **USGS GeoJSON API:** Gercek zamanli kuresel deprem merkezlerini ve sismik patlamalari cizdirmek icin.
*   **Celestrak TLE Data:** Aktif uydu yorungelerini ve spy-satellite aglarini canli cizmek icin.
*   **NASA FIRMS & RainViewer WMS:** Uydudan tespit edilen isisal (termal) dev uyarilari ve agir firtina ruzgarlarini katmanlamak icin.
*   **MediaWiki API (Wikipedia):** Cografi kordinatlara gizlenmis askeri tarihce sizintilarini ve us gecmisini cekmek icin.

Frontend `React.js` ve `Vite` kullanilarak devasa verileri kasmadan cizecek sekilde (Leaflet) olusturulmustur. Backend `Node.js` otomasyonlari ile API hiz kisitlamalarini (Rate Limits / 429) ve zaman asimlarini (Timeout / 504) asmak uzere "Dinamik Yeniden Deneme (Auto-Retry)" algoritmalariyla donatilmis, uretime (Production) hazir olarak kodlanmistir. Ama cok buyuk verilerde kasmalar oluyor, sunucu kapasitelerinden oturu onlari genis capta duzeltebilecegimi suanda dusunmuyorum.

---
*Proje, kamuya acik Acik Kaynak Istihbarat (OSINT) verilerini egitim macli kullanmaktadir.*
