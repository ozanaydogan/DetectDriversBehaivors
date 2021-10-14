# DetectDriversBehaivors
Detect Drivers Bad Behavior Using YOLOv3

Projenin amacı, herhangi bir ulaşım aracını kullanan sürücünün, sürüş esnasında kazaya sebep olabilecek 3 davranışı(Sürüş esnasında telefonla konuşması, 2 elini aynı anda direksiyondan çekmesi, sigara içmesi) tespit etmektir.

# Kendi projenizi inşa etmek için ihtiyacınız olan teknolojiler
- ## CUDA veya Google COLAB
###
CUDA, GPU için NVIDIA'nın sunduğu 
C programlama dili üzerinde eklenti olarak 
kullanıma sunulan bir mimari ve teknolojidir. 
PathScale tabanlı bir C derleyicisi ve C ile 
yazılmış algoritmaların GPU üzerinde 
çalışmasını sağlayan geliştirme araçları 
kümesidir. Derin sinir ağlarıyla model eğitimi sağlanırken GPU'yu kullanmak CPU'ya oranla daha avantajlıdır. GPU'yu aktif etmek için bu CUDA teknolojisi kullanılır.

CUDA teknolojisinin çalışma mantığını anlamak için buraya bakabilirsiniz. [CUDA tutorial](https://www.nvidia.com/content/cudazone/download/Getting_Started_w_CUDA_Training_NVISION08.pdf)

Google Colab eğitim dosyasının linki için [Colab Link]

-  ## YOLOV3'de eğitim
YoloV3'e erişmek için [Link](https://github.com/pjreddie/darknet)

eğitim Darknet Framework'ünde ubuntu ortamında gerçekleştirilmiştir

YoloV3 kullanarak eğitim için YOLO bizden 4 adet dosya istiyor

Train.txt > Bizden Eğitim setindeki eğitim resimlerinin dosya yollarını belirten her resmin satır satır yolunun verildiği txt dosyasıdır.

Test.txt > Bizden Eğitim setindeki test resimlerinin dosya yollarını belirten her resmin satır satır yolunun verildiği txt dosyasıdır.

Classes.names > Tespit edilecek nesnelerin isimlerinin satır satır yazıldığı dosya türü

Custom.data > Formatı aşağıda belirttildiği gibidir:

classes = Class sayımız (Bizim class sayımız 5 idi)

train = Train.txt dosyasının dosya yolunu veriyoruz

valid = Test.txt dosyasının dosya yolunu veriyoruz

names = Classes.names dosyasının dosya yolunu veriyoruz

backup = Eğitimde weights dosyalarını nereye kaydetmek istiyorsak  dosya yolunu veriyoruz

-  ## Kendi datasetinizi oluşturun veya dataset edinin
[Kaggle](https://www.kaggle.com/) gibi sitelerden dataset edinebilirsiniz. Biz projemizde kendi datasetimizi oluşturup kullandık. Datasetimiz 1500 farklı görüntüden oluşmaktadır. Bu görüntülerin herbirinde, tespit etmek istediğimiz objeler bulunmaktadır. Datasetiniz için oluşturmak istediğiniz görüntüleri etiketlemek için [LabelImg](https://github.com/tzutalin/labelImg)'den yardım alabilirsiniz.

-  ## OpenCV
Web kamerasıyla görüntü işleme ve görüntü yakalamak için kullanıldı

-  ## PyGame
Sürücü, sürüş anında kazaya sebep olacak yanlış bir davranışta bulunduğu anda tespit edilir ve bu durumda oluşturulan ses dosyası çalar.

-  ## Kamera

# Projenin Yapım aşamaları

- ### Sigara, El, Yüz, Telefon, Direksiyon objelerinin bulunduğu görüntülerle bir dataset oluşturuldu
- ### Datasetimizi YOLOv3-VOC modeliyle eğittik
- ### CUDA ile GPU üzerinde 12 saat süren eğitim yaptık
- ### Sürücünün sürüş anında kazaya sebep olacak hatalı davranışlarının tespit edilmesi için Python dilinde bir scrpit dosyası yazıldı
Bu aşamada yardım almak için bu linke göz atabilirsiniz. 
[link](https://github.com/pjreddie/darknet/issues/289)

#### YOLOv3'ün çalışma mantığı, CNN'de YOLO algoritmasının kullanıldığı yerler, Darknet-53 hakkında daha detaylı bilgiye sahip olabilmek için oluşturduğumuz Sunum dosyasına gözatınız.

projenin kaynak kodlarına erişmek istiyorsanız ve konu hakkında soru sormak isterseniz ozanaydogan1@hotmail.com veya msait.celik@outlook.com mail adreslerinden ulaşabilirsiniz.
