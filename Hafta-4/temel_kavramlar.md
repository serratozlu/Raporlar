# 4) Dosya Sistemleri ve Depolama Mantığı

## Giriş

Bilgisayarlarda verilerin düzenli şekilde saklanabilmesi için **dosya sistemleri** kullanılır. İşletim sistemi; dosyaların nerede tutulduğunu, nasıl okunacağını ve nasıl yazılacağını bu sistemler sayesinde bilir.  

Ayrıca depolama birimlerinin çalışma mantığını anlamak, bilgisayar performansının neden değiştiğini kavramak açısından önemlidir. Özellikle HDD ve SSD arasındaki farklar, veri erişim hızlarını doğrudan etkiler.

---

# Dosya Sistemi Nedir?

Dosya sistemi; bir depolama aygıtındaki verilerin düzenlenmesini sağlayan yapıdır.

Örneğin:

- Dosyaların isimleri
- Klasör yapıları
- Yetkilendirme sistemi
- Veri konumları
- Boş alan yönetimi

gibi işlemler dosya sistemi tarafından kontrol edilir.

Bir işletim sistemi diski kullanabilmek için onu belirli bir dosya sistemi ile biçimlendirir.

---

# NTFS – ext4 – APFS Karşılaştırması

## 1. NTFS

NTFS (**New Technology File System**) Microsoft tarafından geliştirilmiştir ve genellikle Windows işletim sistemlerinde kullanılır.

### Özellikleri

- Büyük dosya desteği sunar
- Dosya izinleri gelişmiştir
- Günlükleme (journaling) sistemi vardır
- Şifreleme desteği sağlar
- Windows ile tam uyumludur

### Avantajları

- Güvenlidir
- Veri kaybı riskini azaltır
- Büyük disklerde verimli çalışır

### Dezavantajları

- Linux ve macOS üzerinde tam performansla çalışmayabilir
- Kapalı kaynak yapıya sahiptir

---

## 2. ext4

ext4, Linux sistemlerinde en yaygın kullanılan dosya sistemidir.

### Özellikleri

- Yüksek performans sağlar
- Günlükleme desteği vardır
- Büyük dosya ve disk desteği sunar
- Linux çekirdeğiyle uyumlu çalışır

### Avantajları

- Hızlıdır
- Kararlıdır
- Sunucularda yaygın kullanılır

### Dezavantajları

- Windows tarafından doğal olarak desteklenmez
- macOS üzerinde ek yazılım gerektirebilir

---

## 3. APFS

APFS (**Apple File System**) Apple tarafından geliştirilmiştir.

macOS, iPhone ve iPad cihazlarında kullanılır.

### Özellikleri

- SSD’ler için optimize edilmiştir
- Şifreleme desteği güçlüdür
- Snapshot özelliği sunar
- Çok hızlı kopyalama işlemleri yapabilir

### Avantajları

- Apple cihazlarında yüksek performans sağlar
- SSD ile çok verimli çalışır
- Güçlü güvenlik özellikleri içerir

### Dezavantajları

- Windows ile uyumlu değildir
- Apple ekosistemine bağımlıdır

---

# NTFS – ext4 – APFS Genel Karşılaştırma

| Özellik | NTFS | ext4 | APFS |
|---|---|---|---|
| İşletim Sistemi | Windows | Linux | macOS / iOS |
| Günlükleme | Var | Var | Var |
| SSD Optimizasyonu | Orta | İyi | Çok İyi |
| Güvenlik | Yüksek | Yüksek | Çok Yüksek |
| Açık Kaynak | Hayır | Evet | Hayır |
| Büyük Dosya Desteği | Var | Var | Var |

---

# Blok Yapısı Nedir?

Depolama aygıtlarında veriler doğrudan tek parça halinde saklanmaz. Bunun yerine küçük parçalara ayrılır. Bu parçalara **blok** denir.

Örneğin:

Bir dosya 10 KB boyutunda olabilir ancak disk bunu:

- 4 KB
- 4 KB
- 2 KB

şeklinde bloklar halinde saklayabilir.

---

## Blok Mantığının Önemi

İşletim sistemi verileri bloklar halinde okur ve yazar.

Bu yapı sayesinde:

- Veri erişimi hızlanır
- Disk yönetimi kolaylaşır
- Boş alan kontrolü yapılabilir
- Dosyalar organize tutulur

---

## Blok Boyutu

Her dosya sisteminin belirli bir blok boyutu vardır.

Örnek:

| Blok Boyutu | Kullanım |
|---|---|
| 4 KB | Küçük dosyalar için yaygın |
| 8 KB | Daha büyük veri işlemleri |
| 16 KB+ | Sunucu ve veri tabanı sistemleri |

---

## Fragmentation (Parçalanma)

Dosyalar farklı bloklara dağılırsa disk erişimi yavaşlayabilir.

Bu duruma **fragmentation** denir.

Özellikle HDD’lerde büyük performans kaybına neden olabilir.

SSD’lerde ise etkisi çok daha azdır.

---

# HDD Nedir?

HDD (**Hard Disk Drive**) mekanik çalışan depolama birimidir.

İçerisinde:

- Dönen manyetik diskler
- Okuma/yazma kafası
- Motor sistemi

bulunur.

---

## HDD Çalışma Prensibi

HDD’de veriler manyetik plakalar üzerine yazılır.

Çalışma sırası:

1. Disk döner
2. Okuma/yazma kafası hareket eder
3. İstenen veri bulunur
4. Veri okunur veya yazılır

Bu yapı tamamen fiziksel hareket içerdiği için hız sınırlıdır.

---

## HDD Avantajları

- Ucuzdur
- Büyük depolama alanı sunar
- Arşivleme için uygundur

---

## HDD Dezavantajları

- Yavaştır
- Gürültülüdür
- Darbelere karşı hassastır
- Mekanik aşınma yaşar

---

# SSD Nedir?

SSD (**Solid State Drive**) mekanik parça içermeyen depolama birimidir.

Veriler flash bellek hücrelerinde saklanır.

Telefonlardaki depolama mantığına benzer şekilde çalışır.

---

## SSD Çalışma Prensibi

SSD’de:

- Hareketli parça yoktur
- Elektriksel veri aktarımı yapılır
- Veri doğrudan bellek hücrelerinden okunur

Bu nedenle erişim süresi çok düşüktür.

---

# HDD ve SSD Karşılaştırması

| Özellik | HDD | SSD |
|---|---|---|
| Çalışma Tipi | Mekanik | Elektronik |
| Hız | Düşük | Çok Yüksek |
| Gürültü | Var | Yok |
| Güç Tüketimi | Fazla | Daha Az |
| Dayanıklılık | Düşük | Daha Yüksek |
| Fiyat | Daha Ucuz | Daha Pahalı |

---

# SSD Neden Daha Hızlıdır?

SSD’nin hızlı olmasının temel nedenleri:

- Hareketli parça bulunmaması
- Veriye doğrudan erişebilmesi
- Düşük gecikme süresi
- Paralel veri işleme yapabilmesi

HDD’de ise kafa fiziksel olarak hareket etmek zorundadır.

Bu yüzden SSD’ler:

- İşletim sistemini daha hızlı açar
- Programları hızlı çalıştırır
- Oyun yükleme sürelerini azaltır
- Dosya kopyalama işlemlerini hızlandırır

---

# Veri Okuma/Yazma Hızı Nereden Gelir?

Bir depolama biriminin hızı şu faktörlere bağlıdır:

## 1. Erişim Süresi

Veriye ulaşmak için geçen süre.

SSD’de çok düşüktür.

---

## 2. Aktarım Hızı

Bir saniyede taşınabilen veri miktarıdır.

Örneğin:

- HDD → 100-150 MB/s
- SATA SSD → 500 MB/s
- NVMe SSD → 3000+ MB/s

---

## 3. Donanım Teknolojisi

- SATA
- NVMe
- PCIe

gibi teknolojiler veri yolunu hızlandırır.

---

# Günlükleme (Journaling) Nedir?

Modern dosya sistemlerinde kullanılan güvenlik yöntemidir.

Dosya sistemi işlem yapmadan önce işlemi bir günlük kaydına yazar.

Eğer elektrik kesilirse sistem:

- Hangi işlemin yarım kaldığını anlayabilir
- Veri bozulmasını azaltabilir

NTFS, ext4 ve APFS bu sistemi kullanır.

---

# Sonuç

Dosya sistemleri, verilerin düzenli ve güvenli saklanmasını sağlar. NTFS, ext4 ve APFS farklı işletim sistemlerine göre optimize edilmiştir.

Depolama tarafında ise HDD ve SSD arasındaki temel fark çalışma prensibidir:

- HDD mekanik çalışır
- SSD elektronik çalışır

Bu nedenle SSD’ler çok daha hızlıdır.

Ayrıca blok yapısı ve veri erişim yöntemleri, depolama performansının temelini oluşturur. Bu konuların öğrenilmesi, bilgisayar performansının neden değiştiğini anlamayı sağlar.