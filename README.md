# FF.DEV Xray Panel

Router ve Linux cihazlar icin web tabanli xray yonetim paneli.

Tarayicidan baglanip vless/vmess/trojan profillerini yukleyebilir, xray'i baslatip durdurabilir, abonelik ekleyebilirsiniz.

---

## Indirme & Kurulum

**Mimari secin:**

| Dosya | Cihaz |
|-------|-------|
| `ffdev-panel-aarch64` | Modern router / ARM64 Linux |
| `ffdev-panel-armv7` | Eski ARM router (armv7) |
| `ffdev-panel-mipsle` | TP-Link, Netgear (MIPS LE) |
| `ffdev-panel-mips` | MIPS BE router |
| `ffdev-panel-amd64` | x86_64 Linux sunucu |

```sh
# Mimariyi degistirin (aarch64 / armv7 / mipsle / mips / amd64)
ARCH=aarch64

wget -O /data/xray/ffdev-panel \
  https://github.com/fckfavor/ffdev-panel/releases/latest/download/ffdev-panel-${ARCH}

chmod +x /data/xray/ffdev-panel
/data/xray/ffdev-panel &
```

Panel acildiktan sonra: **http://[ROUTER-IP]:1010**

---

## Guncelleme

Panel arayuzunden **Ayarlar → Panel Guncelle** ile tek tikla guncelleyebilirsiniz.

Manuel guncelleme:
```sh
kill $(cat /tmp/ffdev_panel.pid 2>/dev/null) 2>/dev/null || true
ARCH=aarch64
wget -O /data/xray/ffdev-panel.new \
  https://github.com/fckfavor/ffdev-panel/releases/latest/download/ffdev-panel-${ARCH}
chmod +x /data/xray/ffdev-panel.new
mv /data/xray/ffdev-panel.new /data/xray/ffdev-panel
/data/xray/ffdev-panel &
```
