📊 Stokastik Süreçler: Saatlik Enerji Tüketimi Üzerine Markov Zinciri Analizi

Bu proje, zaman serisi formundaki sürekli bir verinin (saatlik enerji tüketimi) kesikli durumlara (states) ayrılarak Markov Zinciri (Markov Chain) modeli ile analiz edilmesini içermektedir. Proje, "İST 374 Olasılıksal Süreçler" dersi kapsamında akademik kurallara uygun olarak R dilinde geliştirilmiştir.

📝 Proje HakkındaEnerji tüketimi gibi doğası gereği sürekli değişen sistemlerin gelecekteki davranışlarını tahmin etmek, kaynak planlaması açısından büyük önem taşır. Bu çalışmada, enerji tüketim miktarları istatistiksel çeyreklik (quantile) dilimlere göre "Düşük", "Normal" ve "Yüksek" olmak üzere 3 farklı duruma ayrılmıştır.

Çalışma kapsamında aşağıdaki stokastik analizler gerçekleştirilmiştir:

Sistemin Bir-Adım Geçiş Matrisinin (P) hesaplanması ve görselleştirilmesi.

Orta ve uzun vadeli tahminler için n-Adım Geçiş Matrislerinin ($P^3$, $P^{100}$) oluşturulması.

Markov zinciri diyagramlarının oluşturulması.

Sistemin yapısal analizi (İndirgenebilirlik, Aperiyodiklik ve Yutucu Durum kontrolleri).

Uzun Dönem Denge Dağılımının (Stationary Distribution) bulunması ve yorumlanması.

Ek olarak, Yutucu (Absorbing) Markov Zincirleri üzerine teorik bir senaryo ile Beklenen Yutulma Süresi (N) ve Yutulma Olasılıklarının (F) hesaplanması.

📂 Veri Seti

Çalışmada kullanılan veri seti Kaggle platformundan alınmıştır:

Veri Seti: Hourly Energy Consumption (PJM Interconnection)

Özellikler: Veri seti, farklı eyaletlere ait geçmişe dönük saatlik Megawatt (MW) enerji tüketim kayıtlarını içermektedir. Çalışmada veri ön işleme (sıralama, NA temizliği) yapıldıktan sonra Markov süreçlerine entegre edilmiştir.

🛠️ Kullanılan Teknolojiler ve KütüphanelerProje R programlama dili ile yazılmış ve R Markdown formatında raporlanmıştır.

markovchain: Markov zincirlerinin kurulması ve analizi

diagram: Geçiş diyagramlarının profesyonel çizimi

expm: Matrislerin n. kuvvetlerinin (üssü) alınması

dplyr: Veri manipülasyonu ve ön işleme

ggplot2 & reshape2: Durum-zaman grafikleri ve ısı haritası görselleştirmeleri

🚀 Kurulum ve Çalıştırma

Bu projeyi kendi bilgisayarınızda çalıştırmak için aşağıdaki adımları izleyebilirsiniz:

Depoyu bilgisayarınıza klonlayın:Bashgit clone https://github.com/KULLANICI_ADINIZ/markov-chain-energy-analysis.git

RStudio'yu açın ve Odev_Raporu.Rmd dosyasını çalıştırın.

Eksik kütüphaneleri yüklemek için R konsoluna aşağıdaki kodu yapıştırın:

Rinstall.packages(c("markovchain", "diagram", "dplyr", "ggplot2", "reshape2", "expm"))

Knit butonuna basarak HTML, PDF veya Word formatında proje raporunu elde edebilirsiniz.

📈 Temel Bulgular

Sistemin Ataleti: Enerji tüketiminin kendi mevcut durumunu koruma eğilimi (ana köşegen olasılıkları) oldukça yüksek çıkmıştır (Ort. ~%85).

Kademeli Değişim: Sistem "Düşük" seviyeden "Yüksek" seviyeye aniden geçiş yapmamakta; değişimler "Normal" durum üzerinden kademeli olarak gerçekleşmektedir.

Denge (Limit) Dağılımı: Analiz edilen sistem indirgenemez (irreducible) yapıda olduğundan, uzun vadede (örn. $P^{100}$) sistemin belirli bir kararlı duruma ulaştığı ve başlangıç değerinden bağımsızlaştığı (Teorem 2.1) ispatlanmıştır.

📌 Kaynakça

PJM Hourly Energy Consumption Data, Kaggle.

İST 374 Olasılıksal Süreçler Ders Notları (Prof. Dr. Gamze Kadılar)

Spedicato G. A., (2017). Discrete Time Markov Chains with R. The R Journal.

