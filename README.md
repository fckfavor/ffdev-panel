<div align="center">

# FF.DEV Xray Panel

**Router ve Linux cihazlar icin hafif, web tabanli Xray yonetim paneli**

[![Release](https://img.shields.io/github/v/release/fckfavor/ffdev-panel?style=flat-square&color=4f46e5&label=Son%20Surum)](https://github.com/fckfavor/ffdev-panel/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/fckfavor/ffdev-panel/total?style=flat-square&color=059669&label=Indirme)](https://github.com/fckfavor/ffdev-panel/releases)

</div>

---

## Ozellikler

- Vless / VMess / Trojan profil ekleme ve yonetimi
- Abonelik (subscription) desteği
- TProxy / TUN modu
- Geoip & Geosite guncelleme
- Panel uzerinden tek tikla otomatik guncelleme
- Tum mimari desteği: aarch64, armv7, mipsle, mips, amd64

---

## Kurulum

> Once mimarinizi belirleyin ve asagidan ilgili blogu kopyalayip calistirin.

---

### aarch64 — Modern router / ARM64 Linux
*(MediaTek, BCM, Qualcomm yeni nesil)*

```sh
mkdir -p /data/xray/bin /data/xray/profiles /data/xray/subs /data/xray/logs
chmod -R 755 /data/xray

wget -O /data/xray/ffdev-panel \
  https://github.com/fckfavor/ffdev-panel/releases/latest/download/ffdev-panel-aarch64

chmod +x /data/xray/ffdev-panel
/data/xray/ffdev-panel &
```

---

### armv7 — Eski ARM router
*(32-bit ARM, armv7l)*

```sh
mkdir -p /data/xray/bin /data/xray/profiles /data/xray/subs /data/xray/logs
chmod -R 755 /data/xray

wget -O /data/xray/ffdev-panel \
  https://github.com/fckfavor/ffdev-panel/releases/latest/download/ffdev-panel-armv7

chmod +x /data/xray/ffdev-panel
/data/xray/ffdev-panel &
```

---

### mipsle — MIPS Little Endian router
*(TP-Link, Netgear, D-Link MIPS LE)*

```sh
mkdir -p /data/xray/bin /data/xray/profiles /data/xray/subs /data/xray/logs
chmod -R 755 /data/xray

wget -O /data/xray/ffdev-panel \
  https://github.com/fckfavor/ffdev-panel/releases/latest/download/ffdev-panel-mipsle

chmod +x /data/xray/ffdev-panel
/data/xray/ffdev-panel &
```

---

### mips — MIPS Big Endian router

```sh
mkdir -p /data/xray/bin /data/xray/profiles /data/xray/subs /data/xray/logs
chmod -R 755 /data/xray

wget -O /data/xray/ffdev-panel \
  https://github.com/fckfavor/ffdev-panel/releases/latest/download/ffdev-panel-mips

chmod +x /data/xray/ffdev-panel
/data/xray/ffdev-panel &
```

---

### amd64 — x86_64 Linux sunucu

```sh
mkdir -p /data/xray/bin /data/xray/profiles /data/xray/subs /data/xray/logs
chmod -R 755 /data/xray

wget -O /data/xray/ffdev-panel \
  https://github.com/fckfavor/ffdev-panel/releases/latest/download/ffdev-panel-amd64

chmod +x /data/xray/ffdev-panel
/data/xray/ffdev-panel &
```

---

## Panel Arayuzu

Kurulumdan sonra tarayicidan acin:

```
http://[CIHAZ-IP]:1010
```

---

## Guncelleme

**Panel arayuzunden:** Ayarlar → Panel Guncelle butonu ile otomatik yapilir.

**Manuel guncelleme** (mimarinize gore URL'i degistirin):

```sh
kill $(cat /tmp/ffdev_panel.pid 2>/dev/null) 2>/dev/null || true

wget -O /data/xray/ffdev-panel.new \
  https://github.com/fckfavor/ffdev-panel/releases/latest/download/ffdev-panel-aarch64

chmod +x /data/xray/ffdev-panel.new
mv /data/xray/ffdev-panel.new /data/xray/ffdev-panel
/data/xray/ffdev-panel &
```
