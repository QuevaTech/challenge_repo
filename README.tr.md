# 🎲 Entropi Yarışması (The Entropy Challenge)

[🇬🇧 Read in English](README.md) | [🇹🇷 Türkçe Oku](README.tr.md)

## Giriş
**Radyo Frekansı (RF) Gürültüsünü** özel bir **Sinir Ağı (Neural Network)** mimarisi ile işleyen ve SHA-3 (Keccak) işlemcisiyle güçlendiren yeni nesil bir rastgele sayı üreteci geliştirdik. Bu kaynağın **Gerçek Rastgelelik (True Randomness)** kalitesinde olduğunu ve ideal gürültü kaynaklarından ayırt edilemeyeceğini iddia ediyoruz.

Çıktıları ve doğrulama raporlarını yayınlıyoruz—fakat **kaynak kodu paylaşmıyoruz**. Yarışma çok basit: **Yanıldığımızı kanıtlayın.**

## Veri
- **Örnek Dosya:** `data/random_sample.bin` (~17 MB)
- **Kalite:** **NIST STS (SP 800-22)** ve **NIST SP 800-90B** standartlarına göre doğrulanmıştır.
- **Entropi:** >0.999 bit/bit.

Detaylı raporları [NIST_REPORT.md](NIST_REPORT.md) dosyasında bulabilirsiniz.

## 🏆 Yarışma (Challenge)
Bu sistemi "kırmayı" başaran herkese itibar ve tanınırlık vadediyoruz.

### Kategoriler ve Ödüller

#### 🥇 Seviye 1: Kâhin (The Predictor) - Bir Sonraki Bit Testi
**Ödül:** **Hall of Fame (Onur Listesi) & Başarı Sertifikası**
**Görev:** Size verilen $N$ uzunluğundaki bit dizisine bakarak, $N+1$. biti %50'den istatistiksel olarak anlamlı derecede yüksek bir ihtimalle ($p < 0.001$) tahmin edin.

#### 🥈 Seviye 2: Ayırt Edici (The Distinguisher)
**Ödül:** **Mansiyon (Honorable Mention)**
**Görev:** Ürettiğimiz veriyi, `os.urandom` veya donanımsal TRNG çıktılarından ayırt edebilen (başarı oranı > 0.01 olan) bir algoritma geliştirin.

#### 🥉 Seviye 3: Desen Avcısı (Pattern Finder)
**Ödül:** **Teşekkür (Acknowledgment)**
**Görev:** Standart NIST testlerinin gözden kaçırdığı, verideki gizli bir periyodik tekrarı veya belirgin bir sapmayı (bias) tespit edin.

## Nasıl Katılabilirsiniz?
1. Bu depo'yu (repository) forklayın.
2. Analiz kodunuzu (Python, C, Matlab vb.) yazın.
3. Bulgularınızı ve kanıtınızı içeren bir "Issue" açın.
4. Eğer kanıtınız doğrulanırsa, **Hall of Fame** listemize adınızı ekleyeceğiz.

## 🏅 Hall of Fame (Onur Listesi)
| Tarih | Araştırmacı | Başarı |
|-------|-------------|--------|
| - | - | - |

---
*Powered by Deep Neural Stochastic Processes & Keccak*
