# 🧊 YOLO + TripoSR — Görselden 3D Modele

Bu proje, tek bir fotoğraf üzerinden uçtan uca bir 3D model üretim hattı sunar. Sisteme verilen bir görsel önce YOLO nesne tespit modeli tarafından analiz edilir; görseldeki hedef nesne otomatik olarak tanınır, konumu belirlenir ve arka plandaki gereksiz alanlardan arındırılarak kenar payı bırakılıp kırpılır. Elde edilen bu kırpılmış görüntü ardından TripoSR modeline iletilir; bu model, tek bir 2 boyutlu görüntüden yola çıkarak nesnenin geometrisini ve yüzey detaylarını yeniden inşa eder ve tekstürlü, döndürülüp incelenebilir bir 3 boyutlu mesh (.glb formatında) üretir. Süreç, kullanıcının donanımında ağır bir hesaplama gerektirmeden çalışacak şekilde tasarlanmıştır: nesne tespiti yerel makinede gerçekleştirilirken, hesaplama açısından yoğun olan 3D yeniden yapılandırma adımı Hugging Face üzerinde barındırılan TripoSR servisine devredilir. Böylece kullanıcı, karmaşık bir kurulum veya güçlü bir grafik kartına ihtiyaç duymadan, sıradan bir fotoğrafı birkaç dakika içinde işlenebilir bir 3D varlığa dönüştürebilir.

🔄 Nasıl Çalışır?

<img width="439" height="76" alt="Ekran Resmi 2026-09-06 00 58 40" src="https://github.com/user-attachments/assets/7e9bf370-803f-438b-b8d7-2d1050abe33a" />




<img width="448" height="320" alt="Ekran Resmi 2026-09-06 00 59 17" src="https://github.com/user-attachments/assets/381dea6a-00f3-47c5-8fa1-08df054c54a5" />


💡 Neden uzak TripoSR? Yerel kurulum torchmcubes / xatlas gibi C++ derleyici gerektiren paketlere ihtiyaç duyar ve sık sık kurulum hatası verir. Bu proje, ağır işi Hugging Face'in barındırdığı Space'e devrederek yerelde hiçbir derleme gerektirmez.

🚀 Hızlı Başlangıç
git clone https://github.com/<kullanici-adin>/<repo-adin>.git
cd <repo-adin>
pip install jupyter
jupyter notebook yolo_to_3d.ipynb

1.IMAGE_PATH değişkenini kendi görselinle değiştir
2.Hücreleri sırayla çalıştır
3.Son hücrede 3D modelini interaktif olarak incele 🎉

🧰 Kullanılan Teknolojiler
Ultralytics YOLO · TripoSR · Gradio Client · Trimesh · Plotly

<div align="left">

MIT Lisansı ile paylaşılmıştır.

</div>
