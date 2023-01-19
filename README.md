# Iron Fish Ödüllü Node Test Kurulum Rehberi

![Iron-Fish-Testneti](https://miro.medium.com/max/720/1*sxBBcNLRideJweRal2pMmw.webp)


### Önerilen Sistem Gereksinimleri;

|CPU | RAM  | Disk  | 
|----|------|----------|
|  4| 8GB  | 160GB    |

 # Daha önce Node kurulumu yapmadıysanız buradan sırasıyla adımları takip ederek tüm süreci öğrenebilirsiniz.
  ## Yeni Başladım Rehberi; [Coin Hunters](https://coinhunterstr.com/)
  ### 1. [Testnet ve Node test kurulum rehberi Bölüm-1](https://coinhunterstr.com/testnet-ve-node-kurulum-rehberi/)
  ### 2. [Yeni Chrome Tarayıcı nasıl açarım?](https://coinhunterstr.com/yeni-chrome-tarayici-nasil-acarim/)
  ### 3. [Ücretsiz Sunucu Kiralama](https://coinhunterstr.com/ucretsiz-sunucu-nasil-kiralarim/)
  ### 4. [Digital Ocean Nasıl Kayıt olurum?](https://coinhunterstr.com/digital-oceana-nasil-kayit-olabilirim/)
  ### 5. [MobaXTerm Terminal Kurulumu](https://coinhunterstr.com/mobaxterm-terminal-kurulumu/)
  
## UYARI

Iron Fish Ödüllü testnetine katılabilmek için, mutlaka sitesine kayıt olmanız ve oraya verdiğiniz kullanıcı adi ile node kuracağınız kullanıcı adının aynı olması gerekir. Rehber içerisinde adımları dikkatlice takip edebilirsiniz.

### Sistem Güncellemeleri;

```
sudo apt update && apt upgrade -y
```

### Sistem Gereksinimlerini yüklüyoruz.

```
sudo apt install build-essential g++ make
```

### Yeni bir screen kurulma
> Sunucu içinde yeni bir screen oluşturuyoruz. Kurulum ve takibini oradan yapacağız.
```
sudo apt install screen
```
> "Screen Adı" tırnaklar dahil kaldırıp istediğiniz adı girebilirsiniz.
> Örnek sudo screen -S ironfish gibi
```
sudo screen -S "Screen Adı"
```

### Node js kurulumu ile devam ediyoruz.

```
sudo curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash - &&\
sudo apt-get install -y nodejs
```

### Iron Fish Node yüklüyoruz.

```
sudo npm install -g ironfish
```
### Kurulumu kontrol etmek için aşağıdaki kodu girebilirsiniz. 

```
ironfish
```
> kod sonrasında aşağıdaki gibi bir çıktı almanız gerekiyor.
![Iron-Fish-Testneti](https://miro.medium.com/max/720/1*HqdNlZgHIA4Nqs0Qus11kA.webp)

## Node için gerekli portları açıyoruz.
```
ufw allow ssh
ufw allow 9033
ufw enable 
```
> Terminal aşağıdaki gibi bir soru yöneltirse -y diyip devem ediyoruz.
![Iron-Fish-Testneti](https://miro.medium.com/max/720/1*Jqi9YDGMThdsTAhIVhv0Qw.webp)

## Iron Fish Sitesine kayıt
Devam etmek için [Buradan](https://testnet.ironfish.network/about) sitesine ulaşıyoruz. Aşağıdaki bulunan resim gibi "Incentivited Testnet Phase 3" yazan bölümün altındaki "Sign up" basıyoruz.

![Iron-Fish-Testneti](https://miro.medium.com/max/720/1*mB4zgPx1NDBWwNAV_0qxmw.webp)

Sonrasında, aşağıdaki formdaki bilgileri doldurup kayıt oluyoruz.
### UYARI: Graffiti adını node ismiyle aynı olacak şekilde seçin!!
![Iron-Fish-Testneti](https://miro.medium.com/max/720/1*-9g3lQCL3Pbk8RbAh-irsg.webp)

Kayıt olduktan sonra, sağda Graffiti adımızın üzerine basıyoruz. Görseldeki gibi tarayıcıdaki URL adresini kopyalıyoruz.
![Iron-Fish-Testneti](https://miro.medium.com/max/720/1*FDYKvBPJ9WLnvlCteBEjEw.webp)
> Terminale dönüyoruz.

## Node ismimizi Graffiti adımız ile eşleştiriyoruz.
```
ironfish testnet
```
> Bizden biraz önce kopyaladığımız URL adresini istiyor.
> ![Iron-Fish-Testneti](https://miro.medium.com/max/720/1*uh2X64hiz3H1EEfYOtau5Q.webp)

> URL adresini girdikten sonra -y basıp ENTER diyoruz. Aşağıdaki gibi bir çıktı alıyoruz.
> ![Iron-Fish-Testneti](https://miro.medium.com/max/720/1*v1as1DmiyhDFR7SYxSqe6g.webp)


## Node Çalıştırıyoruz.
```
ironfish start
```
> 10-15dk. içerisinde sekronize olmasını bekliyoruz. 
> CTRL A+D ile screenden çıkıyoruz. !!! Kesinlikle CTRL+C yapmıyoruz. Node durmasına neden olursunuz.

## Screen ekranına tekrar girme
> 1. Adımda aşağıdaki kodu giriyoruz. Sunucuda olan screenleri listeler.
```
screen -ls
```
> Sonrasında listelenmiş olan screenin tam ismini alıp; örnek screen -r 14423.ironfish
> "screen ismi" kısmını silip onu yazıyoruz.
> ![Iron-Fish-Testneti](https://miro.medium.com/max/720/1*38oosgvYLZM5_QEE_PfuCQ.webp)
```
screen -r "screen ismi"
```
## Node durumunu öğrenme
```
ironfish status -f
```
> Görseldeki gibi bir çıktı alıyorsanız sorun yoktur. 
> ![Iron-Fish-Testneti](https://miro.medium.com/max/720/1*8hIaI5NIHGzDO-1a1PVVaw.webp)

# Yararlı Komular

## Node Tekrar Çalıştırma

> Node durduğunda tekrar çalıştırmak için
```
ironfish start
```
## Node Hataları için

> Node hata alırsanız, hata detayını görmek için
```
ironfish logs -v
```
## Node Bağlı olduğu peerları görmek için

> Node hata alırsanız, hata detayını görmek için
```
ironfish peers -f
```
>![Iron-Fish-Testneti](https://miro.medium.com/max/720/1*9T0Lb26veztF8sCm_HMqxw.webp)

## Iron Fish Cüzdan Listesi

```
ironfish wallet:accounts
```

## Iron Fish Cüzdan Adresi

```
ironfish wallet:address
```

## Iron Fish Cüzdan Değeri
> Cüzdan içideki coinlerin sayısını görmek için
```
ironfish wallet:balances
```
## Iron Fish Cüzdan Adresi

```
ironfish wallet:address
```

## Iron Fish Faucetten Coin almak için

```
ironfisf faucet
```
> mail adresinizi giriyorsunuz. (Siteye kayıt olduğunuz mail adresinizi girin.)
> Enter basıyorsunuz.
> Yoğunluğa göre biraz zaman alabilir ama test tokenleri gelecektir.

# Ödüllü Testnet 3. Görevleri;

## Asset Mint Görevi
> Öncelikle cüzdanınızda bakiye yoksa faucet bölümünden token isteyin.
> Alttaki komutu girip -y ENTER basıyoruz.
> Bu işlem için sizde asset ismi isteyecek girdiğiniz graffiti adını verebilirsiniz. Enter basıyoruz.
> asset metadatasını isteyecek tekrardan graffiti adınız verebilirsiniz. Enter basıyoruz.
> Ne kadar sayıda basmak istediğinizi soruyor, örnek 20 adet diyebilirsiniz. Enter basıyoruz.
> Fiyatınızı belirlemenizi istiyor örnek: 0.00000001 yazabilirsiniz. Enter basıyoruz.
> Sonunda bir çıktı alıyorsunuz, oradaki bağlantıyı 10dk. sonrasında explorerdan kontrol edebilirsiniz. 

```
ironfish wallet:mint
```
![Iron-Fish-Testneti](https://miro.medium.com/max/720/1*wO_jd-tA9NNfgX-B_TVDYw.webp)

## Burn Asset Görevi
> Bir önceki görevde oluşturduğunu assetlerin "Asset Indetifier" ID'sini alıyoruz. ENTER basıyoruz.
> Kaç adedini yakacağımızı giriyoruz. Örneğin 5 tanesini, sonra ENTER basıyoruz. 
> Fiyat kısmına 0.00000001 yazıyoruz ve ENTER basıyoruz.
> Bize sorulan soruya -y diyor ve ENTER basıyoruz.
> Sonunda bir çıktı alıyorsunuz, oradaki bağlantıyı 10dk. sonrasında explorerdan kontrol edebilirsiniz.

```
ironfish wallet:burn
```
![Iron-Fish-Testneti](https://miro.medium.com/max/720/1*d1SEa0tvBNTO1suL0EgYKA.webp)

## Send Asset Görevi
>Bir önceki görevde oluşturduğunu assetlerin "Asset Indetifier" ID'sini alıyoruz. ENTER basıyoruz.
>Kaç adedini göndereceğimizi belirliyoruz. Örneğin 5 tanesini yazıyoruz ve ENTER basıyoruz.
>Iron Fish Public adres giriyoruz. Bunun için discord kanallarından veya başka katılanlardan adreslerini isteyebilirsiniz. Adresi girdikten sonra ENTER basıyoruz.
>Fiyat kısmına 0.00000001 yazıyoruz ve ENTER basıyoruz.
>Sonunda bir çıktı alıyorsunuz, oradaki bağlantıyı 10dk. sonrasında explorerdan kontrol edebilirsiniz.

```
ironfish wallet:send
```
![Iron-Fish-Testneti](https://miro.medium.com/max/720/1*-cB1VJsgjbblOEkzMcBbiQ.webp)

# UYARI
### Yukarıdaki görevleri haftada bir kere yapılması gerekiyor. Her biri 200 puan değerinde testnet süresince hepsini mutlaka yapın.



## Iron Fish Discord kanalına katılmayı unutmayın;
### [Discord](https://discord.gg/35ZxaUquTc)

## Yarım için telegram kanalımız;
### [Coin Hunters Telegram](https://t.me/CoinHuntersTR)
