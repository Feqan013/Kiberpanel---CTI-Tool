# Kiberpanel - CTI Tool
Telegram platformasında paylaşılan Azərbaycan veb resurslarına məxsus infostealer loglarını və kibertəhdid mesajlarını toplayaraq istifadəçiləri məlumatlandıran plarforma 
# Kiberpanel - interfeys(demo versiya):
Veb interfeys vasitəsilə SOC komandaları şirkətə məxsus məlumat sızmaları, son xəbərlər və CVE-lər haqqında məlumat toplaya bilərlər.
Dashboard: Son xəbərlər və son məlumat sızmaları
<img width="1659" height="902" alt="dashboard" src="https://github.com/user-attachments/assets/1ab560f1-145b-488e-abe7-abdb3f0b8317" />
Logs: Loglar arasında axtarış funksiyası
<img width="1653" height="889" alt="logs" src="https://github.com/user-attachments/assets/7ccfb1f5-d1a8-44ec-b0fe-6e260b9f20d3" />
News: Xəbərlər
<img width="1651" height="905" alt="news" src="https://github.com/user-attachments/assets/58ffc9dd-ca0b-4ad1-8cdc-2fd8cb7ceded" />
CVEs: Boşluqlar
<img width="1654" height="909" alt="cves" src="https://github.com/user-attachments/assets/9eef89b2-219d-455a-95e4-729687752a96" />

Kiberpanel 2 funksiyaya sahibdir:
1) Infostealer Data Collector
2) Keyword Search - Alert


# 1)Infostealer Data Collector
Telegram Log hesablarında paylaşılan .txt, .zip, .rar formatlı log fayllarını yükləyir, unzip edir, göstərilən domainə(.az) görə hesabları toplayır, uyğun formata salır və diskdə saxlayır.

Windows,pycharm və python 3.12 ilə test edilib.
İstifadəsi üçün chromedriver(https://googlechromelabs.github.io/chrome-for-testing/) 7-zip(https://www.7-zip.org/download.html) və 400 GB+ yer tələb olunur. İki formatda işlədilə bilər:
```bash
python.exe TGscan.py "jun 10" ---- Göstərilən tarixdə paylaşılan hesablar üçün
python.exe TGscan.py ---- Dünənki tarixdə paylaşılan hesablar üçün(Task Scheduler-ə əlavə edilməsi üçün)
```
İşləməsi üçün kodun ilk sətirlərində olan path-lar editlənməlidir. Tarix və fayl adı avtomatik olar hesaba əlavə edilir. Proses bitdikdən sonra yüklənmiş bütün fayllar silinir.
![Diagram1](https://github.com/Feqan013/TGscan/assets/63374185/10bbf34f-6fd6-4d33-a409-cc4b2db0139f)
<img width="1079" height="1526" alt="342074667-10bbf34f-6fd6-4d33-a409-cc4b2db0139f" src="https://github.com/user-attachments/assets/b41d4a93-f19d-42fd-bd96-a84472f14aa2" />

Yüklənmə prosesi:


https://github.com/Feqan013/TGscan/assets/63374185/45986bf4-3e4a-4d1f-a5cd-48b67f8c870b
# 2)Keyword Search
APT və Hacker qruplarında hədəf keywordlərlə bağlı yeni mesaj paylaşıldığı zaman telegram üzərindən bot vasitəsilə mesaj göndərərək məlumatlandırır. DDOS hücumları və data breachlər haqqında tez məlumat almaq üçün istifadə edilir. Standart olaraq 5 dəqiqə intervalla axtarış edir. 7/24 işləməsi üçün nəzərdə tutlub.
İstifadə etmək üçün -k flagindən istifadə edilir:
```bash
python.exe TGscan.py -k ".az" "Azerbaijani" "test.az" ---- Göstərilən keywordlərlə bağlı hər-hansısa yeni mesaj paylaşılarsa istifadəçi məlumatlandırılacaq.
```
Axtarış prosesi:
![image](https://github.com/Feqan013/TGscan/assets/63374185/1e7690f1-0ac2-443b-899d-192ce32664d3)
Mesaj aşkar edildikdə botun göndərdiyi xəbərdarlıq(mesaj kontenti və ekran görüntüsü)
![image](https://github.com/Feqan013/TGscan/assets/63374185/c6d1e842-0879-4ab6-b373-a2a2286c4194)



