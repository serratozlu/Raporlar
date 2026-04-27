# BİLGİSAYAR MİMARİSİ RAPORU
### Bilgisayar Mimarisi Nedir?

Bilgisayar mimarisi, bir bilgisayarın donanımsal bileşenlerinin nasıl çalıştığını ve birbiriyle nasıl iletişim kurduğunu inceleyen alandır.

##  CPU (Central Processing Unit) Nedir ?
CPU (Merkezi İşlem Birimi) sunucudaki temel bilgi işlem birimi olan donanım bileşenidir. Sunucular ve diğer akıllı cihazlar, verileri dijital sinyallere dönüştürür ve bunlar üzerinde matematiksel işlemler gerçekleştirir. 
    
CPU, sinyalleri işleyen ve bilgi işlem olanağı sağlayan birincil bileşendir. Bir bilgi işlem cihazının beyni olarak görev yapar. Bellekten talimatları getirir, gerekli görevleri gerçekleştirir ve çıktıyı belleğe geri gönderir. İşletim sistemini ve uygulamaları çalıştırmak için gereken tüm bilgi işlem görevlerini yerine getirir.

### CPU'nun Tarihsel Gelişimi Nasıldır ?

- 1950'ler (İlk Adımlar): UNIVAC 1103 gibi bilgisayarların bir parçası olarak ilk merkezi işlem birimi kavramları ortaya çıkmıştır.

- 1960'lar (Entegre Devreler): Transistörlerin yerini binlerce devre elemanını tek bir çipe sığdıran entegre devreler aldı.

- 1971 (Mikroişlemci Devrimi): Intel 4004, dünyanın ilk ticari mikroişlemcisi (tek çipli CPU) olarak üretildi ve hesap makinelerinde kullanıldı.

- 1980'ler - Günümüz (Hızlı Gelişim): Intel 8086, Pentium serisi ve günümüzün çok çekirdekli (multi-core) işlemcileriyle (Core i9 vb.) inanılmaz bir işlem gücüne ulaşıldı. 
    
CPU'nun tarihi, temel olarak "daha küçük, daha hızlı ve daha verimli" olma prensibine dayanır. 

### CPU İç Yapısı Nasıldır ?

CPU temelde iki ana bölümden oluşur:

- ALU (Aritmetik Mantık Birimi)
    
    Veriler üzerinde temel aritmetik işlemleri (toplama, çıkarma, çarpma ve bölme) ve mantıksal işlemleri (VE, VEYA, DEĞİL) gerçekleştirir. CPU içindeki yazmaçlardan veri alıp bunları kontrol biriminden gelen talimatlara göre işler ve sonucu üretir.

- Kontrol Birimi (Control Unit) 

    Kontrol birimi komut işlemeyi yönetip CPU içindeki ve diğer bilgisayar bileşenleri arasındaki veri akışını koordine eder. Bellekten getirilen talimatları yorumlayıp bunları CPU'nun çalıştırabileceği mikro işlemlere dönüştüren bir komut kod çözücü bileşenine sahiptir. Kontrol birimi, diğer CPU bileşenlerini gerekli işlemleri gerçekleştirmeleri için yönlendirir.

### CPU Nasıl Çalışır ?

Fetch – Decode – Execute döngüsü:

- Komutu getir (Fetch)
- Komutu çöz (Decode)
- Komutu çalıştır (Execute)


## RAM (Random Access Memory) Nedir ?

RAM (Rastgele Erişimli Bellek), bilgisayar ve mobil cihazların aktif olarak çalışan uygulamaları, verileri ve işletim sistemi dosyalarını geçici olarak depoladığı hızlı, geçici (uçucu) bir sistem belleğidir. İşlemcinin (CPU) verilere anında erişmesini sağlayarak cihazın hızını ve çoklu görev performansını artırır; cihaz kapandığında içindeki veriler silinir.

### RAM'in Temel Özellikleri ve Görevleri Nelerdir ?
- Geçici Depolama: Sadece cihaz açıkken veri tutar, kapatıldığında veriler kaybolur.

- Yüksek Hız: Sabit disklere (HDD/SSD) göre binlerce kat daha hızlıdır.

- İşlemci ile Çalışma: İşlemci, o an ihtiyaç duyduğu verileri RAM'den alır, bu da performansı doğrudan etkiler.

- Çoklu Görev (Multitasking): Daha fazla RAM, aynı anda daha fazla uygulama çalıştırırken cihazın yavaşlamasını önler.


### RAM Neden Önemlidir ?
- Yüksek Performans: RAM miktarı ne kadar yüksek olursa, sistem o kadar fazla veriyi aynı anda işleyebilir, bu da oyun, kurgu veya çoklu görevlerde hız sağlar.

- Köprü Görevi: 2 Sabit sürücü ile işlemci arasındaki yavaşlığı giderir.

- Kapasite: Yetersiz RAM durumunda bilgisayar yavaşlar veya donar, çünkü işlemci verileri daha yavaş olan sabit diske yazmak zorunda kalır.

## Cache (Önbellek) Nedir?
Cache, CPU ile RAM arasındaki çok hızlı bir ara bellektir. 1980’lerde CPU performansını artırmak için geliştirildi. CPU’nun RAM’e gitmesini azaltmak, hız kazanmak amacıyla ortaya çıkarılmıştır.

### Cache Katmanları (L1, L2, L3) Nelerdir?

Cache bellek kendi içinde katmanlara ayrılır:

- L1 Cache (En hızlı): CPU’nun içinde. Çok küçük ama aşırı hızlıdır.En sık kullanılan veriler buradadır.

- L2 Cache: L1’den biraz daha büyüktür ama daha yavaştır.

- L3 Cache: En büyük cache katmanıdır. Birden fazla çekirdek tarafından ortak kullanılır.

### Hız Sıralaması
L1 > L2 > L3 > RAM > Disk

### Neden Kritik ?
- CPU’nun bekleme süresini azaltır
- Performansı ciddi şekilde artırır 
- Özellikle oyun, veri işleme ve backend sistemlerde çok önemlidir.


## RAM ve Cache Arasındaki Farklar

| Özellik | Cache | RAM |
| :--- | :--- | :--- |
| **Hız** | Çok hızlı | Daha yavaş |
| **Boyut** | Küçük | Büyük |
| **Konum** | CPU içinde | Anakartta |
| **Amaç** | CPU'yu hızlandırmak | Programları çalıştırmak |


## Genel Sistem Akış Hızı Nasıldır ? 
En hızlıdan en yavaşa doğru veri akışı aşağıdaki gibidir  
- `CPU ↔ Cache ↔ RAM ↔ Disk`

Burada amaç CPU'ya en hızlı veriyi ulaştırmaktır. 
