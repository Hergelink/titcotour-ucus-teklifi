# Titcotour Uçuş Teklifi Hazırlayıcı

Vercel için tasarlanmış basit bir uygulama. Amadeus / GDS metinlerini API ile yapılandırır; çalışanlar fiyat ve koşulları kontrol edip düzenledikten sonra teklifi PDF olarak kaydeder veya e-posta metni kopyalar.

## Kurulum
1. GitHub'da **yeni bir depo** oluşturun (otel uygulamanızın dosyalarının üzerine yazmayın).
2. Bu klasörün içindeki `index.html`, `vercel.json` ve `api/parse.js` dosyalarını repoya yükleyin.
3. Vercel > Add New Project > GitHub deposunu seçin. Framework: **Other**. Root Directory: dosyalar repoda kökteyse **boş**.
4. Environment Variables alanına `OPENAI_API_KEY` ekleyin. Gerekirse `OPENAI_MODEL` değeri `gpt-4.1-mini` olabilir.
5. Deploy yapın. API anahtarını GitHub'a veya tarayıcı koduna koymayın.

## Kullanım
- Amadeus metni yapıştırın, `AI ile bilgileri ayıkla` düğmesini tıklayın.
- Sol tarafta çıkan alanları **mutlaka kontrol edin** ve eksikleri ekleyin.
- `Teklifi güncelle` düğmesini tıklayın.
- PDF için `PDF olarak kaydet` ve açılan yazdır penceresinde "Save as PDF / PDF olarak kaydet" seçin. Bu yaklaşım ayrıca bir PDF kütüphanesi gerektirmez.

## Güvenlik / sınırlamalar
- Yolcu isimleri dahil yapıştırılan tüm metin OpenAI API'ye gönderilir. Kişisel verileri mümkünse maskeleyin, şirket politikanıza uyun.
- Bu sürümde kullanıcı girişi yoktur. Kamuya açık URL'yi bilen kişiler ücretli API isteği gönderebilir. Üretim kullanımı öncesinde erişim koruması ve oran sınırı ekleyin. API kullanım limitleri belirleyin.
- Uçuş bilgileri, fiyat, bagaj ve kurallar kaynakla karşılaştırılmalı; eksik veriler *Belirtilmedi — teyit ediniz* şeklinde gösterilir.
- E-posta metni otomatik gönderilmez; sadece panoya kopyalanır.
- Ücretsiz Vercel Hobby planının ticari kullanım sınırlarını ayrıca değerlendirin.

## Hizmet bedeli (yeni)

Teklif düzenleme bölümündeki ‘Yön başına hizmet bedeli ekle’ kutusunu isteğe bağlı işaretleyin; yön başına tutarı ve yön sayısını (1 veya 2) seçin. Gidiş-dönüş için 2 yön seçin. Bedel uçuş fiyatına eklenir; PDF ve e-posta çıktısında ayrı gösterilir. Uçuş bedeli ve hizmet bedeli aynı para biriminde olmalıdır. API dosyasında değişiklik yoktur; mevcut projede yalnızca index.html değiştirilebilir.
