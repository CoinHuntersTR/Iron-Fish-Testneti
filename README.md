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

## Node Çalıştırıyoruz.
```
ironfish start
```
> 10-15dk. içerisinde sekronize olmasını bekliyoruz. 
> CTRL A+D ile screenden çıkıyoruz. !!! Kesinlikle CTRL+C yapmıyoruz. Node durmasına neden olursunuz.


# Explorer
### https://www.aleo.network/
### https://aleo123.io/
### https://explorer.hamp.app/

# Aleo Sosyal Medya Bağlantıları
### [Discord](https://discord.gg/aleohq)
### [Twitter](https://twitter.com/AleoHQ)
