# 📱 Mobil ve Stilize/Toon Oyunlar Detay Rehberi / Mobile & Stylized/Toon Guide

Bu kılavuz; mobil platformlar (Android/iOS), el konsolları (Nintendo Switch, Steam Deck), stilize (Toon/Anime) grafik tarzı ve hafifletilmiş render mimarileri üzerine odaklanan projeler için hazırlanmıştır.

This guide focuses on mobile platforms (Android/iOS), handheld consoles (Nintendo Switch, Steam Deck), stylized (Toon/Anime) art directions, and lightweight rendering pipelines.

---

## 🇹🇷 Türkçe Detay Rehberi

### 1. Mobil ve El Konsolu Performansı (Switch, Steam Deck)

> [!IMPORTANT]
> Mobil ve taşınabilir donanımlarda pil tüketimi, termal kısılma (thermal throttling) ve kısıtlı bellek (RAM) nedeniyle sürüm seçimi hayati önem taşır.

*   **UE 4.27 (Saf Mobil Performans):** Eğer hedefiniz alt ve orta segment Android cihazlar ile Nintendo Switch ise, en düşük paket boyutu (build size) ve en optimize Forward Renderer bu sürümdedir. Ancak modern grafik kütüphanelerinin (Vulkan/Metal) yeni nimetlerinden faydalanamazsınız.
*   **UE 5.4.4 (Steam Deck ve Üst Segment Mobil):** Vulkan optimizasyonları ve **Neural Network Engine (NNE)** entegrasyonu sayesinde Steam Deck ve modern mobil işlemciler (Apple Silicon, Snapdragon Gen 2+) için en dengeli sürümdür. Masaüstü kalitesindeki shader kodlarını verimli bir şekilde derler.
*   **UE 5.8.0 (Geleceğe Yatırım):** Bu sürümle birlikte mobil render hatlarında köklü değişiklikler ve doğrudan Switch 2 / yeni nesil mobil GPU mimarilerine yönelik optimizasyonlar gelmektedir.

### 2. Lumen Lite ve Mobil Işıklandırma Devrimi

> [!NOTE]
> Klasik mobil oyunlarda ışıklandırmayı tamamen fırınlamak (bake etmek) tek performanslı seçenektir. Ancak gerçek zamanlı dinamik gün/gece döngüleri için yeni çözümler gerekmektedir.

*   **Klasik Mobil Çözüm (Static Baking):** UE 4.27 ve UE 5.1 üzerinde mobil için ışıkları tamamen fırınlamak (bake etmek) tek performanslı seçenektir. Dinamik gün/gece döngüsü mobil cihazları aşırı ısıtır.
*   **Lumen Lite (UE 5.8.0):** UE 5.8 ile gelen **Lumen Lite** teknolojisi, mobil cihazlarda ve el konsollarında gerçek zamanlı küresel aydınlatmayı (Global Illumination) yarı yarıya daha az GPU gücüyle çalıştırabilir hale getirmiştir. Dinamik ışıklandırmalı mobil projeler için devrim niteliğindedir.

### 3. Substrate ve Gelişmiş Toon Shader Yapısı

> [!TIP]
> Stilize oyunlarda (Genshin Impact veya Anime tarzı) özel gölgelendirme modelleri (Custom Shading Models) yerine Substrate kullanarak katmanlı ve performanslı materyaller üretebilirsiniz.

*   **Legacy Material Graph (UE 4.27 & 5.1):** Toon shading yapmak için materyal editöründe karmaşık matematiksel hileler (dot product, custom nodes) kullanmak gerekir. Sonuçlar ışık açısına göre tutarsız olabilir.
*   **Substrate (UE 5.3 ve Üzeri):** Unreal'ın yeni materyal sistemi olan Substrate, farklı materyal katmanlarını (örneğin stilize bir anime gözü üzerindeki ıslaklık ve mat cilt dokusunu) fiziksel olarak doğru şekilde birleştirmenizi sağlar.
*   **UE 5.8.0 Toon Shader İyileştirmeleri:** 5.8 sürümünde Substrate mimarisi stilize ve PBR olmayan (non-photorealistic) gölgelendirmeleri resmi olarak destekleyecek şekilde optimize edilmiştir. Hücresel gölgelendirme (Cel shading) ve kontur çizgisi (Outline) çizimi çok daha performanslıdır.

---

## 🇬🇧 English Detailed Guide

### 1. Mobile & Handheld Performance (Switch, Steam Deck)

> [!IMPORTANT]
> Battery efficiency, thermal throttling, and memory (RAM) limitations make the engine version critical for portable devices.

*   **UE 4.27 (Pure Mobile Performance):** If your target is low-to-mid segment Android devices and Nintendo Switch, this version offers the smallest shipping build size and the most optimized Forward Renderer. However, you miss out on modern Vulkan/Metal API features.
*   **UE 5.4.4 (Steam Deck & High-End Mobile):** The most balanced version for Steam Deck and modern mobile chipsets (Apple Silicon, Snapdragon Gen 2+), thanks to major Vulkan optimization and **Neural Network Engine (NNE)** integration.
*   **UE 5.8.0 (Future-proofing):** Introduces fundamental mobile rendering pipeline rewrites, paving the way for next-gen handheld architectures (like Switch 2) and high-end mobile GPUs.

### 2. Lumen Lite & Mobile Lighting Revolution

> [!NOTE]
> Baking lightmaps is the traditional way to achieve performance on mobile. However, dynamic cycles require modern real-time lighting solutions.

*   **Legacy Mobile Approach (Static Baking):** In UE 4.27 and 5.1, baking lightmaps is the only viable production method. Dynamic day/night cycles will trigger thermal throttling on mobile devices.
*   **Lumen Lite (UE 5.8.0):** Introduces **Lumen Lite**, allowing real-time Global Illumination on high-end mobile devices and handhelds at half the GPU performance cost. A game-changer for dynamic mobile lighting.

### 3. Substrate & Advanced Toon Shading

> [!TIP]
> Using the new Substrate framework allows you to blend realistic PBR and stylized toon layers efficiently without custom engine shader hacks.

*   **Legacy Material Graph (UE 4.27 & 5.1):** Achieving high-quality Cel-shading requires complex math workarounds (custom nodes, dot product math) in the material editor, which often break under dynamic lights.
*   **Substrate (UE 5.3+):** The new modular material framework allows physical blending of stylized layers (e.g., combining a highly stylized anime eye reflection with a matte skin shading layer) seamlessly.
*   **UE 5.8.0 Toon Shader Enhancements:** In 5.8, Substrate is optimized to natively support non-photorealistic rendering (NPR). Cel-shading, hatching, and dynamic outline generation are significantly more performant.
