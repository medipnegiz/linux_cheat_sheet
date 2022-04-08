DevOps ve Networking İçin  Linux Komutları [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
===============
<hr>
<p align="center">
	<img alt="Git" src="./Img/linux.svg" height="190" width="455">
</p>
<hr>

### Index
* [lsof Command](#lsof_command)
* [Groups and Users](#groups_and_users)
* [id Command](#id_command)
* [cat Command](#cat_command)
* [diff Command](#diff_command)
* [dd Command](#dd_command)
* [route Command](#route_command)
* [mtr Command](#mtr_command)
* [nslookup ve dig Commands](#nslookup_ve_dig_commands)
* [tcpdump Command](#tcpdump_command)
* [sudo !! Command](#sudo_!!_command)
* [wget Command](#wget_command)
* [free Command](#free_command)
* [tr Command](#tr_command)
* [htop, ps ve kill Commands](#htop_ps_ve_kill_commands)
* [head and tail Commands](#head_and_tail_commands)
* [man Command](#man_command)
* [sort Command](#sort_command)
* [chown Command](#chown_command)
* [chmod Command](#chmod_command)

<hr>

## lsof Command 
##### (lsof(List Of Open File) sistemdeki tüm çalışan dosyaları listeler.)

##### Belirtilen user tarafından açılmış dosyaları listeler.:
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

## id Command
##### (User ve Grup numarik id’lerini listeler.)

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

## cat Command
##### (Bu komut ile belgeleri okuyabilir, değiştirirebilir ve birleştirebiliriz.)

##### test-1.txt ve test-2.txt belgelerini birleştirerek çıktısını verir:
```
cat “test-1.txt” “test-2.txt” 
```

##### Seçilen belgenenin tüm satırlarını numaralandırır:
```
cat -b 
```

##### Seçilen belgenin boş olmayan satırlarını da numaralandırır:
```
cat -n 
```

<hr>

## diff Command

##### Bu komut iki dosya arasındaki farkları listeler:
```
diff “test-1.txt” “test-2.txt”
```

<hr>

## dd Command
##### (Bu komut belirtilen belge ve ya dizini belirtilen hedefe kopyalar. cpden farklı olarak byte-to-byte kopyalama işlemi yapar. Örneğin bir diskin başka bir diske kopyalamasını yaparken diskin tam bir replikasını oluşturur.(AWS snapshot gibi) Backup almakta kullanışlıdır.)

##### Mountpoint1 diskini olduğu gibi Mountpoint2 diskine kopyalar:
```
dd if = /dev/mp1 of = /dev/mp2 
```

##### Tüm commitleri görüntüler(Sadece commit hash ve commit mesajı görüntülenir.):
```
$ git log --oneline
```

##### Eğer kopyalama işlemindeki hatalar gözardı edilmek isteniyorsa conv=noerror parametresi verilir:
```
dd conv=noerror if = /dev/mp1 of = /dev/mp2
```

<hr>

## route Command

##### Bulunduğumuz ağın route table bilgilerini listeler:
```
route
```

##### ICMP protokolünü kullanarak belirtilen hedefe gönderilen paketin kaç atlamada hedefe ulaştığını gösterir.:
```
traceroute google.com
```

<hr>

## mtr Command
##### (mtr komutu ping ve traceroute komutlarını kombine eder. Gerçek zamanlı olarak gönderilen pakette gerçekleşen veri kayıplarını ve geçikme sürelerini detaylı olarak listeler.)

##### Gerçek zamanlı olarak listeler:
```
mtr google.com 
```

##### Hedefe sadece 10 paket atarak sonucu rapor halinde listeler. "-n" parametresi DNS çözümlemesini engeller.:
```
mtr -n --report google.com
```

<hr>

## nslookup ve dig Commands

##### Belirtilen adresin NS ve SOA kayıtlarını sıralar:
```
nslookup github.com
```
```
dig google.com
```

<hr>

## tcpdump Command
##### (Makinada bulunan tüm network interface’lerin durumunu sorgular ve interfacelerden gönderilen paketleri yakalar.)

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

## sudo !! Command

##### Bu komut, komut satırında kendinden önce girilen komutu root izni ile tekrarlar:
```
sudo !!
```

<hr>

## wget Command

##### Bu komut ile belirtilen web sayfası indirilir:
```
wget https://www.linkedin.com/in/mahmut-edip-negiz-6b1145213/
```

<hr>

## free Command

##### diskin kullanım durumunu listeler:
```
free
```

##### bytes olarak listeler:
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

## tr Command
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

## htop, ps ve kill Commands

##### htop gerçek zamanlı olarak cpu ve memory kullanımını gösterir. ps komutunun aksine mouse ile etkileşimlidir:
```
htop
```

#####  ps komutu da cpu ve memory kullanımını gösterir, htop komutunundan farklı olarak çıktıyı rapor haline sunar:
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

## head and tail Commands

##### Belgenin ilk on satırını çıkarır:
```
head “dosya.txt” 
```

##### Belgenin son on satırını çıkarır:
```
tail “dosya.txt”  
```

<hr>

## head and tail Commands

##### Bu komut diğer tüm komutların detaylı kullanımını açıklar:
```
man whoami
```

<hr>

## sort Command
##### (Bu komut ile hem alfabetik hem de numerik sıralama yapılır. Dosyaları, dosya içeriklerini ve dizinleri sıralar. Sıralamayı case sensitive olarak yapar.)

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

## chown Command

##### Dosyaların sahipliğini değiştirir:
```
sudo chown “kullanıcı_veya_grup_adı” “dosya_adı”
```

<hr>

## chmod Command

##### Bu komut, dosya ve dizinlerin erişim izinlerini değiştirmek için kullanılır. Her bir basamak user, group ve others kullanıcılılarını temsil eder:
```
chmod 754 “dosya.txt”

4 →read(r) permission
2 → write(w) permission
1 → execute(x) permission
0 → no permission
```