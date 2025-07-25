# Not: Bu README dosyasının Türkçe versiyonunu aşağıda bulabilirsiniz.
# Grover's Algorithm Simulation
This project is a Python Jupyter Notebook (or Google Colab Notebook) that aims to implement and visualize Grover's Algorithm, a famous quantum search algorithm, using the Qiskit library. It demonstrates the power of quantum computing by searching for an item marked with a specific "secret string".

# Features
Grover's Algorithm Implementation: Implements the core steps of Grover's algorithm (superposition, oracle, diffuser) to solve the quantum search problem.

Custom Oracle Construction: Dynamically builds a quantum oracle circuit to mark a specific secret string.

Diffuser Operator: Constructs the Grover's diffuser operator to amplify amplitudes in the search space.

Qiskit Integration: Utilizes IBM's open-source Qiskit library to create, manipulate, and simulate quantum circuits.

Quantum Circuit Simulation: Runs the circuit using the Qiskit Aer simulator and obtains measurement results.

Result Visualization: Plots a histogram of the measurement results using Matplotlib, showing the most probable search outcome.

# Technologies Used
Python: The main programming language for the project.

Qiskit: IBM's open-source library for quantum computing.

Qiskit Aer: Qiskit's high-performance simulator extension for simulating quantum circuits.

Matplotlib: Used for creating plots and visualizations in Python.

NumPy: Essential Python library for numerical operations and array manipulation.

pylatexenc: Used to support LaTeX notation in quantum circuit drawings.

Google Colab (or Jupyter Notebook): The environment where the code is executed and presented.

# Code Explanation
Inside the notebook, there are detailed Markdown cells explaining what each code block does and how Grover's algorithm works.

Dependency Installation: The initial cells install necessary libraries like qiskit, pylatexenc, and qiskit-aer.

Oracle Function (construct_oracle):

Constructs a quantum oracle circuit based on the given secret_string (e.g., '0110').

This oracle marks the state corresponding to the secret string with a negative phase.

It uses MCXGate (Multi-Controlled X Gate) to apply a multi-controlled Toffoli gate.

Diffuser Function (diffuser):

Creates the diffuser operator, which performs the amplification step of Grover's algorithm.

It uses a combination of Hadamard gates and a multi-controlled Z gate (simulated with MCXGate).

# Main Grover Circuit:

A main circuit (grover) is created with n qubits (4 main qubits + 1 auxiliary qubit).

Hadamard gates are applied to all main qubits to create a superposition.

The auxiliary qubit is set up to receive the phase (with X and H gates).

The oracle and diffuser are applied for a specific number of iterations (2 iterations in this example).

The main qubits are measured.

# Simulation and Results:

A quantum simulator is initialized using Aer.get_backend('qasm_simulator').

The circuit is transpiled to the basis gates supported by the simulator (transpile).

The circuit is run with a specified number of shots (shots=1024), and measurement results (counts) are obtained.

The results are printed and visualized with a histogram, showing that the secret string is found with a higher probability than others.
Future Enhancements
Testing the algorithm's performance for different secret_string lengths.

Automatically calculating the optimal number of iterations for Grover's algorithm.

Creating oracles for more complex search problems.

Running this circuit on real IBM quantum hardware.

Adding additional visualizations to explain the mathematical foundations of the algorithm.

# Grover's Algoritması Simülasyonu (Türkçe)

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
