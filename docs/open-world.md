# 🌍 Açık Dünya ve Simülasyon Detay Rehberi / Open World & Simulation Guide

Bu kılavuz; büyük ölçekli haritalar, sürüş simülasyonları (AC/ETS2 modlama projeleri vb.), Blender entegrasyonu ve Unreal Engine'in yeni nesil render teknolojilerini hedefleyen projeler için hazırlanmıştır.

This guide is curated for projects targeting large-scale maps, driving simulations (AC/ETS2 modding style), Blender integration, and next-gen rendering pipelines in Unreal Engine.

---

## 🇹🇷 Türkçe Detay Rehberi

### 1. Dikey Araziler ve Blender Entegrasyonu

> [!NOTE]
> Klasik Landscape (Arazi) sistemi dikey uçurumlarda doku esnemelerine (stretching) sebep olur. Blender'dan aktarılan karmaşık dikey coğrafyalarda sürüm seçimi kritik bir rol oynar.

*   **UE 5.4.4 (Nanite Tessellation):** UE 5.4 ile gelen Nanite Tessellation, Blender'dan getirdiğiniz statik mesh'lere veya Landscape katmanlarına doğrudan materyal üzerinden yüksek kaliteli yükseklik (Displacement) vererek bu esneme sorununu tamamen çözer.
*   **UE 5.8.0 (Mesh Terrain):** Eğer projenizde mağaralar, tüneller ve 90 derecelik dikey uçurumlar çok yoğunsa, UE 5.8'in **Mesh Terrain** özelliği standart Landscape sınırlamalarını tamamen ortadan kaldırır. Arazileri doğrudan 3D mesh gibi biçimlendirebilir ve üzerinde delikler açabilirsiniz.
*   **Blender - Datasmith & FBX:** Blender modellerinizin ölçek (Scale) ve UV haritalarını bozmadan aktarmak için UE 5.4 ve üzerinde **Send to Unreal** eklentisini kullanmak, el yapımı köprü ve liman tasarımları için en sorunsuz iş akışını sunar.

### 2. PCG (Procedural Content Generation) Gelişimi

> [!IMPORTANT]
> Solo geliştiriciler için harita detaylandırmasını otomatikleştiren PCG sistemi sürümler arasında kararlılık açısından büyük farklar gösterir.

*   **UE 5.1:** PCG sistemi henüz deneyseldir. Çökmeler (crashes) sıktır ve Spline takibi zordur.
*   **UE 5.3:** PCG stabil hale gelmiştir ancak harita büyüdükçe bellek tüketimi (RAM leaks) yaşanabilir.
*   **UE 5.4.4 (Önerilen):** Yol çizgileri, kaldırım kenarları, bariyerler ve bitki örtüsünün yolları takip etmesi için en stabil PCG sürümüdür. **PCG Biome Core** eklentileri ile bölgesel orman ve şehir detaylandırmaları saniyeler sürer.
*   **UE 5.8.0:** PCG hiyerarşisi Runtime (çalışma zamanı) optimizasyonlarına sahiptir. Çok büyük haritalarda yükleme (streaming) sürelerini en aza indirir.

### 3. Lumen, Virtual Shadow Maps ve MegaLights Karşılaştırması

> [!WARNING]
> Çok fazla dinamik ışık barındıran sahnelerde eski Unreal Engine 5 sürümleri ciddi FPS düşüşlerine yol açacaktır.

*   **Görsel Kalite:** ETS2/AC benzeri fotogerçekçilik için Lumen donanımsal ışın izleme (Hardware Ray Tracing - HWRT) gerektirir.
*   **Gelişmiş Işıklandırma (MegaLights - UE 5.8.0):** Şehir içi veya liman sahnelerinde yüzlerce sokak lambasının ve araç farının aynı anda gölge vermesini istiyorsanız, UE 5.8'in **MegaLights** özelliği performansı düşürmeden dinamik ışık patlamalarını yönetmenizi sağlar. UE 5.4 ve öncesinde bu durum ciddi performans kayıplarına yol açar.
*   **Gölge Optimizasyonu (Virtual Shadow Maps):** Büyük açık dünyalarda yaprakların ve küçük detayların gölgeleri performansı baltalar. UE 5.4.4 sürümü, VSM önbellekleme (caching) optimizasyonu sayesinde sürüş esnasında gölge güncellemelerinden kaynaklanan FPS droplarını (stuttering) minimuma indirir.

---

## 🇬🇧 English Detailed Guide

### 1. Vertical Landscapes & Blender Integration

> [!NOTE]
> Standard Landscape systems suffer from texture stretching on sheer vertical cliffs. Choosing the right engine version dictates your Blender importing workflow.

*   **UE 5.4.4 (Nanite Tessellation):** UE 5.4's Nanite Tessellation solves texture stretching by applying high-fidelity displacement directly to imported static meshes or landscape layers.
*   **UE 5.8.0 (Mesh Terrain):** If your project relies heavily on tunnels, caves, and 90-degree vertical drops, UE 5.8's **Mesh Terrain** removes conventional landscape grid limits, allowing you to sculpt and puncture terrain like a 3D model.
*   **Blender - Datasmith & FBX:** Using the **Send to Unreal** addon in UE 5.4+ offers the most seamless pipeline for custom port structures and bridge meshes, keeping UVs and collision scales perfectly intact.

### 2. PCG (Procedural Content Generation) Evolution

> [!IMPORTANT]
> For solo developers, automating map detail distribution via PCG varies significantly in stability across engine versions.

*   **UE 5.1:** PCG is experimental. Crashing is frequent, and spline tracking is rudimentary.
*   **UE 5.3:** PCG is stable but suffers from memory leaks on massive coordinates.
*   **UE 5.4.4 (Recommended):** The most reliable version for spline-aligned PCG (guardrails, road markings, streetlights). Incorporates **PCG Biome Core** for efficient foliage ecosystem distribution.
*   **UE 5.8.0:** Features runtime optimization improvements, dramatically reducing streaming hiccups on massive open-world coordinates.

### 3. Lumen, Virtual Shadow Maps & MegaLights Comparison

> [!WARNING]
> Multi-light environments in older UE5 releases can cause severe CPU bottlenecks.

*   **Visual Fidelity:** For ETS2/AC photorealism, Lumen Hardware Ray Tracing (HWRT) is highly recommended.
*   **Advanced Lighting (MegaLights - UE 5.8.0):** If your harbor or city scene features hundreds of dynamic streetlights and car headlights casting shadows simultaneously, UE 5.8's **MegaLights** handles this dynamically without the performance tanking. Pre-5.8 versions will struggle under this light count.
*   **Shadow Optimization (Virtual Shadow Maps):** Rendering micro-shadows from dense foliage ruins performance. UE 5.4.4 features optimized VSM caching, preventing CPU stuttering during high-speed driving simulations.
