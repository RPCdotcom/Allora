> Öncelikle baştan uyarımızı yapalım.
> Güncelleme sonrası hata almanız gayet normal - RPC sorun çıkarabiliyor - cüzdanda tokenin yok diyebiliyor - boostrap gitti diyebiliyor ve dahası...

> Gelelim güncellemeye şimdi biz Allora'da Edgenet'de bulunuyorduk. Hop Toparlanın V2'ye gidiyoz dendi . Tatile diye köye götürülen kamyonetin arkasında doluşmuş kuzenler gibi nodelerimizi güncellediğimiz için RPC  Osmanlının zorladığı viyana kapılarına döndü çöküyor hocam.

> Yapacağumuz bazı işlemler var  : 

> Containerleri temizlicez. env dosyası düzenlicez yeni RPC koyacaz.

> Sonra Containerleri yeniden şahlandıracağız.

> Containerleri temizlemek ve işlemleri yapmak için 2 taraf var. Ruesin Rehberden CD Komutunu kullanıp ana dizinde `basic-coin-prediction-node` dosyan bulunuyor yada bu komutu atladın bu dosya `Allora-Chain` Dosyası içerisinde bulunuyor.

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

```console
          --boot-nodes=/ip4/172.22.0.100/tcp/9010/p2p/head-id \
          --topic=allora-topic-1-worker \
          --allora-chain-key-name=testkey \
          --allora-chain-restore-mnemonic='WALLET_SEED_PHRASE' \
          --allora-node-rpc-address=https://allora-rpc.testnet-1.testnet.allora.network/ \
          --allora-chain-topic-id=1
```

> Yeni RPC : 

```console
https://allora-rpc.testnet-1.testnet.allora.network/
```
