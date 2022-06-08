# DECOMPOSITION

Decomposition, büyük karmaşık bir sistemi, böl ve yönet ilkelerine göre daha az karmaşıklığa sahip daha küçük bileşenlerden oluşan bir hiyerarşiye bölmek olarak tanımlayabiliriz. Sistemin her ana bileşenine ise  alt sistem denir.

Bu kavramı 2 başlık altında inceleyebiliriz;

### Yapısal Decomposition
"Böl ve Yönet", ilkelerine dayanarak sorunlarını çözmek için yaygın olarak kullanılan bir tekniktir. Özellikle modelleme yaparken  yararlıdır. Bir nesne yapısal olarak mantıksal parçalara ayrıştırılabiliyorsa, o zaman bu parçaların her birini oluşturmak biraz daha basit bir tasarım problemi haline gelir ve k od modüler hale geldikçe nesnelerin değiştirilmesi çok daha basit bir işleme dönüşür.

### Fonsiyonel Decomposition
Fonksiyon decomposition için hedef, hesaplama tarafından manipüle edilen verilerden ziyade gerçekleştirilecek hesaplama üzerindedir. Yapılması gereken işe göre problem ayrıştırılır. Her görev daha sonra genel çalışmanın bir bölümünü gerçekleştirir ve bu bölümlerin bütünü genel çalışmayı oluşturur.

İş dünyasında, büyük ve karmaşık süreçlerin anlaşılmasını ve yönetilmesini kolaylaştırmak için fonksiyonel decomposition kullanılır. Fonksiyonel decomposition, sorunların çözülmesine yardımcı olur ve iş operasyonlarının, bilgisayar programlamanın, makine öğreniminin ve diğer çeşitli alanların geliştirilmesine yardımcı olur.

**Decomposition neden önemlidir?**
Aynı anda birçok farklı aşamayla uğraşmak, bir problemi birkaç küçük probleme bölüp her birini teker teker çözmekten çok daha zordur. Problemi daha küçük parçalara bölmek, her küçük problemin daha detaylı olarak incelenebileceği anlamına gelir. Benzer şekilde, karmaşık bir sistemin nasıl çalıştığını anlamaya çalışmak, ayrıştırmayı kullanarak daha kolaydır. Örneğin, bir bisikletin nasıl çalıştığını anlamak, tüm bisiklet daha küçük parçalara ayrılırsa ve her parça nasıl çalıştığını daha ayrıntılı görmek için incelenirse daha kolaydır.Bu sebeple karmaşık bir yapıda,yapıyı küçük parçalara bölerek çözümlemek problemin çözüm aşamasını basitleştirir ve buna binaen vakit kazancı sağlar.

Decomposition yöntemi günlük hayatımızdaki problemlerden profesyonel iş hayatımızda olan problemlere kadar her alanda kullanılabilir.Bu bazen evde yapılacak günlük işlerin sırasını belirleme,görev paylaşımı yapma olabilir ken bazen de  bir şirket kurmak için yapılması gerekli olan işlemlerin belirlenerek bir düzen içinde halledilmesi olabilir.Tabii biz şu an için programlama kısmıyla ilgileniyoruz.
 
Bilgisayar programlama problemlerini çözerken, ne yapacağımız,hangi yöntemleri kullanacağımız ve hangi sırayla yapacağımız konusunda seçimler yapmamız gerekir. Bazen sorun o kadar büyük veya karmaşıktır ki nereden başlayacağımızı bilemeyiz ve durum içinden çıkılamayacak hale gelebilir.Böyle durumlarda decomposition yöntemine başvurulur ve problem olabiliğince basite indirgenir.

Bu yöntemin sürecini aşağıdaki gibi özetleyebiliriz:
### 1.Genel Fonksiyonu Belirleme
Yazılım tasarlamaya başlamadan önce, yazılımın, sistemini, ,bileşenin hangi görevi yapması gerektiği konusunda çok net olunmalıdır.Görev belirlenikten , yazılımınızın gerçekleştirmesi gereken en genel görev nbelirlenerek bunun için decomposition diyagramı tasarlamanmaya başlanmalıdır. 
Fonksiyonel  decomposition şemasında, yazılımınızın en genel görevi en üstte olmalı ve görevin nasıl yapılması gerektiği değil, yalnızca görevin ne olduğunun kısa bir açıklaması olmalıdır.

### 2.Alt Fonksiyonları Belirleme
En genel işleve ait  alt işlevler kümesini belirlemek için, en genel işlevden hemen önce yapmanız gereken görevlerin veya işlevlerin neler olduğunun belirlenmesi gerekir. Bu alt fonksiyonların listesi, fonksiyonel decomposition diyagramında en genel fonksiyonun hemen altına yerleştirilmelidir. Satırları kullanarak alt işlevleri genel işleve bağlayın.Bu kısımda fonksiyonaun ne yapması gerektiğinin yanında nasıl yapılacağının da açıklanması gerekir.

### 3.Sonraki Seviye Alt Fonksiyonunu Belirleme
2.adımda belirtlilen alt fonksiiyonlarının her birinin iyileştirilmesi gerekir.Ve diyagramdaki fonksiyonlar daha fazla parçalanmayacak hale gelene kadar fonksiyonlar iyileştirilmeye devam edilmelidir.

### 4.Fonksiyon Decomposition Diyagramı Kontrolü 
Diyagram tamamlandığında diyagrama dahil edilebilecek herhangi bir fonksiyon kalıp kalmadığının kontrolünün yapılması gerekir.

Bu yöntemi basit bir örnekle açıklarsak;
Elinizde alfabetik olarak sıralamak istediğiniz bir sürü kitap var:
+ Kitapları raftan indirin.
+ Kitapları ilk olarak İlk harflerine göre gruplandırın.
+ ”A” harfinden başlayarak grupladığınız kitapları alfabetik sıraya göre düzenleyin.
+ Sıraladığınız kitapları alfabetik sıraya uygun olarak raflara tekrar yerleştirin.

Decomposition yöntemi herkes tarafından kullanılabilecek bir yöntemdir.Ancak ağırlıklı olarak yazılım geliştiriciler ve iş analistleri tarafından etkin olarak kullanılır.

Bir problemi ayrıştırmanın avantajları şunlardır: 
 + Farklı modüller üzerinde farklı kişiler veya ekipler tarafından aynı anda çalışılabilir, bu da üretkenliği artırır
 + Küçük bir modülü düşünmek ve çözmek, büyük bir sorundan daha kolaydır
 + Modülleri birbirine paralel olarak işlemek mümkün olabilir, bu da sorunun bir bütün olarak daha hızlı işlenmesini sağlar. 
Ancak, bozulma riskleri vardır:
 + Sorunu başarılı bir şekilde ayrıştırmak için sorunu çok iyi anlamalısınız 
 + Bir sorunun parçaları üzerinde paralel olarak çalışılırsa, sonunda bunları tek bir çözümde yeniden birleştirmek zor veya imkansız olabilir.

>**Not:** Ödevi hazırlarken kullandığım kaynaklara aşağıdaki linklerden ulaşabilirsiniz.

+ https://www.asc.ohio-state.edu/lewis.239/Class/decomposition.html#:~:text="Divide%20and%20Conquer"%20is%20a,a%20somewhat%20simpler%20design%20problem.

+ (https://www.bbc.co.uk/bitesize/guides/zqqfyrd/revision/1)

+ (http://www.bawiki.com/wiki/Decomposition.html)

+ (https://binaryterms.com/functional-decomposition.html)

+ (https://www.investopedia.com/terms/f/functional-decomposition.asp#:~:text=Functional%20decomposition%20is%20especially%20important,and%20simplify%20the%20programming%20process.)

+ (https://www.ealingindependentcollege.com/userfiles/files/GCSE%20specs/Decomposition%20and%20Abstraction_docx.pdf) 