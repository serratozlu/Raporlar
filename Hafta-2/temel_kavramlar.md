## İşletim Sistemi Temelleri (OS Basics)
İşletim sistemi, donanım kaynaklarını yöneten ve uygulama programları için ortak servisler sağlayan bir sistem yazılımıdır. Modern bir işletim sisteminin temel yapı taşları şunlardır:

### Kernel (Çekirdek) Nedir ve Görevleri Nelerdir?
- Kernel, işletim sisteminin en düşük seviyeli ve en kritik bileşenidir. Bilgisayar donanımı ile uygulama yazılımları arasında "mutlak hakem" görevi görür.

- Kaynak Yönetimi: CPU zamanı, bellek alanı ve I/O (Girdi/Çıktı) cihazlarının hangi süreç tarafından ne kadar süreyle kullanılacağını belirler.

- Sistem Çağrıları (System Calls): Uygulamaların donanıma doğrudan erişimi yoktur. Bir uygulama dosya okumak veya ekrana görüntü basmak istediğinde, Kernel'den bir "sistem çağrısı" ile izin ister.

#### Kernel Türleri:

- Monolitik Kernel: Tüm servislerin (sürücüler, dosya yönetimi vb.) tek bir büyük blokta çalıştığı yapıdır.

- Microkernel: Sadece en temel görevlerin çekirdekte tutulduğu, diğer servislerin kullanıcı alanında çalıştığı modüler yapı.

### Süreç (Process) ve İş Parçacığı (Thread) Farkı
İşletim sisteminde bir işin yürütülmesi iki farklı seviyede ele alınır:

- Süreç: Çalıştırılmakta olan bir programın somut halidir. Her sürecin kendine ait bir adres alanı, veri yığını ve kod segmenti bulunur. Süreçler birbirinden izoledir; birinin hatası diğerini doğrudan etkilemez.

- İş Parçacığı: Bir süreç içerisinde birden fazla koldan yürütülen iş dizileridir. Aynı sürecin içindeki tüm thread'ler aynı bellek kaynaklarını paylaşır.

#### Neden Thread Kullanılır?
Örneğin bir web tarayıcısında, bir thread kullanıcı arayüzünü kontrol ederken, diğer bir thread dosya indirip, üçüncüsü sayfayı render edebilir. Bu durum, "paralel programlama" ve yüksek performans sağlar.


### Bellek Yönetimi (Memory Management)
İşletim sisteminin ana belleği verimli kullanmak için uyguladığı karmaşık bir stratejidir.

- Adres Alanı Dönüştürme: İşlemci, mantıksal adresler üretir. Bellek Yönetim Birimi ise bu adresleri RAM üzerindeki fiziksel adreslere dönüştürür.

- Sanal Bellek: Fiziksel RAM yetersiz kaldığında, sabit diskin bir kısmının RAM gibi kullanılmasıdır. Bu sayede fiziksel bellekten çok daha büyük programlar çalıştırılabilir.

- Sayfalama: Belleğin küçük, sabit boyutlu parçalara  bölünmesidir. Bu teknik, bellekte "parçalanma" sorununu çözer ve verinin RAM'in herhangi bir boş yerinde saklanmasına olanak tanır.

### CPU Zamanlayıcıları (Schedulers)
Çok görevli sistemlerde, işlemciyi hangi sürecin ne kadar süreyle kullanacağını belirleyen algoritmalar bütünüdür.

- Long-Term Scheduler: Hangi süreçlerin sisteme alınacağına karar verir.

- Short-Term Scheduler: Bellekteki "Hazır" kuyruğundan bir süreci seçer ve CPU'yu ona tahsis eder. Milisaniyeler içinde karar verir.

- Bağlam Değiştirme: CPU bir süreçten diğerine geçerken, eski sürecin durumunu (register değerleri, program sayacı vb.) kaydeder ve yeni sürecin bilgilerini yükler. Bu işlem ne kadar hızlıysa sistem o kadar akıcı hissedilir.