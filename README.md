# Grover-s-algorithm
Grover's Algoritması Simülasyonu
Bu proje, Qiskit kütüphanesini kullanarak ünlü kuantum arama algoritması olan Grover's Algoritması'nın bir uygulamasını ve simülasyonunu içeren bir Python Jupyter Notebook'udur (veya Google Colab Notebook'u). Belirli bir "gizli dize" (secret string) ile işaretlenmiş bir öğeyi arayarak kuantum hesaplamanın gücünü göstermektedir.

# Özellikler
Grover's Algoritması Uygulaması: Kuantum arama problemini çözmek için Grover's algoritmasının temel adımlarını (süperpozisyon, oracle, diffuser) uygular.

Özel Oracle Oluşturma: Belirli bir gizli dizeyi işaretlemek için dinamik olarak bir kuantum oracle devresi oluşturur.

Diffuser Operatörü: Arama uzayındaki genlikleri yükseltmek için Grover's diffuser operatörünü inşa eder.

Qiskit Entegrasyonu: Kuantum devrelerini oluşturmak, manipüle etmek ve simüle etmek için IBM'in açık kaynaklı Qiskit kütüphanesini kullanır.

Kuantum Devre Simülasyonu: Qiskit Aer simülatörünü kullanarak devreyi çalıştırır ve ölçüm sonuçlarını elde eder.

Sonuç Görselleştirme: Matplotlib ile ölçüm sonuçlarının histogramını çizerek en olası arama sonucunu gösterir.

# Kullanılan Teknolojiler
Python: Projenin ana programlama dili.

Qiskit: Kuantum devreleri oluşturmak ve yönetmek için IBM'in açık kaynaklı kütüphanesi.

Qiskit Aer: Kuantum devrelerini simüle etmek için Qiskit'in yüksek performanslı simülatör eklentisi.

Matplotlib: Python'da grafikler ve görselleştirmeler oluşturmak için kullanılır.

NumPy: Sayısal işlemler ve dizi manipülasyonları için temel Python kütüphanesi.

pylatexenc: Kuantum devre çizimlerinde LaTeX notasyonunu desteklemek için kullanılır.

Google Colab (veya Jupyter Notebook): Kodun çalıştırıldığı ve sunulduğu ortam.

# Kod Açıklaması
Notebook'un içinde, her bir kod bloğunun ne anlama geldiğini ve Grover's algoritmasının nasıl çalıştığını açıklayan detaylı Markdown hücreleri bulunmaktadır.

Bağımlılıkların Yüklenmesi: İlk hücreler qiskit, pylatexenc ve qiskit-aer gibi gerekli kütüphaneleri yükler.

Oracle Fonksiyonu (construct_oracle):

Verilen secret_string'e (örneğin '0110') göre bir kuantum oracle devresi oluşturur.

Bu oracle, gizli dizeye karşılık gelen durumu negatif bir faz ile işaretler.

MCXGate (Multi-Controlled X Gate) kullanılarak çoklu kontrollü Toffoli kapısı uygulanır.

Diffuser Fonksiyonu (diffuser):

Grover's algoritmasının amplifikasyon adımını gerçekleştiren diffuser operatörünü oluşturur.

Hadamard kapıları ve çoklu kontrollü Z kapısı (yine MCXGate ile simüle edilir) kombinasyonunu kullanır.

Ana Grover Devresi:

n qubit ile bir ana devre (grover) oluşturulur (4 ana qubit + 1 yardımcı qubit).

Tüm ana qubit'lere Hadamard kapıları uygulanarak süperpozisyon oluşturulur.

Yardımcı qubit, fazı almak için ayarlanır (X ve H kapıları ile).

Oracle ve diffuser, belirli sayıda tur (bu örnekte 2 tur) uygulanır.

Ana qubit'ler ölçülür.

Simülasyon ve Sonuçlar:

Aer.get_backend('qasm_simulator') kullanılarak bir kuantum simülatörü başlatılır.

Devre simülatörün desteklediği temel kapılara dönüştürülür (transpile).

Devre belirli sayıda atış (shots=1024) ile çalıştırılır ve ölçüm sonuçları (counts) alınır.

Sonuçlar yazdırılır ve bir histogram ile görselleştirilir, bu da gizli dizenin diğerlerinden daha yüksek bir olasılıkla bulunduğunu gösterir.

# Gelecekteki Geliştirmeler
Farklı secret_string uzunlukları için algoritmanın performansını test etme.

Grover's algoritmasının tur sayısını otomatik olarak hesaplama.

Daha karmaşık arama problemleri için oracle'lar oluşturma.

Gerçek IBM kuantum donanımlarında bu devreyi çalıştırma.

Algoritmanın matematiksel temellerini açıklayan ek görselleştirmeler.
