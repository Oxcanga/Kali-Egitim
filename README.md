# 🔒 Kali Linux Araçları Cheat Sheet

## 📋 İçindekiler
- [Bilgi Toplama Araçları](#bilgi-toplama-araçları)
- [Zafiyet Analiz Araçları](#zafiyet-analiz-araçları)
- [Kablosuz Ağ Araçları](#kablosuz-ağ-araçları)
- [Web Uygulama Araçları](#web-uygulama-araçları)
- [Şifre Saldırı Araçları](#şifre-saldırı-araçları)
- [Forensic Araçları](#forensic-araçları)

## 🔍 Bilgi Toplama Araçları

### Nmap (Network Mapper)
```bash
# Basit tarama
nmap 192.168.1.1

# Detaylı tarama
nmap -sV -sC 192.168.1.1

# Gizli tarama
nmap -sS 192.168.1.1

# Tüm portları tarama
nmap -p- 192.168.1.1
```

### Whois
```bash
whois domainadi.com
```

### DNSRecon
```bash
# DNS kayıtlarını listeleme
dnsrecon -d domainadi.com

# Zone transfer denemesi
dnsrecon -d domainadi.com -t axfr
```

## 🎯 Zafiyet Analiz Araçları

### Nikto
```bash
# Temel web sunucu taraması
nikto -h http://hedefsite.com

# SSL destekli tarama
nikto -h https://hedefsite.com -ssl
```

### OpenVAS
```bash
# OpenVAS servisini başlatma
openvas-start

# Tarama başlatma
omp -u admin -w şifre -T
```

## 📡 Kablosuz Ağ Araçları

### Aircrack-ng
```bash
# Ağ kartını monitor moda alma
airmon-ng start wlan0

# Etraftaki ağları tarama
airodump-ng wlan0mon

# WPA/WPA2 el sıkışması yakalama
airodump-ng -w kayit --bssid [HEDEF_MAC] -c [KANAL] wlan0mon
```

### Wifite
```bash
# Otomatik kablosuz ağ saldırısı
wifite --dict wordlist.txt
```

## 🌐 Web Uygulama Araçları

### SQLMap
```bash
# Basit SQL injection taraması
sqlmap -u "http://hedef.com/sayfa.php?id=1"

# Veritabanı listeleme
sqlmap -u "http://hedef.com/sayfa.php?id=1" --dbs

# Tablo listeleme
sqlmap -u "http://hedef.com/sayfa.php?id=1" -D veritabani --tables
```

### Burp Suite
- Proxy ayarları: 127.0.0.1:8080
- Intercept özelliği ile HTTP/HTTPS trafiğini yakalama
- Active Scanner ile otomatik zafiyet taraması
- Repeater ile manuel request manipülasyonu

## 🔑 Şifre Saldırı Araçları

### John the Ripper
```bash
# Hash dosyasını kırma
john hash.txt

# Wordlist ile kırma
john --wordlist=wordlist.txt hash.txt
```

### Hashcat
```bash
# MD5 hash kırma
hashcat -m 0 hash.txt wordlist.txt

# WPA/WPA2 handshake kırma
hashcat -m 2500 capture.hccapx wordlist.txt
```

## 🔎 Forensic Araçları

### Autopsy
- Disk imajı analizi
- Silinen dosyaları kurtarma
- Zaman çizelgesi analizi
- Keyword araması

### Volatility
```bash
# RAM imajı analizi
volatility -f ram.dump imageinfo

# Çalışan prosesleri listeleme
volatility -f ram.dump --profile=Win7SP1x64 pslist
```

## 💡 İpuçları ve Güvenlik Notları

1. Tüm testler sadece izin verilen sistemlerde yapılmalıdır yoksa iyi şeyler olmaz.
2. Test öncesi gerekli yasal izinler alınmalıdır illegal hiç bir şeyi desteklemiyorum.
3. Sisteminizi güncel tutun kendinizi her zaman koruma altına alın.
4. Güvenli parola politikaları uygulayın, güçlü parolalar kullanın
5. Düzenli yedekleme yapın ve cihazınızın yazılım versiyonlarını her zaman güncel tutun.

## 📚 Faydalı Kaynaklar
Bu kaynakları kullanabilirsiniz. Ben de çoğu zaman bakıyorum :)

- [Kali Linux Resmi Dokümantasyon](https://www.kali.org/docs/)
- [OWASP](https://owasp.org/)
- [Exploit Database](https://www.exploit-db.com/)
- [Hack The Box](https://www.hackthebox.eu/)
- [TryHackMe](https://tryhackme.com/)

## ⚠️ Yasal Uyarı
 
Bu dokümanda yer alan bilgiler sadece eğitim amaçlıdır. Bu araçların kötüye kullanımından doğacak sorumluluklar kullanıcıya aittir. Ben sorumlu değilim. Sadece eğitim amaçlı kullanın kimse   sorun yaşamasın.


---
*Son Güncelleme: 2025-03-30*
