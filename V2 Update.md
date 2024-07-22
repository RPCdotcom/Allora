> Öncelikle baştan uyarımızı yapalım.

> Güncelleme sonrası hata almanız gayet normal - RPC sorun çıkarabiliyor - cüzdanda tokenin yok diyebiliyor - boostrap gitti diyebiliyor ve dahası...

> Gelelim güncellemeye şimdi biz Allora'da Edgenet'de bulunuyorduk. Hop Toparlanın V2'ye gidiyorz dendi .  Haliyle RPC'de değişti.

> RPC Osmanlının zorladığı viyana kapılarına döndü. çöküyor hocam. Yapacak birşey yok.

> Yapacağımız bazı işlemler var  : 

> Containerleri temizliyeceğiz. docker-compose.yml dosyası düzenleyeceğiz. yeni RPC yerleştireceğiz..

> Sonra Containerleri yeniden şahlandıracağız.

> Containerleri temizlemek ve işlemleri yapmak için 2 taraf var. 

> Ruesin Rehberden CD Komutunu kullanıp ana dizinde `basic-coin-prediction-node` dosyan bulunuyor yada bu komutu atladın bu dosya `Allora-Chain` Dosyası içerisinde bulunuyor.

> Bunu Nasıl Anlarım ? ls komutunu terminale yapıştırdın. Bakıyorsun dizinlere eğer `basic-coin-prediction-node` yoksa Allora-Chain içerisinde.

> Ruesin Rehberden `Komut Atlamayarak` Kurdum : 

```console
cd basic-coin-prediction-node
```

> Ruesin Rehberden `CD Komutunu Atlayarak` Kurdum : 

```console
cd allora-chain
```

```console
cd basic-coin-prediction-node
```

> Geldik Container Kısmına Buradada 2 Seçenek Var - Sunucumda farklı bir node yok sadece allora var diyorsanız 1.yi ! Sunucumda farklı nodeler var Docker Container Olabilir diyorsanız 2.yi ! kullanın.

> Sunucumda sadece Allora Var Containerleri Sileceğim : 

```console
docker rm -f $(docker ps -a -q) && docker system prune --volumes -a -f
```

> Sunucumda farklı nodelerde var Docker Container Kullanıyor Olabilirler Diyenler : 

```console
docker ps -a
```

> Bu komut ile Allora'ya Ait Olan Containerlerin id'sini kopyalayıp not edelim.

```console
docker stop containeridsi
```

> Bu komut ile teker teker containerleri stoplatalım.

```console
docker rm containeridsi
```

> Bu komut ile teker teker containlerin fişlerini çekelim.

Geldik Değişim Kısmına : 

```console
nano docker-compose.yml
```

> Girdik içeriye - değiştireceğimiz kısım RPC : 

> Dosya İçerisinde Tam burada "--allora-node-rpc-address=" sizde eski RPC yer alıcaktır. Eskiyi silip yenisini yapıştırın.

![image](https://github.com/user-attachments/assets/caa445b0-a9d2-4cf0-8138-c0b2bb8ef40b)

> Yeni RPC : 

```console
https://allora-rpc.testnet-1.testnet.allora.network/
```

> CTRL X - CTRL Y - Enter ile kaydedin.

> Ardından yeniden ayağa kaldıralım. 

```console
docker compose build
docker compose up -d
```

Logları kontrol etmeyi biliyorsunuz. 

Görmemiz gereken loglarda şöyle olmalı : 

![image](https://github.com/user-attachments/assets/530bdbe5-530b-4202-b7e1-c889b0c683bc)

> Baktın token yok hatası veriyor : 

> Faucet üzerinden token al - şu ara sorunlu sıkıntılar çıkarabiliyor. Tokenin cüzdana geldiğinden emin olun. 

> Faucet : https://faucet.testnet-1.testnet.allora.network/

> Sonrasında yine dizin içerisinde durdurup ayağa kaldırın : 

```console
docker compose down
```

```console
docker compose up -d
```

> Sonrasında yeniden loglarınızı kontrol edip - doğru çalıştığından emin olun.

> Dostlarınızla yardım edin / yardımlaşın CT. Bilgi paylaştıkça çoğalır.
