# LISKOV SUBSITUTE PRINCIPLE

Liskov Değiştirme İlkesi (LSP), kalıtım hiyerarşileri için geçerlidir ve sınıfların, istemcinin değişikliği bilmeden istemci bağımlılıklarının alt sınıflarla değiştirilebilmesi için tasarlanması gerektiğini belirtir.

Bu nedenle, tüm alt sınıflar, temel sınıflarıyla aynı şekilde çalışmalıdır. Alt sınıfın özel işlevselliği farklı olabilir ancak temel sınıfın beklenen davranışına uygun olmalıdır. Gerçek bir davranışsal alt tip olmak için, alt sınıf yalnızca temel sınıfın yöntemlerini ve özelliklerini uygulamakla kalmamalı, aynı zamanda belirtilen davranışına da uymalıdır.

**LSP'nin altında yatan ana fikri:** alt sınıflardan oluşan nesnelerin üst sınıfın nesneleri ile yer değiştirdikleri zaman, aynı davranışı sergilemesini beklemektir.

*Peki,alt seviye nesnelerin bağlı oldukları üst seviye nesneler ile aynı şekilde davranabilmesi ne demek*?
Bu prensipe uygun kod geliştirebilmek için; üst seviye nesnelerin aldığı girdiler ile, aynı formatta çıktı verebilen ve aynı davranışlara sahip alt nesnelerin olması demektir.

Genel olarak, üst türün bir alt türü, üst türün istemcisinin beklemediği bir şey yaparsa, bu LSP'yi ihlal eder. Türetilmiş bir sınıfın, üst sınıfın atmadığı bir istisna oluşturduğunu veya türetilmiş bir sınıfın bazı beklenmedik yan etkileri olup olmadığını hayal edin. Temel olarak, türetilmiş sınıflar asla temel sınıflarından daha azını yapmamalıdır.

LSP'yi ihlal eden tipik bir örnek, bir Rectangle sınıfından türetilen bir Square sınıfıdır. Square sınıfı her zaman genişliğin yüksekliğe eşit olduğunu varsayar. Bir Square nesnesi, bir Rectangle'ın beklendiği bir bağlamda kullanılırsa, bir Square'in boyutları bağımsız olarak değiştirilemediğinden (veya daha doğrusu değiştirilmemesi gerektiğinden) beklenmeyen davranışlar ortaya çıkabilir.


LSP prensibi **Open Closed** prensibinin özel bir türüdür diyebiliriz.O halde Open Closed prensibi'nden biraz bahsedelim.

### Open Closed prensibi 
Birçok program müşteri gereksinimleri doğrultusunda ilk sürümden sonra değişikliğe uğrar.Müşteri programı kullanmaya başladıkça ihtiyaçları doğrultusunda programın değiştirilmesini talep edebilir ve bu oldukça doğal bir süreçtir.
Gelecek olan isteklerin sistemimize rahatlıkla entegre olabilmesi veya kolaylıkla genişletilebilmesi için (günümüzde zaman artık çok değerli bir kıstas olduğu için) uygulamamızı gelişime açık, değişime kapalı bir şekilde geliştirmeliyiz. Değişime karşı çıkılmasının temel nedeni yapılan bu değişikliğin ilgili metodu kullanan yerlerde bozukluğa neden olabilme ihtimalidir (ki genellikle olurlar, sonradan fark edilen bozukluklar çok daha fazla can sıkar).Bunun yanında çokça vakit kaybına neden olur.

Alt sınıflarda meydana gelen davranış değişiklikleri, bu metotların hatalı çalışmasına sebep verebilir. Özellikte bu metotlarda instanceof gibi nesnelerin tipleri arasında kıyaslama yapılmak zorunda kalındığı zaman, LSP prensibi çiğnenmiş olur ki, bu alt sınıfların varlığından haberdar olunduğu anlamına gelir. Yani ileride kod üzerinde değişiklik yapılmak istendiğinde yaşanacak olan karmaşıklığın önüne geçmek ve zaman kaybından kaçınmak için LSP prensibi uygulanmalıdır.


LSP ile geleceğe dönük uygulamalar için kod geliştirilir.Yani ileride yaşanacak değişiklikliklerde problemlerin önüne geçebilmek için kodun geliştilmesi sırasında bu yöntem kullanılır.

**Konuyu daha iyi kavramak için en basit şekilde örnekle anlatmaya çalışalım.**

LSP'yi ihlal eden tipik bir örnek, bir *Rectangle* sınıfından türetilen bir Square sınıfıdır. *Square* sınıfı her zaman genişliğin yüksekliğe eşit olduğunu varsayar. Bir *Square* nesnesi, bir *Rectangle*'ın beklendiği bir bağlamda kullanılırsa, bir *Square*'in boyutları bağımsız olarak değiştirilemediğinden (veya daha doğrusu değiştirilmemesi gerektiğinden) beklenmeyen davranışlar ortaya çıkabilir.

Bu sorun kolayca çözülemez. Square sınıfındaki setter yöntemleri, "Square" değişmezini koruyacak (yani boyutları eşit tutacak) şekilde değiştirebilirsek, bu yöntemler Rectangle setter'lar için son koşulları zayıflatır (ihlal eder) , boyutların bağımsız olarak değiştirilebileceğini belirtir.

                            public class Rectangle {
                            private double height;
                            private double width;

                            public double area();

                            public void setHeight(double height);
                            public void setWidth(double width);
                            }*

Yukarıdaki kod parçası LSP'yi ihmal etmektedir.

                            public class Square extends Rectangle {  
                            public void setHeight(double height) {
                                super.setHeight(height);
                                super.setWidth(height);
                            }

                            public void setWidth(double width) {
                                setHeight(width);
                            }

Çünkü kare için  tek bir uzunluk girilmesi yetecekken Rectangle'dan extend aldığımız için iki adet uzunluk bilgisi girilmesi beklenmektedir.
Matematiksel olarak karenin dikdörtgenden türediğini varsayabiliriz. Ama davranışsal olarak Kare Dikdörtgenin yerine geçmez, bu hiyerarşi LSP'yi ihlal eder.


LSP,yazılım gelişticiler tarafından baçvurulan bir yöntemdir.Müşterinin isteği,kısa sürede ve hata oranı en düşük olacak şekilde yerine getirilir.Böylece müşteri-geliştirici arasındaki ilişkinin de sağlıklı bir şekilde devam etmesi sağlanır.


>**Not:** Kodunuzun Liskov Değiştirme İlkesine uyduğundan emin olmak için kendi kontrollerinizi uygulamanız gerekir. En iyi durumda, bunu kod incelemeleri ve test senaryoları aracılığıyla yaparsınız. Test durumlarınızda, hiçbirinin hataya neden olmadığından veya performansını önemli ölçüde değiştirmediğinden emin olmak için uygulamanızın belirli bir bölümünü tüm alt sınıfların nesneleri ile çalıştırabilirsiniz. Bir kod incelemesi sırasında benzer kontrolleri yapmayı deneyebilirsiniz. Ancak daha da önemlisi, gerekli tüm test senaryolarını oluşturup uyguladığınızı kontrol etmenizdir.

>**Not:** Ödevi hazırlarken kullandığım kaynaklara aşağıdaki linklerden ulaşabilirsiniz.
+ (https://www.alpharithms.com/liskov-substitution-principle-lsp-solid-114908/)
+ (https://medium.com/@radheshyamsingh_83359/liskov-substitution-principle-solid-design-f9d48500c260)
+ (https://stackify.com/solid-design-liskov-substitution-principle/)
+ (https://kenanatmaca.com/liskov-substitution-principle-nedir/)
+ (https://www.jrebel.com/blog/solid-principles-in-java)
+ (https://reflectoring.io/lsp-explained/)
+ (https://www.gokhan-gokalp.com/liskov-substitution-principle-lsp-liskovun-yerine-gecme-prensibi/)  