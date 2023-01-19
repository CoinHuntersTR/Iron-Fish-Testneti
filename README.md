# Iron Fish Ödüllü Node Test Kurulum Rehberi

![aleotestneti](https://miro.medium.com/max/720/1*sxBBcNLRideJweRal2pMmw.webp)


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

### Gerekli olan portları açıyoruz.
> Portları sırasıyla giriyoruz.

```
sudo ufw allow 4133/tcp
sudo ufw allow 3033/tcp
```

### Node için gerekli olan kurulumları yapıyoruz.
> Kodları sırasıyla giriyoruz.
```
tmux
git clone https://github.com/AleoHQ/snarkOS.git --depth 1
cd snarkOS
./build_ubuntu.sh
cargo install --path .
```
### Cüzdan oluşturuyoruz

```
snarkos account new
```

> Cüzdanı kurulumunu yaptığınızda size verilen bilgileri kayıt etmeyi unutmayın.

Buradaki gibi çıktı alacaksınız;
```
Private Key    APrivateKey1xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  <-- Save Me And Use In The Next Step
     View Key  AViewKey1xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  <-- Save Me
      Address  aleo1xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx  <-- Save Me 
```
## Node Başlatıyoruz
> Aşağıdaki kodu girdiğinizde çıkan ekranda sizden cüzdanınızın Private Key'ini girmenizi istiyor.
```
./run-prover.sh
```
Bu adımda private keyimizi girdiğimizde çalışmaya başlıyor. Sonrasında blokda ödül kazanıp kazanmadığımıza explorer üzerinden cüzdan adresimizle bakabiliriz.

# Explorer
### https://www.aleo.network/
### https://aleo123.io/
### https://explorer.hamp.app/

# Aleo Sosyal Medya Bağlantıları
### [Discord](https://discord.gg/aleohq)
### [Twitter](https://twitter.com/AleoHQ)
