# atp_study_case
1- Docker Swarm ile cluster olarak çalışan ortamımıza aşağıdaki servisleri çalıştırabilecek stack.yaml dosyası oluşturulması gerekiyor.
Nginx
Apache Tomcat Server (A uygulaması)
Apache Tomcat Server (B uygulaması)
Mysql
Redis (Master)
Redis (Slave)
Ek maddeler:

Nginx uygulaması nginx.conf dosyasını Docker config içerisinden alıcak
Nginx uygulaması sadece "nginx=true" olarak etiketlenmiş makinelerde çalışacak, diğer uygulamalar "app=true" olarak etiketlenmiş makinelerde çalışacak
Mysql uygulamasındaki verilerin silinmemesi için volume kullanılacak
Uygulamalar için deploy section içerisinin düzenlenmesi gerekmektedir (mode, parelelisim,replicas,order gibi). Bu değerleri nelere dikkat ederek vermeliyiz?
Nginx'in 80 ve 443 portları dışarıya bind edilmiş olcak
Diğer uygulamar default portlarında çalışır olcak ama dışardan erişim sadece nginx üzerinden yapılıcak
nginx.conf dosyası oluşturulacak ve ve alt uygulamalara erişim sağlanacak şekilde configüre edilecek
80 ve 443 portlarından gelen istekler dinlenecek
SSL redirect yapılacak
Path bazlı alt uygulamalara yönlendirecek (örnek: /pathA veya /redis gibi)

2- Docker ile Sanal Makina arasındaki fark nedir?

3- Docker ile Kubernetes arasındaki fark nedir?

4- "Biz karar değiştirdik. Bu kubernetes denen şey güzele benziyor. Docker Swarmı atalım çöpe Kubernetes'e geçirelim bu uygulamaları" dedik.
   1. maddedeki uygulamaları Kubernetes ortamında nasıl taşırız? Hangi destek uygulamalarına ihtiyacın olur, süreci nasıl tasarlayabiliriz?
   Aynı şekilde ek bu maddeleri kubernetesde karşılayacak ve erişimlerini sağlayacak şekilde manifest dosyalarının oluşturulması gerekiyor.

5- Örnek olarak verilen Azure Devops Pipeline yaml dosyasında basit bir CI süreci bulunuyor. Bu dosyaya aşağıdaki özelliklerinde eklenmesi gerekmektedir.
Pipeline, sadece dev/test/preprod branchlerinde otomatik trigger olsun.
Pipeline, sadece main/src* ve pom.xml  dosyalarında değişiklik olursa otomatik trigger olsun.
Pipeline içerisindeki docker taskları deploy ismindeki bir parametre "true" olarak seçilirse çalışsın
"variables: env: dev" değeri tetiklenen branche göre güncellensin. (pipeline, test branchinden çalışıyorsa env: test olarak güncellensin)

7- İstanbul'da aylardan Şubat.
Saat gece 03:00. Bütün şirket, Devops ekibi dahil sıcak yataklarında uyuyor.
Sen ise nöbetçisin.
Telefon acı acı çaldı. Genel Müdür arıyordu,
çok kritik bir sistemde erişim sorunu falan bi sorunlar olduğunu söyledi.
Bütün ekipteki herkesi tek tek aradın ama nafile açan yok :(
Bu patlamış olan proje ile ilgili her sunucuya,servise vs erişimin var fakat uygulama hakkında hiç bir bilgin yok.
Ne yaparsın?
Hangi adımları takip edersin?
Sorunu nasıl çözmeye çalışırsın?

###########################################################################################################

                                                                KLASOR ACIKLAMALARI

-- CASE-STUDY-1

EK-MADDELER ---> EK MADDELERIN NASIL GERÇEKLENDIGI
dockerswarm.yaml  ---> DOCKER SWARMA GENEL BAKIS
multipasswithcreateubuntuserver.yaml ---> DOCKER SWARM CLUSTER ICIN UBUTU SERVER KURULUMU
nginx-latest-conf-aciklamalar ---> NGINX DOSYASI ACIKLAMASI
nginx-latest.conf  ---> NGINX CONF DOSYASI
stack-latest.yaml  ---> SERVICE YAML DOSYASI

-- CASE-STUDY-4

EK-MADDELER ---> EK MADDELERIN NASIL GERÇEKLENDIGI
Deployment, sevice , storageclass yaml dosylarını içerir.

-- CASE-STUDY-5

azure-pipeline-modified.txt ---> Pipeli'nin update edilmiş hali.
dort-madde ---> istenilen maddelerin açıklanması



