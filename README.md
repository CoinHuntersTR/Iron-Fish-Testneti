# Iron Fish Ödüllü Node Test Kurulum Rehberi

![aleotestneti](https://miro.medium.com/max/720/1*sxBBcNLRideJweRal2pMmw.webp)


### Önerilen Sistem Gereksinimleri;

|CPU | RAM  | Disk  | 
|----|------|----------|
|  32| 32GB  | 128GB    |

### Minimum kurulum için gereksinimler;
|CPU | RAM  | Disk  | 
|----|------|----------|
|  16| 16GB  | 128GB    |
 # Daha önce Node kurulumu yapmadıysanız buradan sırasıyla adımları takip ederek tüm süreci öğrenebilirsiniz.
  ## Yeni Başladım Rehberi; [Pusula Finans Labs.](https://www.labs.pusulafinans.com/category/rehber/)
  ### 1. [Testnet ve Node test kurulum rehberi Bölüm-1](https://www.labs.pusulafinans.com/2022/08/23/testnet-ve-node-kurulum-rehberi/)
  ### 2. [Yeni Chrome Tarayıcı nasıl açarım?](https://www.labs.pusulafinans.com/2022/08/23/yeni-chrome-tarayici-nasil-acarim/)
  ### 3. [Ücretsiz Sunucu Kiralama](https://www.labs.pusulafinans.com/2022/08/23/nasil-ucretsiz-sunucu-kiralarim/)
  ### 4. [Digital Ocean Nasıl Kayıt olurum?](https://www.labs.pusulafinans.com/2022/08/23/digital-oceana-nasil-kayit-olabilirim/)
  ### 5. [MobaXTerm Terminal Kurulumu](https://www.labs.pusulafinans.com/2022/08/23/mobaxterm-terminal-kurulumu/)
  
## UYARI

Aleo testneti PoW ve CPU ve Hashrate dayalı olduğu için, ödüllü testnet olmasına rağmen ödül kazanamayabilirsiniz. Ücretli aldığınız cihazlarda bile mining yaparken blok bulamazsanız ödüle hak kazanmayacağınızı bilin. Bu nedenle yapıp yapmamak size kalmış durumda. Bir önceki testnette katılıp hiç ödül kazanamayanlara ekip teselli ödülü vermişti. Bunu tekrar eder mi bilinmez? 

### Sistem Güncellemeleri;

```
sudo apt update
sudo apt install make clang pkg-config libssl-dev build-essential gcc xz-utils git curl vim tmux ntp jq llvm ufw -y
```

### Rust Yüklüyoruz.

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
source $HOME/.cargo/env
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
