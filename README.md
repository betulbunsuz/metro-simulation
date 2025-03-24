# metro-simulation

Bu proje, Ankara'daki metro ağı üzerinde en az aktarmalı ve en hızlı rotayı bulmak için BFS ve A* algoritmalarını kullanan bir metro simülasyonudur.

## Kullanılan Teknolojiler ve Kütüphaneler

- **Python**: Proje Python dilinde yazılmıştır.
- **heapq**: A* algoritmasında öncelik sırasına göre elemanları işlemek için kullanılan Python'un yerleşik `heapq` kütüphanesi kullanılmıştır. Bu kütüphane, sıralı bir veri yapısı olan ikili yığınları (binary heap) uygulamak için idealdir.
- **collections**: Python'un `collections` modülü, özellikle `deque` veri yapısı, BFS algoritmasında kuyruk işlemleri için kullanılmıştır.

## Algoritmaların Çalışma Mantığı

### BFS Algoritması

**Breadth-First Search (BFS)** algoritması, bir başlangıç düğümünden başlar ve her bir seviyedeki tüm komşu düğümleri sırayla keşfeder. Bu algoritma, en az aktarmalı rotaları bulmada etkilidir çünkü her bir adımda sadece bir seviyedeki komşuları kontrol eder. BFS'nin temel özelliklerinden biri, bir hedefe ulaşılmadan önce en kısa yolu bulma garantisi sunmasıdır. Bu algoritma, doğrusal bir yapıyı takip ettiği için en az aktarma gereksinimiyle rotaları belirler.

### A* Algoritması

**A* (A-star)** algoritması, BFS algoritmasından farklı olarak hem maliyet hem de hedefe olan tahmin edilen mesafeyi göz önünde bulundurur. A* algoritmasında her bir düğüm, iki faktöre göre değerlendirilir: geçerli mesafe (g) ve hedefe olan tahmin edilen mesafe (h). Bu nedenle, A* daha verimli bir şekilde en hızlı rotayı bulur. Hedefe en hızlı ulaşmayı sağlayan rotaları keşfetmek için kullanılan heuristic (kestirimsel) fonksiyon, optimizasyon sağlar.

### Neden Bu Algoritmaları Kullandık?

- **BFS**: En az aktarmalı rotayı bulmak için ideal bir algoritma olup, metro ağı gibi yapılar için mükemmel bir seçimdir.
- **A***: En hızlı rotayı bulmak için A* algoritması, tahmin edilen hedef mesafesini kullanarak daha verimli bir keşif yapar ve dolayısıyla daha kısa süreli yolculukları bulmak için uygundur.
  
### Projenin geliştirilmesi
Dinamik rota güncellemesi yapılabilir. Gerçek zamanlı trafik bilgisi ekleyerek, metro hattındaki aksaklıkları ve gecikmeleri dikkate alarak rotaların dinamik bir şekilde güncellenebilir.

## Örnek Kullanım ve Test Sonuçları

Proje, en az aktarmalı ve en hızlı rotayı bulmak için şu şekilde kullanılabilir:

```python
metro = Metro()  # Metro ağı sınıfının bir örneği

# BFS ile en az aktarmalı rota
rota_bfs = metro.en_az_aktarmali_rota_bul("AŞTİ", "OSB")
print("En az aktarmalı rota:", rota_bfs)

# A* ile en hızlı rota
rota_astar = metro.en_hizli_rota_bul("AŞTİ", "OSB")
print("En hızlı rota:", rota_astar)
