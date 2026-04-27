# AĞ TEMELLERİ (NETWORKING) DERİNLEMESİNE ANALİZ RAPORU

## 1. Temel Bileşenler ve Kavramlar

### IP, Port ve DNS: Dijital Adresleme
* **IP (Internet Protocol):** Cihazın kimlik numarasıdır. Verinin hangi "binaya" gideceğini belirler.
* **Port:** Binadaki "daire numarasıdır". Verinin hangi uygulamaya (Web, Oyun, Veritabanı) teslim edileceğini belirler.
* **DNS (Domain Name System):** İnsan dostu isimleri (google.com) makinelerin anladığı IP adreslerine (142.250.185.78) çevirir.

### En Sık Kullanılan Protokol Portları
| Port | Protokol | Kullanım Amacı |
| :--- | :--- | :--- |
| **22** | SSH | Güvenli uzaktan yönetim (Terminal) |
| **53** | DNS | Alan adı sorgulama işlemleri |
| **80** | HTTP | Şifrelenmemiş web trafiği |
| **443** | HTTPS | Şifrelenmiş (Güvenli) web trafiği |

---

## 2. Taşıma Katmanı: TCP vs UDP

### TCP "3-Way Handshake" (Üçlü El Sıkışma)
TCP, veriyi göndermeden önce güvenli bir hat kurar. Bu süreç şu şekilde işler:
1.  **SYN:** İstemci bağlantı isteği gönderir.
2.  **SYN-ACK:** Sunucu isteği onaylar ve karşılık verir.
3.  **ACK:** İstemci onaylandığını teyit eder ve veri aktarımı başlar.



| Özellik | TCP (Güven Veren) | UDP (Hız İsteyen) |
| :--- | :--- | :--- |
| **Bağlantı** | Kurulması zorunlu (Handshake) | Bağlantı kurulmaz |
| **Hata Kontrolü** | Eksik paketleri tekrar ister | Kayıp paketleri umursamaz |
| **Kullanım** | Dosya transferi, Web | Canlı yayın, Online oyun |

---

## 3. Paket Yapısı ve Encapsulation (Kapsülleme)

Bir veri ağa çıktığında katman katman paketlenir. Buna **Encapsulation** denir. Her katman kendi "zarfını" ekler:

* **Ethernet Header:** Modemin (MAC) bir sonraki sıçrama noktasını bilir.
* **IP Header:** Kaynak ve hedef IP adreslerini içerir.
* **TCP/UDP Header:** Port bilgilerini ve paket sırasını tutar.
* **Payload:** Asıl taşınan veridir.



---

## 4. Ağ Analiz ve Teşhis Araçları

### Ping (ICMP Echo)
Hedef makinenin erişilebilir olup olmadığını kontrol eder.
> **Kritik Bilgi:** Bazı sunucular güvenlik için ICMP paketlerini (Ping) engelleyebilir; bu sunucunun kapalı olduğu anlamına gelmez.

### Traceroute (Yol İzleme)
Verinin hedefe giderken geçtiği tüm durakları (router) listeler.
* **Çalışma Mantığı:** Paketin içindeki **TTL (Time To Live)** değeri her durakta 1 azaltılır. Değer 0 olduğunda durak "buradayım" diye cevap döner.

### Nslookup (DNS Sorgulama)
Bir alan adının hangi IP'ye bağlı olduğunu veya DNS kayıtlarını görmeni sağlar.

---

## 5. Genel Sistem Akış Şeması
`Kullanıcı Sorgusu` → `DNS Çözümleme` → `TCP Handshake` → `HTTP Request (Paketler halinde)` → `Sunucu Yanıtı`

**Özet :** Verinin bütünlüğünü koruyarak (TCP) en doğru adrese (IP) ve en doğru uygulamaya (Port) en hızlı şekilde ulaşmasını sağlamaktır.