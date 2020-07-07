# III-hafta-odevi

                                                        TASK vs THREAD DİFFERENCES in C#


İşleri birden çok iş parçacığında yürüttüğümüzde, iş parçacıklarının birden çok işlemci arasında ayrıldığı garanti edilmez.
Task, paralelleştirilebilir bir iş birimini yönetmek için hafif bir nesnedir. Paralel olarak bir şey yürütmek istediğinizde kullanılabilir. Paralel, hesaplama hızını en üst düzeye çıkarmak için işin birden fazla işlemciye dağıtıldığı anlamına gelir. Çok çekirdekli işlemcileri kullanmak için görevler ayarlanır.
Task, iş parçacığı üzerinden aşağıdaki güçlü özellikleri sağlar.
Sistemin birden fazla görevi varsa, CLR iş parçacığı havuzunu dahili olarak kullanır ve bu nedenle iş parçacığının İş parçacığı kullanılarak ayrılmış bir iş parçacığı oluşturma ile ilişkili olması gerekmez. Ayrıca birden çok iş parçacığı arasındaki bağlam değiştirme süresini de azaltın.
Task  bir sonuç döndürebilir. Sonucu iş parçacığından döndürmek için doğrudan bir mekanizma yoktur.
Sinyal oluşturma yapısı olmadan bir dizi görevi bekleyin.
Birbiri ardına yürütmek için görevleri bir araya getirebiliriz.
Bir görev başka bir görevden başlatıldığında bir üst / alt ilişkisi oluşturun.
Alt görev istisnası üst göreve yayılabilir.
İptal belirteçleri kullanılarak görev desteği iptali.
'Eşzamansız' ve 'bekliyor' anahtar kelimeleri kullanarak eşzamansız uygulama kolaydır.

                                                     TASK vs ASYNC AWAİT
                                                     
NET'te yeni olan veya eski bir sürümden yeni platforma ve araçlara geçen birçok geliştiriciyle konuşuyorum. Gibi her zaman Görevler vs Threads ve async vs paralel doğasını tanımlamak için yeni yollar düşünmeye çalışıyorum. Modern .NET geliştirme, async / await modelinde bulunur ve async / await, Görev modeline dayanır. Bu nedenle, bu kavramları anlamak, .NET'te uzun vadeli başarı geliştirmenin anahtarıdır.
DoWorkAsync () yöntemi yalnızca bir döngü çalıştırır. Döngünün her seferinde, bir tür eşzamansız görev yapacak ve daha sonra bir süre meşgul “iş” yapacak, ardından ekranda o “işi” yapmak için harcadığı zamanı temsil eden bir dikdörtgen çizecektir. (Bu, bir web hizmeti çağrısı yapmaya ve ardından hizmetten döndürülen veriler üzerinde bazı yerel işlemler yapmaya benzer.) Bu şekilde (a) işin ne zaman yapıldığını ve (b) işin çakışıp çakışmadığını kolayca görebiliriz diğer görevin çalışmasıyla. Varsa, birden fazla iş parçacığında çalışıyoruz. İlgilendiğimiz iş bizim kodumuzdur (örn. Yerel veri işleme) - beklenen şey değil (async web hizmeti), böylece uygulamadaki her çubuk yerel işlemi temsil edecektir.
ConfigureAwait (false), zaman uyumsuz tesisatta iş parçacığı bağlamını yok saymasını ve istediği eski iş parçacığında devam etmesini söyler. Bu, kırmızı görev gecikmesiyle tamamlanır tamamlanmaz, UI iş parçacığının kullanılabilir olmasını beklemesi gerekmediği anlamına gelir. Rastgele bir iş parçacığı iş parçacığı üzerinde çalışır.
Olay işleyicisinin görevlerinin bir iş parçacığında mı, birden fazla iş parçacığında mı çalışacağı konusunda hiçbir fikri yoktur. Tek bildiği, potansiyel olarak eşzamansız 3 görevin tamamlanmasını istemesidir. Temel uygulama ek konuların devreye girip girmeyeceğini belirleyecektir. Birden fazla iş parçacığına sahip olup olmamanız, paralel çalışıp çalışmadığınızı belirler. Bu nedenle, uygulamanızı yazarken ve hata ayıklarken her iki davranışa da hazırlıklı olmanız gerekir, çünkü sonunda, sadece bağlıdır.

 
                                                               EXTENSİON NEDİR?
Uzantılar, Visual Studio içinde çalışan ve yeni veya geliştirilmiş özellikler sağlayan kod paketleridir. Uzantılar, Visual Studio'ya işlevsellik katan denetimler, örnekler, şablonlar, araçlar veya diğer bileşenler olabilir

                                                    Per user and management extensions

Uzantıların çoğu kullanıcı başınadır ve %LocalAppData%\Microsoft\VisualStudio\<Visual>Studio sürümü\ \Extensions klasörüne yüklenir. Birkaç uzantı yönetim uzantılarıdır ve Visual * <Studio yükleme klasörüne\>\Common7\IDE\Extensions* klasörüne yüklenir.
Sisteminizi hatalar veya kötü amaçlı kod içerebilecek uzantılara karşı korumak için, kullanıcı başına uzantıları yalnızca Visual Studio normal kullanıcı izinleriyle çalıştırıldığında yüklenmesini kısıtlayabilirsiniz. Bu, Visual Studio yüksek izinlerle çalıştırıldığında kullanıcı başına uzantıların devre dışı bırakıldığı anlamına gelir.

Kullanıcı başına uzantıların yüklenmesini kısıtlamak için:
Uzantıseçenekleri sayfasını açın (Araç > Seçenekleri > Ortamı > Uzantıları).
Yönetici onay kutusu olarak çalışırken kullanıcı uzantıları başına Yükle'yi temizleyin.
Visual Studio'yu yeniden başlatın.


                                                  Automatic extension updates:

Uzantılar Visual Studio Marketplace'te yeni bir sürüm bulunduğunda otomatik olarak güncellenir. Uzantının yeni sürümü algılanır ve arka planda yüklenir. Visual Studio'yu bir sonraki açtığınızda, uzantının yeni sürümü çalışır.
Otomatik güncelleştirmeleri devre dışı kullanabilirsiniz, özelliği tüm uzantılar için veya yalnızca belirli uzantılar için devre dışı kullanabilirsiniz.
Tüm uzantılar için otomatik güncelleştirmeleri devre dışı kalmak için Extensions > UzantılarıYönet iletişim kutusunda uzantılar için ayarlarınızı değiştir bağlantısını seçin. Seçenekler iletişim kutusunda, uzantıları otomatik olarak güncelleştir'indenetimini kaldırın.
Belirli bir uzantı için otomatik güncelleştirmeleri devre dışı kalmak için, Uzantıları Yönet iletişim kutusunun sağ tarafındaki uzantının ayrıntılar bölmesinde bu uzantıyı otomatik olarak güncelleştirme seçeneğini kaldırın.

                                                     Crash and unresponsive notifications:

Visual Studio, bir önceki oturumda bir uzatmanın bir kazaya karıştığından şüphelenirse sizi fark edin. Visual Studio çöktüğe göre, özel durum yığınını depolar. Visual Studio bir dahaki sefere, yaprakile başlayan ve tabanına doğru çalışan, yığını inceler. Visual Studio, bir çerçevenin yüklü ve etkin bir uzantının parçası olan bir modüle ait olduğunu belirlerse, bir bildirim gösterir.
Visual Studio ayrıca, ui'nin yanıt vermemesine neden olan bir uzantıdan şüpheleniyorsa sizi de size haber verir.
Bu bildirimler gösterildiğinde, bildirimi yoksayabilir veya aşağıdaki eylemlerden birini alabilirsiniz:
Bu uzantıyı devre dışı bırakmayıseçin. Visual Studio uzantıyı devre dışı düşürür ve devre dışı bırakmanın etkili olması için sisteminizi yeniden başlatmanız gerekip gerekmediğini bilmenizi sağlar. İsterseniz Uzantıları > Yönet Uzantıları Iletişim kutusunda uzantıyı yeniden etkinleştirebilirsiniz.
Bu iletiyi bir daha asla gösterme'yiseçin.
Bildirim önceki oturumda bir kilitlenmeyle ilgiliyse, Visual Studio bu uzantıyla ilişkili bir kilitlenme oluştuğunda artık bir bildirim göstermez. Visual Studio, yanıt vermeme bu uzantıyla ilişkilendirildiğinde veya diğer uzantılarla ilişkilendirilebilen kilitlenmeler veya yanıt vermeme için bildirimler göstermeye devam eder.
Bildirim yanıt vermeme yle ilgiliyse, tümleşik geliştirme ortamı (IDE), bu uzantı yanıt vermeme ile ilişkilendirildiğinde artık bir bildirim göstermez. Visual Studio, bu uzantı ve diğer uzantılar için kilitlenme ve yanıt vermeyle ilgili bildirimler için çökmeyle ilgili bildirimleri göstermeye devam edecektir.







































