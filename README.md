# 🎮 Unreal Engine Sürüm Seçim Rehberi / Version Selection Guide

<p align="center">
  <a href="https://github.com/BeyazAdam">
    <img src="https://img.shields.io/badge/Developer-BeyazAdam-blue?style=for-the-badge&logo=github" alt="Developer BeyazAdam">
  </a>
  <a href="https://github.com/BeyazAdam/unreal-engine-version-guide">
    <img src="https://img.shields.io/badge/Repository-unreal--engine--version--guide-orange?style=for-the-badge&logo=github" alt="Repository">
  </a>
  <a href="https://beyazadam.github.io/unreal-engine-version-guide/">
    <img src="https://img.shields.io/badge/Interactive%20Tool-Live%20Demo-brightgreen?style=for-the-badge&logo=vercel" alt="Live Demo">
  </a>
  <img src="https://img.shields.io/badge/Unreal%20Engine-5.4%20%7C%205.8-informational?style=for-the-badge&logo=unrealengine&logoColor=white" alt="Unreal Engine Versions">
</p>

---

## 🇹🇷 Türkçe Rehber

Merhaba! Ben **[BeyazAdam](https://github.com/BeyazAdam)**. 

Unreal Engine ekosisteminde proje başlatırken en çok zaman kaybedilen ve ileride teknik borç (technical debt) olarak karşımıza çıkan en kritik aşamalardan biri **doğru motor sürümünü seçmektir**. Bu rehber, projenizin türüne, hedef platformuna, ekip boyutuna ve grafik tarzına göre en doğru Unreal Engine sürümünü saniyeler içinde belirlemeniz için bir deniz feneri olması amacıyla hazırlandı.

> [!TIP]
> 🚀 Saniyeler içinde projenize en uygun sürümü bulmak için **[Interaktif Sürüm Seçim Aracı](https://beyazadam.github.io/unreal-engine-version-guide/)** sayfamızı kullanabilirsiniz!

### 📌 Hızlı Karar Matrisi (Sürümlerin Güçlü Yanları)

| Sürüm | Slogan (Öne Çıkan Karakteri) | En Uygun Olduğu Projeler | Neden Seçmelisiniz? | Kimler Kaçınmalı? |
| :--- | :--- | :--- | :--- | :--- |
| **UE 4.27** | 🛡️ *Eski Dost, Kaya Gibi Stabil* | Düşük donanımlı mobil, HTML5, 2D oyunlar, retro/piksel projeler ve legacy VR. | Sektörün en yüksek kararlılığa (stability) sahip sürümüdür. Paket boyutu en küçüktür. | Nanite, Lumen veya modern fizik motoru Chaos'un yeni özelliklerine ihtiyaç duyanlar. |
| **UE 5.1** | 🚀 *Yeni Neslin İlk Ayak Sesleri* | İlk nesil UE5 projeleri, görece hafif Nanite/Lumen PC projeleri, stabil World Partition kullanımı. | UE5'in prodüksiyona hazır ilk kararlı sürümüdür. Geliştirme araçları stabil ve oturmuştur. | Yoğun bitki örtüsü (Procedural Foliage) ve karmaşık dinamik deformasyon yapacaklar. |
| **UE 5.3** | 🎬 *Sinematik Deha ve Detay Canavarı* | AAA sinematikler, sanal prodüksiyon, gelişmiş saç/kürk fiziği (Strands), Orthographic projeler. | Volumetric Cloud/Fog geliştirmeleri, VDB desteği ve üst düzey görsel çıktı kalitesi. | Zayıf donanıma sahip solo veya küçük indie geliştiriciler (Editör performans yükü fazladır). |
| **UE 5.4.4** | ⚓ *Solo Geliştiricinin Güvenli Limanı* | Solo/Indie PC ve Konsol projeleri, stabil macera oyunları, optimizasyon odaklı 3D projeler. | **Neural Network Engine (NNE)**, optimize edilmiş Nanite Tessellation ve uzun süre test edilmiş en stabil UE5 sürümü. | En uç sınır deneysel özellikleri (MegaLights, Mesh Terrain) üretim aşamasında kullanmak isteyenler. |
| **UE 5.8.0** | 🌌 *Geleceğin Teknolojisi, Sınırsız Özgürlük* | Yeni nesil AAA oyunlar, devasa dikey araziler, çoklu dinamik ışıklandırmalı sahneler. | **Mesh Terrain** (yerleşik 3D arazi), **MegaLights**, **Lumen Lite** (mobil ve alt segment konsollar için optimize Lumen). | Kararlı, hatasız (bug-free) çalışma ve tüm eski eklentilerin (plugins) sorunsuz entegrasyonunu arayanlar. |

---

### 🤖 Yapay Zeka Karar Verici (AI Prompt)

Aşağıdaki promptu kopyalayarak ChatGPT, Claude veya Gemini gibi bir yapay zekaya gönderip projeniz için anında teknik direktör analizi alabilirsiniz:

```markdown
Sen kıdemli bir Unreal Engine teknik direktörüsün. Aşağıda detaylarını verdiğim oyun projem için en uygun Unreal Engine sürümünü (UE 4.27, UE 5.1, UE 5.3, UE 5.4.4 veya UE 5.8.0 arasından) seçmeme yardımcı olmanı istiyorum.

Proje Detaylarım:
- Oyun Türü: [Örn: Açık Dünya Simülasyonu, 2D Platformer, TPS Hayatta Kalma]
- Hedef Platformlar: [Örn: PC (Steam), Mobil (Android/iOS), Nintendo Switch, Konsol]
- Grafik Tarzı: [Örn: Fotogerçekçi, Stilize/Toon, Low-Poly]
- Ekip Boyutu: [Örn: Solo Geliştirici, 3 Kişilik Ekip, Büyük Stüdyo]
- Critical Mechanics: [Örn: Araç fiziği, devasa harita yükleme, yoğun NPC kalabalığı, detaylı yüz animasyonları]

Bana şunları analiz et:
1. Benim için en ideal Unreal Engine sürümü hangisidir ve neden?
2. Bu sürümü seçerken karşılaşabileceğim potansiyel performans veya entegrasyon riskleri nelerdir?
3. Sürümün hangi spesifik özellikleri (PCG, Nanite, Lumen vb.) benim projemde doğrudan fark yaratır?

BeyazAdam Unreal Engine Karar Verici şablonuna uygun olarak net, kısa ve teknik odaklı bir cevap ver.
```

---

## 🇬🇧 English Guide

Hi there! I'm **[BeyazAdam](https://github.com/BeyazAdam)**.

When starting a project in the Unreal Engine ecosystem, one of the most critical decisions that can lead to massive technical debt later is **choosing the wrong engine version**. This guide is designed to act as a lighthouse, helping you determine the most suitable Unreal Engine version for your project's genre, target platforms, team size, and art style in seconds.

> [!IMPORTANT]
> 🚀 To find the perfect engine version for your project in seconds, try our **[Interactive Version Selector](https://beyazadam.github.io/unreal-engine-version-guide/)**!

### 📌 Quick Decision Matrix (Strengths of Versions)

| Version | Slogan (Core Character) | Best Suited Projects | Why Choose It? (Key Features) | Who Should Avoid? |
| :--- | :--- | :--- | :--- | :--- |
| **UE 4.27** | 🛡️ *Old Friend, Rock-Solid* | Low-end mobile, HTML5, 2D games, retro/pixel art, and legacy VR. | Most stable version in the industry. Smallest build sizes. Excellent performance on older devices. | Developers who need Nanite, Lumen, or the latest features of the Chaos physics engine. |
| **UE 5.1** | 🚀 *First Footsteps of Next-Gen* | First-generation UE5 projects, moderately heavy Nanite/Lumen PC games, stable World Partition. | The first fully production-ready, stable UE5 release. Editor tools are robust and mature. | Projects with dense dynamic vegetation or advanced dynamic deformation requirements. |
| **UE 5.3** | 🎬 *Cinematic Genius & Detail Monster* | AAA cinematics, virtual production, advanced hair/fur physics (Strands), Orthographic camera support. | Volumetric Cloud/Fog improvements, sparse volume texture (VDB) support, top-tier rendering quality. | Solo/Indie developers with weak hardware (Editor performance overhead is high). |
| **UE 5.4.4** | ⚓ *The Safe Harbor for Solo Devs* | Solo/Indie PC and Console games, stable 3D adventures, optimization-focused projects. | **Neural Network Engine (NNE)**, optimized Nanite Tessellation, and the most stable current UE5 build. | Developers who want to use cutting-edge experimental features (MegaLights, Mesh Terrain) in production. |
| **UE 5.8.0** | 🌌 *Technology of the Future, Limitless Freedom* | Next-gen AAA games, massive vertical landscapes, scenes with hundreds of dynamic lights. | **Mesh Terrain** (native 3D landscapes), **MegaLights**, **Lumen Lite** (optimized Lumen for mobile/lower-end consoles). | Developers looking for bug-free stability and instant compatibility with legacy marketplace plugins. |

---

### 🤖 AI Decision Maker Prompt

Copy the prompt below and paste it into ChatGPT, Claude, or Gemini to get an instant Technical Director analysis for your project:

```markdown
You are a senior Unreal Engine Technical Director. I want you to help me choose the most suitable Unreal Engine version (out of UE 4.27, UE 5.1, UE 5.3, UE 5.4.4, or UE 5.8.0) for the game project detailed below.

Project Details:
- Game Genre: [e.g., Open World Simulation, 2D Platformer, TPS Survival]
- Target Platforms: [e.g., PC (Steam), Mobile (Android/iOS), Nintendo Switch, Console]
- Art Style: [e.g., Photorealistic, Stylized/Toon, Low-Poly]
- Team Size: [e.g., Solo Developer, 3-person Team, Large Studio]
- Critical Mechanics: [e.g., Vehicle physics, massive world loading, dense NPC crowds, detailed facial animations]

Please analyze:
1. What is the ideal Unreal Engine version for my project, and why?
2. What potential performance or integration risks might I face with this version?
3. Which specific features of this version (PCG, Nanite, Lumen, etc.) will make a direct difference in my project?

Provide a concise, technical, and direct response in alignment with the BeyazAdam Unreal Engine Decision Maker template.
```

---

## 📂 Detaylı Rehberler / Detailed Guides

* 🗺️ [Açık Dünya ve Simülasyon Detay Rehberi / Open World & Simulation Guide](file:///e:/GitHubs/ue_rehber/docs/open-world.md)
* 📱 [Mobil ve Stilize/Toon Oyunlar Detay Rehberi / Mobile & Stylized/Toon Guide](file:///e:/GitHubs/ue_rehber/docs/stylized-mobile.md)
