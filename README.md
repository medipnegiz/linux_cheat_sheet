DevOps ve Networking İçin  Linux Komutları [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
===============
<hr>
<p align="center">
	<img alt="Git" src="./Img/linux.svg" height="190" width="455">
</p>
<hr>

# Diğer Mevcut Diller:

1. [German Linux Cheat Sheet](https://github.com/medipnegiz/linux_cheat_sheet/tree/main/other_sheet/linux_cheat_sheet_ge.md)
2. [English Linux Cheat Sheet](https://github.com/medipnegiz/linux_cheat_sheet/tree/main/other_sheet/linux_cheat_sheet_en.md)
<hr>

### İçindekiler
* [lsof Komutu](#lsof_komutu)
* [Groups and Users](#groups_and_users)
* [id Komutu](#id_komutu)
* [cat Komutu](#cat_komutu)
* [diff Komutu](#diff_komutu)
* [dd Komutu](#dd_komutu)
* [route Komutu](#route_komutu)
* [mtr Komutu](#mtr_komutu)
* [nslookup ve dig Komutları](#nslookup_ve_dig_komutları)
* [tcpdump Komutu](#tcpdump_komutu)
* [sudo !! Komutu](#sudo_!!_komutu)
* [wget Komutu](#wget_komutu)
* [free Komutu](#free_komutu)
* [tr Komutu](#tr_komutu)
* [htop, ps ve kill Komutları](#htop_ps_ve_kill_komutları)
* [head and tail Komutları](#head_and_tail_komutları)
* [man Komutu](#man_komutu)
* [sort Komutu](#sort_komutu)
* [chown Komutu](#chown_komutu)
* [chmod Komutu](#chmod_komutu)

<hr>

## lsof Komutu 
##### (lsof(List Of Open File) sistemdeki tüm çalışan dosyaları listeler)

##### Belirtilen user tarafından açılmış dosyaları listeler:
```
lsof -u “user”
```

<hr>

## Groups and Users

##### Yeni bir User ekler:
```
sudo useradd “username”
```

##### Yeni User’ın şifresini oluşturur:
```
sudo passwd “username” 
```

##### Belirtilen User’ı siler:
```
sudo userdel “username” 
```

##### Yeni bir grup oluşturur:
```
sudo groupadd “groupname” 
```

##### Belirtilen grubu siler:
```
sudo groupdel “groupname” 
```

##### Belirtilen gruba belirtilen User’ı ekler:
```
sudo usermod -g “groupname” “username” 
```

<hr>

## id Komutu
##### (User ve Grup numarik id’lerini listeler)

##### Mevcut grup id:
```
id -g 
```

##### Tüm grupların id’leri:
```
id -G
```

##### Mevcut user id:
```
id -u 
```

<hr>

## cat Komutu
##### (Bu komut ile belgeleri okuyabilir, değiştirirebilir ve birleştirebiliriz)

##### test-1.txt ve test-2.txt belgelerini birleştirerek çıktısını verir:
```
cat “test-1.txt” “test-2.txt” 
```

##### Seçilen belgenin tüm satırlarını numaralandırır:
```
cat -b 
```

##### Seçilen belgenin boş olmayan satırlarını da numaralandırır:
```
cat -n 
```

<hr>

## diff Komutu

##### Bu komut iki dosya arasındaki farkları listeler:
```
diff “test-1.txt” “test-2.txt”
```

<hr>

## dd Komutu
##### (Bu komut belirtilen belge ve ya dizini belirtilen hedefe kopyalar. cpden farklı olarak byte-to-byte kopyalama işlemi yapar. Örneğin bir diskin başka bir diske kopyalamasını yaparken diskin tam bir replikasını oluşturur.(AWS snapshot gibi) Backup almakta kullanışlıdır)

##### Mp1 diskini olduğu gibi Mp2 diskine kopyalar:
```
dd if = /dev/mp1 of = /dev/mp2 
```

##### Tüm commitleri görüntüler(Sadece commit hash ve commit mesajı görüntülenir):
```
$ git log --oneline
```

##### Eğer kopyalama işlemindeki hatalar gözardı edilmek isteniyorsa conv=noerror parametresi verilir:
```
dd conv=noerror if = /dev/mp1 of = /dev/mp2
```

<hr>

## route Komutu

##### Bulunduğumuz ağın route table bilgilerini listeler:
```
route
```

##### ICMP protokolünü kullanarak belirtilen hedefe gönderilen paketin kaç atlamada hedefe ulaştığını gösterir:
```
traceroute google.com
```

<hr>

## mtr Komutu
##### (mtr komutu ping ve traceroute komutlarını kombine eder. Gerçek zamanlı olarak gönderilen pakette gerçekleşen veri kayıplarını ve geçikme sürelerini detaylı olarak listeler)

##### Gerçek zamanlı olarak listeler:
```
mtr google.com 
```

##### Hedefe sadece 10 paket atarak sonucu rapor halinde listeler. "-n" parametresi DNS çözümlemesini engeller:
```
mtr -n --report google.com
```

<hr>

## nslookup ve dig Komutları

##### Belirtilen adresin NS ve SOA kayıtlarını sıralar:
```
nslookup github.com
```
```
dig google.com
```

<hr>

## tcpdump Komutu
##### (Makinada bulunan tüm network interface’lerin durumunu sorgular ve interfacelerden gönderilen paketleri yakalar)

##### Tüm arayüzleri listeler:
```
sudo tcpdump --list-interfaces
```

##### Tüm arayüzlerin paket iletimini dinler:
```
sudo tcpdump
```

##### Belirtilen arayüzün paket iletimini dinler:
```
sudo tcpdump -i eth0
```

##### Paket dinleme işlemini 10 ile sınırlar:
```
sudo tcpdump -i eth0 -c 10 
```

<hr>

## sudo !! Komutu

##### Bu komut, komut satırında kendinden önce girilen komutu root izni ile tekrarlar:
```
sudo !!
```

<hr>

## wget Komutu

##### Bu komut ile belirtilen web sayfası indirilir:
```
wget https://www.linkedin.com/in/mahmut-edip-negiz-6b1145213/
```

<hr>

## free Komutu

##### diskin kullanım durumunu listeler:
```
free
```

##### diskin kullanım durumunu byte olarak listeler:
```
free -b
```

#####  kilobytes olarak listeler (default):
```
free -k
```

##### megabytes olarak listeler:
```
free -m
```

##### gigabytes olarak listeler:
```
free -g
```

<hr>

## tr Komutu
##### (tr komutu ile belirtilen dosyanın içinde manipülasyonlar yapılabilir. Pipeler | kullanılarak daha karmaşık scriptler yazılabilir.)

##### deneme.txt içindeki tüm e’ler o olur:
```
cat deneme.txt | tr “e” “o” 
```

#####  deneme.txt içindeki tüm küçük harfler BÜYÜK olur:
```
cat deneme.txt | tr “[a-z]” “[A-Z]”
```

#####  deneme.txt içindeki tüm i’ler silinir:
```
cat deneme.txt | tr -d “i” 
```

<hr>

## htop, ps ve kill Komutları

##### htop gerçek zamanlı olarak cpu ve memory kullanımını gösterir. ps komutunun aksine mouse ile etkileşimlidir:
```
htop
```

#####  ps komutu da cpu ve memory kullanımını gösterir, htop komutundan farklı olarak çıktıyı rapor haline sunar:
```
ps aux

a = Tüm kullanıcıların işlemlerini gösterir.
u = İşlemin sahibini gösterir.
x = Terminale bağlı olmayan işlemleri gösterir.
```

#####  kill komutu ile de bu ID’ler kullanılarak işlem sonlandırılır:
```
kill “ID”
```

<hr>

## head and tail Komutları

##### Belgenin ilk on satırını çıkarır:
```
head “dosya.txt” 
```

##### Belgenin son on satırını çıkarır:
```
tail “dosya.txt”  
```

<hr>

## head and tail Komutları

##### Bu komut diğer tüm komutların detaylı kullanımını açıklar:
```
man whoami
```

<hr>

## sort Komutu
##### (Bu komut ile hem alfabetik hem de numerik sıralama yapılır. Dosyaları, dosya içeriklerini ve dizinleri sıralar. Sıralamayı case sensitive olarak yapar)

##### Çıktıyı ters olarak sıralar:
```
sort -r
```

##### Çıktıyı case insensitive olarak sıralar:
```
sort -f 
```

##### Çıktıyı numerik olarak sıralar:
```
sort -n
```

<hr>

## chown Komutu

##### Dosyaların sahipliğini değiştirir:
```
sudo chown “kullanıcı_veya_grup_adı” “dosya_adı”
```

<hr>

## chmod Komutu

##### Bu komut, dosya ve dizinlerin erişim izinlerini değiştirmek için kullanılır. Her bir basamak user, group ve others kullanıcılılarını temsil eder:
```
chmod 754 “dosya.txt”

4 →read(r) permission
2 → write(w) permission
1 → execute(x) permission
0 → no permission
```
