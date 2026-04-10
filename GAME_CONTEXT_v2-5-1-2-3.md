# GAME CONTEXT — LaFamilia
> v2.5.1.2.3 | Platform: React Native (iOS + Android) | Portrait only
> Canonical source of truth. Tüm prototype ve dosyalar buna göre senkronize edilir.

---

## TEKNİK KURALLAR

```
Platform        : React Native (Expo → bare RN)
Yönelim         : Portrait only
Dil             : İngilizce (UI metinleri UPPERCASE)
Arka plan       : #ffffff
Vurgu           : #111111
Altın           : #C9A84C / #B8860B
Tier renkleri   : T1:#888 T2:#22c55e T3:#3b82f6 T4:#a855f7 T5:#C9A84C
```

### React Native Geçiş Notları (Prototype → RN)
```
Prototype'ta kullanılan          →  React Native karşılığı

localStorage                     →  AsyncStorage (@react-native-async-storage)
  lf_tut_done                        AsyncStorage.setItem / getItem
  lf_music
  lf_sfx

Audio / new Audio()              →  expo-av (Audio.Sound)
  smPlayMusic()                      sound.loadAsync() + sound.playAsync()
  smPlaySfx()                        sound.replayAsync()
  loop: true                         isLooping: true
  volume                             setVolumeAsync()

document.addEventListener        →  TouchableOpacity / Pressable onPress
CSS :active transform            →  Animated.spring veya react-native-reanimated
CSS animation / @keyframes       →  Animated API veya Reanimated
position:fixed                   →  position:'absolute' + Modal
overflow:hidden scroll           →  ScrollView / FlatList
innerHTML                        →  State + JSX render

Canvas (matrix efekti)           →  react-native-canvas veya SVG animasyon
D3 / TopoJSON harita             →  react-native-svg + custom projection
```

### Sunucu & Chat Altyapısı (React Native geçişinde kurulacak)
```
SUNUCU ŞARTLARI:
- Dünyanın her yerine düşük gecikmeyle erişilebilmeli
- Ücretli olabilir — performans öncelikli
- Önerilen: Cloudflare Workers + dedicated VPS kombinasyonu
  veya AWS / Google Cloud (global edge lokasyonları var)
- Minimum: 4GB RAM, 2 CPU, sınırsız bant genişliği
- İşletim sistemi: Ubuntu 22.04

CHAT ALT YAPISI:
- Global/Server/Aile chat için Socket.io + Node.js
- Gerçek zamanlı, düşük gecikme
- Her server = ayrı Socket.io namespace
- Global chat: son 100 mesaj tutulur, eskisi düşer
- Aile chat: max 100 kişi, hafif
- Küfür filtresi backend'de de çalışmalı

GLOBAL DAĞITIM İÇİN SEÇENEKLER:
- AWS (us-east + eu-west + ap-southeast) — pahalı ama en güvenilir
- Hetzner (Nürnberg + Helsinki + Ashburn) — ucuz, Avrupa/ABD güçlü
- Vultr / DigitalOcean — orta fiyat, 20+ lokasyon

NOT: Sunucu seçimi React Native geçişinde netleşecek.
     Önce oyun tamamlanır, sonra altyapı kurulur.
```

---

## ASSET İSİMLENDİRME KURALI
```
✅ TÜM asset dosya isimleri TÜRKÇE olacak
❌ İngilizce dosya ismi kullanılmayacak
✅ BASE_URL: https://mericaltinors1983-max.github.io/LaFamilia/
❌ hustler reposu artık kullanılmıyor
```

---

## ASSETS

```
BASE_URL = 'https://mericaltinors1983-max.github.io/LaFamilia/'
```

Tüm PNG, GIF, MP3 asset'leri bu repoya yüklenir ve BASE_URL üzerinden çekilir.

### Fontlar
```
CorleoneDue     : CorleoneDue-Wp8v.ttf   (ana başlık)
Cinzel          : Google Fonts            (popup başlık)
Bebas Neue      : Google Fonts            (sayılar)
Oswald          : Google Fonts            (gövde metin)
Space Mono      : Google Fonts            (etiket)
```

### Rank Hayvanları
```
rank_animal_1.png   Fare
rank_animal_2.png   Tavşan
rank_animal_3.png   Tilki
rank_animal_4.png   Maymun
rank_animal_5.png   Yaban Domuzu
rank_animal_6.png   Yılan
rank_animal_7.png   Kobra
rank_animal_8.png   Kurt
rank_animal_9.png   Köpekbalığı
rank_animal_10.png  Çita
rank_animal_11.png  Timsah
rank_animal_12.png  Kaplan
rank_animal_13.png  Kartal
rank_animal_14.png  Aslan
```

### UI İkonları
```
close_icon.png      icon_info.png       lafamilia_logo.png
splash_aim.png      stat_can.png        stat_def.png
stat_xp.png         stat_ks.png         stat_money.png
icon_ammofab.png    back_btn.png        megaphone.png
nav_karakter.png    nav_envanter.png    nav_aile.png
nav_etkinlik.png    nav_mesaj.png       nav_bildirim.png
nav_ayarlar.png     nav_banka.png       nav_kumarhane.png
nav_binalar.png     nav_harita.png      nav_aktivite.png
nav_satinal.png     nav_gazete.png      nav_yaris.png
nav_mermifab.png    nav_suc.png
```

### Alt Bar GIF'leri
```
gif_offender.gif    gif_wheelman.gif    gif_insidejob.gif
gif_armedrob.gif    gif_felony.gif      gif_bustout.gif
gif_kaçakçılık.gif  gif_poligon.gif
```

### Ülke Bayrakları
```
country_turkey.png   country_usa.png      country_russia.png
country_italy.png    country_mexico.png   country_china.png
country_germany.png  country_colombia.png country_japan.png
country_brazil.png
```

### Şehir İkonları (40 adet)
```
city_istanbul.png    city_izmir.png       city_diyarbakir.png  city_trabzon.png
city_napoli.png      city_sicilya.png     city_milano.png      city_roma.png
city_newyork.png     city_chicago.png     city_lasvegas.png    city_miami.png
city_moskova.png     city_stpetersburg.png city_kazan.png      city_vladivostok.png
city_medellin.png    city_bogota.png      city_cali.png        city_cartagena.png
city_mexicocity.png  city_guadalajara.png city_tijuana.png     city_monterrey.png
city_tokyo.png       city_osaka.png       city_kyoto.png       city_yokohama.png
city_sanghay.png     city_hongkong.png    city_pekin.png       city_shenzhen.png
city_berlin.png      city_hamburg.png     city_munih.png       city_frankfurt.png
city_rio.png         city_saopaulo.png    city_salvador.png    city_fortaleza.png
```

### Bina İkonları
```
bina_airport.png     bina_port.png        building_gar.png     bina_bank.png
building_hapishane.png  building_casino.png  bina_ammofab.png  bina_lab.png
building_otel.png    building_bira_fab.png  building_bar.png  icon_mall.png
building_hastane.png  bina_whiskey.png    bina_diamond.png     bina_gold.png
bina_tobacco.png     bina_drone.png       bina_pharmacy.png    bina_chip.png
building_gym.png     building_gazete.png  icon_pawn.png
```

### Müzik & SFX
```
music_main.mp3       music_casino.mp3     music_buildings.mp3
sfx_click.mp3        sfx_success.mp3      sfx_fail.mp3
sfx_rankup.mp3       sfx_kill.mp3         sfx_money.mp3
```

---

## UI / APP SHELL

### Layout
```
┌─────────────────────────────────────┐
│   TopBar (44px) — Stats             │
├─────────────────────────────────────┤
│   TopNav Sıra 1 (42px) — 8 ikon    │
│   TopNav Sıra 2 (42px) — 8 ikon    │
├─────────────────────────────────────┤
│   Orta Ekran (MainContent)          │
├─────────────────────────────────────┤
│   BottomBar (64px) — 8 GIF ikon    │
└─────────────────────────────────────┘
```

TopBar + TopNav + BottomBar şu ekranlarda GİZLENİR:
- Ölüm ekranı
- Hapis ekranı
- Tutorial
- Safe House

### TopBar (44px)
```
Sol   : rank_animal PNG (26px) | CAN bar | DEF bar | XP bar | KS bar
Sağ   : para ($) | mermi | şehir ikonu
Orta  : Ticker — kayan gazete metni
```

Bar gösterimi: mevcut / max × 100 = %
- CAN % = mevcut can / o rankın max canı
- DEF % = mevcut defence / 60.000
- XP %  = mevcut xp / sonraki rank xp eşiği
- KS %  = KS değeri / 100

### TopNav Sıra 1
```javascript
const TOP_NAV_1 = [
  { id:'karakter',  png:'nav_karakter.png',  screen:'karakter'  },
  { id:'envanter',  png:'nav_envanter.png',  screen:'envanter'  },
  { id:'binalar',   png:'nav_binalar.png',   popup:'binalar'    },
  { id:'harita',    png:'nav_harita.png',    screen:'ulkeler'   },
  { id:'mesaj',     png:'nav_mesaj.png',     popup:'mesaj',  badge:true },
  { id:'bildirim',  png:'nav_bildirim.png',  popup:'bildirim', badge:true },
  { id:'etkinlik',  png:'nav_etkinlik.png',  popup:'etkinlik'   },
  { id:'ayarlar',   png:'nav_ayarlar.png',   popup:'ayarlar'    },
];
```

### TopNav Sıra 2
```javascript
const TOP_NAV_2 = [
  { id:'aile',      png:'nav_aile.png',      screen:'family'    },
  { id:'suc',       png:'nav_suc.png',       popup:'suc'        },
  { id:'banka',     png:'nav_banka.png',     popup:'banka'      },
  { id:'kumarhane', png:'nav_kumarhane.png', screen:'casino'    },
  { id:'aktivite',  png:'nav_aktivite.png',  popup:'aktivite'   },
  { id:'yaris',     png:'nav_yaris.png',     screen:'yaris'     },
  { id:'satinal',   png:'nav_satinal.png',   popup:'satinal'    },
  { id:'gazete',    png:'nav_gazete.png',    popup:'gazete'     },
];
// grid-template-columns: repeat(8, 1fr) | her sıra 42px | ikon 20px
```

### BottomBar (64px) — GIF ikonlar
```javascript
const BOTTOM_BTNS = [
  { id:'offender',   gif:'gif_offender.gif',  popup:'offender'   },
  { id:'armedrob',   gif:'gif_armedrob.gif',  popup:'armedrob'   },
  { id:'wheelman',   gif:'gif_wheelman.gif',  popup:'wheelman'   },
  { id:'insidejob',  gif:'gif_insidejob.gif', popup:'insidejob'  },
  { id:'felony',     gif:'gif_felony.gif',    popup:'felony'     },
  { id:'bustout',    gif:'gif_bustout.gif',   popup:'bustout'    },
  { id:'kacakcilik', gif:'gif_kacakcilik.gif',popup:'kacakcilik' },
  { id:'poligon',    gif:'gif_poligon.gif',   popup:'poligon'    },
];
```

### Tam Ekran Açılanlar (Orta ekranda, bar'lar gizlenmez)
```
family | casino | map | karakter | envanter | araba_yarisi
```

### Popup Açılanlar (Standart popup kuralıyla)
Yukarıdaki listeler dışındaki her şey popup olarak açılır.

---

## POPUP STANDARDI

### Konum & Boyut
```css
position: fixed;
bottom: 116px;
left: 50%;
transform: translateX(-50%);
width: 320px;
height: 520px;
background: #fff;
border: 1.5px solid #C9A84C;
border-bottom: none;
overflow: hidden;
z-index: 10001;
```

### Overlay
```css
position: fixed; inset: 0;
background: rgba(0,0,0,0.65);
z-index: 10000;
/* tıklanınca popup kapanır */
```

### Açılış Animasyonu
```
Suç popupları (Offender/Wheelman/Inside Job/Armed Rob/Felony/Bustout/Kaçakçılık/Poligon):
Suç popupları (Offender/Wheelman/Inside Job/Armed Rob/Felony/Bustout/Kaçakçılık/Poligon):
  → Matrix efekti: Her suç popupunun KENDİ canvas'ı var (global matrixEffect KALDIRILDI)
  → ŞEFFAF canvas, BEYAZ karakterler, 700ms
  → Popup boyutunda (320×520px), bottom:116px, ortada
  → Çerçeve YOK
  → Ardından popup fade+scale ile belirir (alttan kayma YOK)

  CLOSE BUTONU — TÜM SUÇ POPUPLARI (of/wm/ar/ij/fe/bu/kc/po):
  ❌ close_icon.png KULLANILMAZ — sağ üstte X butonu YOK
  ✅ btn_close_bar.png — YALNIZCA popup ALT ORTASINDA — height:36px
  ✅ close bar, popup div'inin IÇINDE, en altta yer alır

  FELONY İSTİSNASI (minimize):
  → Alt bar 2 parçalı: sol=btn_minimize_bar.png | sağ=btn_close_bar.png

  FLOAT ANİMASYONLARI (tüm suçlarda):
  → Başlangıç: window.innerHeight - 210px (popup sonuç alanı)
  → Sol: window.innerWidth/2 - 60px
  → Yukarı kayar, 1.65sn, sırayla (XP turuncu, para yeşil, KS kırmızı, sürüş mavi)

  ANA EKRAN PNG HİZALAMASI:
  → İç wrapper: display:flex; flex-direction:column; align-items:center; width:100%; text-align:center

Diğer tüm popuplar:
  → Açık siyah skeleton shimmer (koyu gri tonlar, 1.1sn) → içerik belirir
  → Ardından içerik belirir
```

### Header (64px)
```
Sol   : o popupın GIF'i — her popup için değişir (35px)
Orta  : lafamilia_logo.png — SABİT (absolute centered, 54px yükseklik)
Sağ   : icon_info.png + close_icon.png — SABİT (her biri 28px)
Alt   : border-bottom: 1.5px solid #111
```
Bina popuplarında sol ikon = o binanın PNG'si

❌ SUÇ POPUPLARINDA HEADER YOKTUR:
Offender / Wheelman / Armed Robbery / Inside Job / Felony / Bustout / Kaçakçılık / Poligon
→ Header div YOK | GIF/PNG header'da YOK | lafamilia_logo header'da YOK
→ icon_info.png header'da YOK | close_icon.png header'da YOK
→ Suç popupları tam ekran içerik + ALT CLOSE BAR ile çalışır

### Close Bar (50px)
```css
border-top: 1.5px solid #111;
background: #fff;
içerik: btn_close_bar.png — SABİT, tüm popuplarda aynı PNG, height:36px
```

### Buton PNG Boyutları (SABİT)
```
btn_close_bar.png : height 36px  — tüm popupların alt close bar'ı
btn_ok.png        : height 52px  — sonuç/hapis ekranı onay butonu
```

### PNG Fallback Kuralı (ZORUNLU)
Her PNG/GIF için mutlaka fallback yazılır. PNG yüklenemezse görünürlük bozulmasın.
```html
<!-- Örnek fallback — her img tagine uygulanır -->
<img src="BASE_URL/dosya.png"
     style="height:36px;object-fit:contain;"
     onerror="this.outerHTML='<span style=\'font-family:Oswald,sans-serif;font-weight:700;color:#B8860B;\'>KAPAT</span>'">

<!-- GIF fallback -->
<img src="BASE_URL/gif_wheelman.gif"
     onerror="this.style.display='none'">

<!-- PNG fallback emoji -->
<img src="BASE_URL/rank_animal_7.png"
     onerror="this.outerHTML='<span style=\'font-size:40px\'>🐍</span>'">
```
// Kural: Her img taginde onerror ZORUNLUDUR. Fallback metni veya emoji olabilir.

### Popup Border
```css
border: 1.5px solid #C9A84C;   /* sarı */
border-bottom: none;
```

### Buton Standartı
```css
/* Primary */
background: #fff; color: #C9A84C;
border: 1.5px solid #C9A84C;
height: 44px; font: Oswald 700 14px; letter-spacing: 2px;

/* Press Down efekti */
:active { transform: scale(0.97) translateY(1px); }

/* Secondary */
background: #fff; color: #111;
border: 1.5px solid #ddd;
```

### Font & Renk Standartı
```
// 12 yazı türü — tüm popuplarda bu standart geçerlidir

Hero başlık        : Oswald 700 22px #C9A84C letter-spacing:2px   (TOP SPENDER, popup ana başlık)
Ekran başlığı      : Bebas Neue 26px #111 letter-spacing:3px       (WHEELMAN, OFFENDER gibi)
Bölüm etiketi      : Oswald 700 13px #B8860B letter-spacing:1.5px  (AYLIK SIRALAMA, REWARD gibi)
Stat etiketi       : Oswald 600 11px #888 letter-spacing:1px       (COOLDOWN, XP, SUCCESS gibi)
Büyük değer        : Bebas Neue 24px #111                          (sayılar, para değerleri)
Normal değer/isim  : Oswald 700 14px #111                          (oyuncu isimleri, row değerleri)
Altın değer        : Oswald 700 16px #C9A84C                       (timer, harcama tutarı, özel vurgu)
Alt metin/sub      : Oswald 600 12px #C9A84C                       ("bu ay toplam harcama", "$99.99 harcandı")
İtalik flavor      : Oswald 400 italic 13px #888                   (tırnak içi metinler)
Buton yazısı       : Oswald 700 14px letter-spacing:2px
Close bar          : Oswald 700 12px #B8860B letter-spacing:2px
Not/dipnot         : Oswald 600 11px #888 line-height:1.6

Sekme aktif        : color:#111 border-bottom:2px solid #111
Sekme pasif        : color:#999
Yeşil              : #2a7a3a  (başarılı/iyi)
Altın              : #C9A84C / #B8860B
Kırmızı            : #c62828  (tehlike/kayıp)
```

### Float Efektleri (işlem sonrası sırayla yukarı kalkar)
```javascript
const FLOAT_COLORS = {
  para:     '#2a7a3a',   // yeşil
  xp:       '#f97316',   // turuncu
  ks:       '#c62828',   // kırmızı
  defence:  '#111111',   // siyah
  suruş:    '#3b82f6',   // mavi
  bustout:  '#C9A84C',   // sarı
};
// Sırayla çıkar — biri bitmeden diğeri başlamaz
```

---

## SPLASH SCREEN

```
1. Beyaz arka plan
2. lafamilia_logo.png ortada belirir
3. Altın çizgi
4. "Mafia Game" typewriter efektiyle yazılır (CorleoneDue font)
5. "WORLD IS YOURS" soluklaşarak çıkar
6. 3.5 saniye sonra → Giriş/Kayıt ekranına geçer
```

---

## KAYIT & GİRİŞ EKRANI

### Kayıt Akışı
```
1. Dil seçimi (9 dil)
2. Nick gir
3. Mail gir
4. Şifre gir
5. Şehir seç (10 ülke → 40 şehir)
6. Kayıt ol → Tutorial → Oyun
```

### Giriş Ekranı
```
- Logo
- Nick + Şifre
- Şifremi Unuttum (mail ile sıfırlama — backend)
- Bize Yazın butonu
- SSS/FAQ butonu
- Oyun adresi
```

### Dil Seçenekleri
```
İngilizce · Türkçe · Almanca · İspanyolca · Portekizce-BR
Rusça · Japonca · Çince · Fransızca
```
Settings'ten sonradan değiştirilebilir.

### Yeni Oyuncu
```
- Başlangıç parası: $10.000
- 5 gün koruma: öldüremez, öldürülemez. Saldırırsa anında kalkar.
- Tutorial otomatik başlar
```

### Server Seçimi
```
- Tüm serverlar listelenir
- Dolu server: kırmızı | Müsait: yeşil
- Oyuncu seçer
- Server 1: reklam yok | Server 2+: reklam açık
```
---

## HARİTA

### 3 Katman
```
Katman 1 — Dünya   : D3 NaturalEarth1 projeksiyonu, 10 ülke renkli
Katman 2 — Ülke    : Şehirler Voronoi ile aile bölgelerine ayrılır
                     Bölge aile rengiyle boyanır, şehir + aile adı overlay
Katman 3 — Şehir   : Binalar PNG + isim, bina tıklayınca popup
```

Harita tam ekran açılır. Ülkeye/şehire tıklanınca GIF bir kez oynar, sonra içerik açılır.

### Ülke Renkleri
```javascript
const COUNTRY_COLORS = {
  turkey:   '#E30A17', italy:    '#009246', germany:  '#FFCC00',
  russia:   '#003DA5', china:    '#DE2910', japan:    '#BC002D',
  usa:      '#3C3B6E', mexico:   '#006847', brazil:   '#009C3B',
  colombia: '#FCD116',
};
```

### 10 Ülke — 40 Şehir
```javascript
const COUNTRY_DATA = [
  { id:'turkey',   cities:[
    { id:'istanbul',    liman:true  },
    { id:'izmir',       liman:true  },
    { id:'diyarbakir'               },
    { id:'trabzon',     liman:true  },
  ]},
  { id:'italy',    cities:[
    { id:'napoli',   liman:true, ozel_banka:true   },
    { id:'sicilya',  liman:true, ozel_casino:true  },
    { id:'milano'                                   },
    { id:'roma',     liman:true                    },
  ]},
  { id:'usa',      cities:[
    { id:'newyork',  liman:true, ozel_mermi:true, ozel_liman:true, ozel_casino:true },
    { id:'chicago',  liman:true, ozel_mermi:true  },
    { id:'lasvegas',              ozel_casino:true },
    { id:'miami',    liman:true, ozel_airport:true },
  ]},
  { id:'russia',   cities:[
    { id:'moskova'                               },
    { id:'stpetersburg', liman:true             },
    { id:'kazan'                                },
    { id:'vladivostok',  liman:true, ozel_altin:true },
  ]},
  { id:'colombia', cities:[
    { id:'medellin', ozel_lab:true },
    { id:'bogota'                  },
    { id:'cali'                    },
    { id:'cartagena', liman:true   },
  ]},
  { id:'mexico',   cities:[
    { id:'mexicocity',  ozel_mermi:true },
    { id:'guadalajara'                  },
    { id:'tijuana',     liman:true      },
    { id:'monterrey'                    },
  ]},
  { id:'japan',    cities:[
    { id:'tokyo',    liman:true },
    { id:'osaka',    liman:true },
    { id:'kyoto'               },
    { id:'yokohama', liman:true },
  ]},
  { id:'china',    cities:[
    { id:'sanghay',  liman:true, ozel_elmas:true },
    { id:'hongkong', liman:true                  },
    { id:'pekin'                                 },
    { id:'shenzhen', liman:true                  },
  ]},
  { id:'germany',  cities:[
    { id:'berlin'                                       },
    { id:'hamburg', liman:true, ozel_liman:true, ozel_bira:true },
    { id:'munih'                                        },
    { id:'frankfurt'                                    },
  ]},
  { id:'brazil',   cities:[
    { id:'rio',      liman:true },
    { id:'saopaulo', liman:true },
    { id:'salvador'             },
    { id:'fortaleza'            },
  ]},
];
```

### Özel Şehir Bonusları
```javascript
const BINA_SPECIAL = {
  medellin_labaratuvar:  { bonus:'3x ÜRETİM'     },
  chicago_mermi_fab:     { bonus:'1.3x ÜRETİM'   },
  mexicocity_mermi_fab:  { bonus:'1.2x ÜRETİM'   },
  newyork_mermi_fab:     { bonus:'1.1x ÜRETİM'   },
  hamburg_bira_fab:      { bonus:'1.5x ÜRETİM'   },
  vladivostok_altin_fab: { bonus:'2x ÜRETİM'     },
  sanghay_elmas_fab:     { bonus:'2x ÜRETİM'     },
  lasvegas_casino:       { bonus:'SINIRSIZ BAHİS' },
  sicilya_casino:        { bonus:'%3 KOMİSYON'   },
  newyork_casino:        { bonus:'%3 KOMİSYON'   },
  newyork_liman:         { bonus:'+%10 SATIŞ'    },
  hamburg_liman:         { bonus:'+%20 SATIŞ'    },
  istanbul_liman:        { bonus:'-%20 SÜRE'     },
  miami_havalimani:      { bonus:'-%25 SÜRE'     },
  napoli_banka:          { bonus:'ÖZEL FAİZ'     },
  japan_drone_fab:       { bonus:'1.2x ÜRETİM'  }, // tüm Japonya drone fabrikaları
};
```

### Mesafe Kategorileri (Kaçakçılık için)
```javascript
// Aynı ülke içi mesafe otomatik hesaplanır (kısa/orta/uzun)
// Ülkeler arası: ic / komsu / ayni_kita / farkli_kita
```

---

## BİNALAR

### Bina Tipleri
```
PUBLIC      : Satın alınamaz, saldırılamaz, soyulamaz. Her zaman çalışır.
THE KITCHEN : Üretim tesisi. Sahip olmadan üretim yapılmaz.
THE FRONT   : Satış/paravan işyeri. Sahip olmadan satış yapılmaz.
```

Sahipsiz bina: üretim durur, satış yapmaz, soyulamaz, sadece satın alınabilir.

### Bina Listesi (22 bina)
```javascript
const BINALAR = [
  // PUBLIC
  { id:'havalimani',     tip:'PUBLIC',      name:'AIRPORT'      },
  { id:'liman',          tip:'PUBLIC',      name:'PORT'         },
  { id:'tren_istasyonu', tip:'PUBLIC',      name:'TRAIN STATION'},
  { id:'banka',          tip:'PUBLIC',      name:'BANK'         },
  { id:'hapishane',      tip:'PUBLIC',      name:'PRISON'       },
  { id:'gazete',         tip:'PUBLIC',      name:'GAZETTE'      },

  // THE KITCHEN
  { id:'mermi_fab',  tip:'KITCHEN', urun:'Mermi',  uretim:2000, fiyat:10000000, rankMin:6  },
  { id:'labaratuvar',tip:'KITCHEN', urun:'White',  uretim:300,  fiyat:9000000,  rankMin:9  },
  { id:'bira_fab',   tip:'KITCHEN', urun:'Bira',   uretim:1000, fiyat:5000000,  rankMin:5  },
  { id:'hastane',    tip:'KITCHEN', urun:'Kan',    uretim:500,  fiyat:6000000,  rankMin:4  },
  { id:'viski_fab',  tip:'KITCHEN', urun:'Viski',  uretim:750,  fiyat:8000000,  rankMin:7  },
  { id:'elmas_fab',  tip:'KITCHEN', urun:'Elmas',  uretim:100,  fiyat:9000000,  rankMin:9  },
  { id:'altin_fab',  tip:'KITCHEN', urun:'Altın',  uretim:200,  fiyat:8000000,  rankMin:8  },
  { id:'sigara_fab', tip:'KITCHEN', urun:'Sigara', uretim:2000, fiyat:5000000,  rankMin:4  },
  { id:'eczane',     tip:'KITCHEN', urun:'Pill',   uretim:500,  fiyat:6000000,  rankMin:4  },
  { id:'drone_fab',  tip:'KITCHEN', urun:'Drone',  uretim:300,  fiyat:7000000,  rankMin:7  },

  // THE FRONT
  { id:'casino',     tip:'FRONT',   name:'CASINO'      },
  { id:'otel',       tip:'FRONT',   name:'HOTEL'       },
  { id:'bar',        tip:'FRONT',   name:'BAR'         },
  { id:'pawn_shop',  tip:'FRONT',   name:'PAWN SHOP'   },
  { id:'gym',        tip:'FRONT',   name:'GYM'         },
  { id:'avm',        tip:'FRONT',   name:'MALL'        },
];
// Oyuncu başına aynı türden MAX 1 Kitchen | Depo sınırı YOK
```

### Bina Puanları (Şehir hakimiyeti için)
```javascript
const BINA_PUAN = {
  mermi_fab:  13,
  casino:     13,
  labaratuvar:11,
  elmas_fab:  9,
  avm:        9,
  // Diğer 9 bina: 5'er puan
  // TOPLAM: 100 puan
};
```

### Gelir Dağılımı
```
Kitchen geliri: %5 şehri kontrol eden aile | %95 sahibe
Front geliri  : %5 şehri kontrol eden aile | %95 sahibe
Sahip ölürse  : bina sahipsiz kalır, aynı fiyatla satışa
```

### Bina Savunma Sistemi
```javascript
// Saldırı → SOY olarak adlandırılır
// Sahipsiz binaya SOY yapılamaz | Public'e SOY yapılamaz

const BINA_SAVUNMA = {
  otomatik_mermi: 30000,  // her soyda ateşlenir
  ks: 'sahip.ks',         // sahibin anlık KS'i kullanılır
  // Sahip ek mermi + BG yükleyebilir
};

// Soy başarılıysa: kasa saldırgana geçer, sahip değişmez
// Soy başarısızsa: kasa sahipte kalır
```

### Şehir Kontrolü
```
Bir aile şehri kontrol etmek için:
1. Mermi Fabrikası
2. Casino
3. 2 pasif gelir binası (Pawn / Bar / Gym / Hotel / Mall)

Kontrol kazanılırsa:
→ Haritada şehir rengi aile rengine döner
→ Tüm Kitchen ve Front binalarından %5 komisyon
→ +%5 savunma bonusu (aile üyelerine)
```

### Bina Popup Mantığı
```
PUBLIC      → Seyahat + Kaçakçılık butonları (transport tiplerine göre)
            → Gazete popup'ı ayrı açılır

KITCHEN (sahipsiz)  → Sadece [BİNAYI AL] + rank/fiyat bilgisi
KITCHEN (başkası)   → [ÜRÜNİ AL] + [SOY ET]
KITCHEN (benim)     → Tab: KASA | MAL | SAVUNMA

FRONT (sahipsiz)    → Sadece [BİNAYI AL]
FRONT (başkası)     → Sadece [SOY ET]
FRONT (benim)       → Tab: KASA | MAL | SAVUNMA

CASINO              → [CASİNO'YA GİR] → casino tam ekran açılır
```

### Gazete
```
- Her şehirde PUBLIC bina olarak var
- TopNav → GAZETE ikonundan da açılır
- Popup olarak açılır (320×520px standart)
- 3 sekme: HABERLER | RÖPORTAJ | GAZETECİ

GAZETECİ MEKANİĞİ:
- Her server'da sadece 1 gazeteci olabilir
- Başvuruyla alınır (GAZETECİ OL butonu)
- Günlük maaş: $50,000
- Haber başına bonus: $10,000
- Röportaj başına bonus: $25,000
- İstediği zaman ayrılabilir

SİSTEM OTO-HABERLERİ (gazeteci olmasa da üretilir):
- Ölüm haberleri
- Jackpot haberleri
- Yeni üye kaydı
- Yeni aile kuruldu
- Online sayısı (ticker badge'e — ayrı haber değil)
Her olay hem Gazete'ye hem Ticker'a düşer.

Admin duyuruları da burada + ticker'da görünür
```
---

## RANK SİSTEMİ

```javascript
const RANKS = [
  { id:1,  name:'Street Rat',  xp:0,        animal:'Fare'          },
  { id:2,  name:'Runner',      xp:1000,      animal:'Tavşan'        },
  { id:3,  name:'Hustler',     xp:3000,      animal:'Tilki'         },
  { id:4,  name:'Crook',       xp:7000,      animal:'Maymun'        },
  { id:5,  name:'Thug',        xp:15000,     animal:'Yaban Domuzu'  },
  { id:6,  name:'Gangster',    xp:30000,     animal:'Yılan'         },
  { id:7,  name:'Enforcer',    xp:60000,     animal:'Kobra'         },
  { id:8,  name:'Operator',    xp:120000,    animal:'Kurt'          },
  { id:9,  name:'Hitman',      xp:250000,    animal:'Köpekbalığı'   },
  { id:10, name:'Underboss',   xp:500000,    animal:'Çita'          },
  { id:11, name:'Strategist',  xp:1000000,   animal:'Timsah'        },
  { id:12, name:'Boss',        xp:2000000,   animal:'Kaplan'        },
  { id:13, name:'Crew Chief',  xp:4000000,   animal:'Kartal', defBonus:0.10 },
  { id:14, name:'Godfather',   xp:8000000,   animal:'Aslan',  defBonus:0.20, noCop:true },
];
```

### Rank Atlama Şartları (RANK_EXTRA)
```javascript
const RANK_EXTRA = {
  '1→2':  { suc:9 },
  '2→3':  { suc:18,  araba:5 },
  '3→4':  { suc:27,  araba:9 },
  '4→5':  { insidejob:1,  mermi:450 },
  '5→6':  { insidejob:3,  mermi:900,   kill:2  },
  '6→7':  { insidejob:5,  mermi:4500,  kill:5  },
  '7→8':  { felony:1,     mermi:9000,  kill:7  },
  '8→9':  { felony:3,     mermi:22500, kill:10 },
  '9→10': { felony:5,     mermi:45000, kill:11 },
  '10→11':{ aile:true,    mermi:90000, kill:12 },
  '11→12':{ mermi:180000, kill:13 },
  '12→13':{ mermi:450000, kill:15 },
  '13→14':{ don:true, mermi:900000, kill:20 },
};
// mermi = lifetime toplam (harcansa düşmez)
```

### Rank Atlama Ekranı
```
- Beyaz arka plan, tüm menüler gizlenir
- Yeni rankın hayvan PNG'si küçükten büyüye gelir (pop animasyonu)
- Altın halkalar yayılır
- Altın konfeti
- Rank adı ve numarası belirir
- [DEVAM ET] butonu
```

---

## STAT SİSTEMLERİ

### XP
```javascript
const XP_TABLE = {
  offender:         50,
  wheelman:         75,
  insidejob:        500,
  armedrob:         800,
  felony:           5000,
  bustout:          100,
  kill_ayni_rank:   1500,
  kill_ust_rank:    1800,
};
// Birikir, azalmaz. Rank atlar.
```

### KS (Killing Skill)
```javascript
const KS_TABLE = {
  insidejob:  0.01,
  armedrob:   0.02,
  felony:     0.05,
  poligon:    0.005,   // 10dk cooldown
  aktivite:   0.10,    // günde max (KS aktivite 2)
  kill_ayni:  0.01,
  kill_ust:   0.02,
};
// Başlangıç: 0 | Birikir, azalmaz | Cap: 100
// KS % = isabet yüzdesi. KS 0 → %0 isabet, KS 100 → %100 isabet
// Isabetsiz mermi SIFIR hasar verir
// Silah/Kolye/Yüzük item bonusu ekstra KS artışı verir
```

### Defence
```javascript
// Toplam max defence: 60.000
// DEF % = mevcut defence / 60.000 × 100

const DEFENCE_KAYNAKLAR = {
  bg:      'tier bazlı (min→max, 100 kafa ile max)',
  yelek:   'tier bazlı',
  suit:    'tier bazlı',
  rank_can:'rank bazlı (Godfather: 10.000)',
  aktivite:'max 10.000 (aktivite ile birikir)',
};

// PvP'de hasar sırası: Suit → Yelek → BG'ler → Can
// Can min 1'e düşer, ölüm olmaz (PvP hariç)
```

### Can (HP) Sistemi
```javascript
// Rank bazlı can değerleri:
const RANK_CAN = {
  1:500, 2:600, 3:700, 4:800, 5:1000,
  6:1500, 7:2000, 8:3000, 9:5000, 10:6000,
  11:7000, 12:8000, 13:9000, 14:10000,
};

// Toplam max can (Godfather, tam donanım):
// 10.000 (rank) + 25.000 (5×T5 BG) + 10.000 (T5 yelek) + 5.000 (T5 suit) + 10.000 (aktivite) = 60.000

// 1 Kan = 1 can iyileştirir
// Hastaneden Kan alınır, envanterde biriktirilir
```

### BG (Bodyguard) Sistemi
```javascript
// 50 farklı BG, her birinden max 1 adet
// 5 slot, her BG kafayla güçlendirilir (max 100 kafa)

const BG_TIERS = {
  T1: { min:100,  max:1000  },
  T2: { min:1000, max:2000  },
  T3: { min:2000, max:3000  },
  T4: { min:3000, max:4000  },
  T5: { min:4000, max:5000  },
};
// defence = min + (kafaSayısı/100) × (max-min)

// Aynı BG tekrar düşerse → o tier'ın 10 kafasına dönüşür
// NPC'den her tier 1 kez satın alınabilir
// 5×T5 BG tam upgrade = 25.000 defence
```

### Item Sistemi
```javascript
const ITEM_ROLLER = {
  celik_yelek: 'defence',   // T1:100→1000 | T5:4000→5000
  suit:        'defence + slot',
  canta:       'slot',
  silah:       'KS artış %',
  kolye:       'KS artış %',
  yuzuk:       'KS artış %',
};

// Dayanıklılık YOK
// NPC satış: alış × 0.50
// T5 altın parlama animasyonu
// Rank min şartları var (T5 için Rank 12-14)
```

### Sürüş Becerisi
```javascript
// Başlangıç: %20 | Birikir, azalmaz
// Yarışa katılınca: +%0.01
// Yarış kazanınca: +%0.05
// Inside Job tamamlanınca (lider): +%0.005
// Efektif hız = arabanın hızı × (sürüş becerisi / 100)
```

### Bustout Becerisi
```javascript
// Bustout başarı oranını BELİRLEYEN tek faktördür (rank avantajı yoktur)
// Başlangıç: %20 | Birikir, azalmaz | Tavan: %90
// Her 5 başarılı bustout: +%1
// Kendini bustout etmede de geçerli
// Başkasını bustout etmede de geçerli
```

---

## AKTİVİTE SİSTEMİ

### Genel Kurallar
```
- Günde max 5 saat aktivite
- Bir aktivite aktifken diğeri başlatılamaz
- Aktiviteler sırayla açılır (önceki tamamlanmadan sonraki açılmaz)
- Her aktivite 25 saat tamamlanınca sonraki açılır
```

### Aktivite Popup
```
3 büyük buton:
1. MESLEK ($)      → para aktiviteleri popup'ı
2. UPGRADE (KS+DEF)→ KS ve defence aktiviteleri popup'ı
3. YARIŞ (araba)   → araba yarışı tam ekran açılır
```

### Para Aktiviteleri (6 adet, sırayla açılır)
```javascript
const PARA_AKTIVITELER = [
  { id:'para_1', rewardPh:5   },
  { id:'para_2', rewardPh:12  },
  { id:'para_3', rewardPh:25  },
  { id:'para_4', rewardPh:50  },
  { id:'para_5', rewardPh:75  },
  { id:'para_6', rewardPh:100 },
]; // $/saat
```

### Defence Aktiviteleri (4 adet, sırayla açılır)
```javascript
const DEF_AKTIVITELER = [
  { id:'def_1', rewardPh:50  },
  { id:'def_2', rewardPh:75  },
  { id:'def_3', rewardPh:100 },
  { id:'def_4', rewardPh:175 },
]; // defence/saat | Toplam max: 10.000
// Defence 10.000'e ulaşınca aktiviteden defence kazanılmaz
```

### KS Aktiviteleri (2 adet, sırayla açılır)
```javascript
// KS Aktivite 1: Def Aktivite 4 tamamlanınca açılır
// KS Aktivite 2: KS Aktivite 1 tamamlanınca açılır
const KS_AKTIVITELER = [
  { id:'ks_1', reward:0.05  }, // 5 saat sonunda toplam
  { id:'ks_2', reward:0.10  }, // 5 saat sonunda toplam
];
// Günde 1 KS aktivitesi yapılabilir
```
---

## SUÇLAR

### Genel Kurallar
```
- Başarı şansı var, başarısız olunca hapse düşülür
- Başarısız olunca da XP kazanılır (hapis XP'si yok — sadece suç XP'si)
- Cooldown başarılı veya başarısız fark etmez, sabittir
- Hapse düşünce: kefalet öde | kendini bustout et (max 3 hak) | başkası kurtarsın
```

### Suç Tablosu
```javascript
const SUCLAR = {
  offender: {
    cooldown: 5,        // dakika
    xp:       50,
    para:     { r1_5:'$10–$50', r6_10:'$100–$500', r11_14:'$500–$2.000' },
    hapis:    { r1_5:30, r6_10:60, r11_14:120 },   // saniye
    kefalet:  { r1_5:100, r6_10:500, r11_14:1000 },
    basari:   { 1:.20, 2:.25, 3:.31, 4:.36, 5:.42, 6:.47, 7:.52, 8:.58, 9:.63, 10:.68, 11:.74, 12:.79, 13:.85, 14:.90 },
  },
  wheelman: {
    cooldown: 30,
    xp:       75,
    odul:     'araba (tier bazlı)',
    hapis:    { r1_5:60, r6_10:120, r11_14:180 },
    kefalet:  { r1_5:500, r6_10:2000, r11_14:5000 },
  },
  insidejob: {
    cooldown: 30,
    xp:       500,
    ks:       0.01,
    suruş:    0.005,   // lider için (başarılıda)
    para:     { r1_5:'$500–$2K', r6_10:'$2K–$8K', r11_14:'$8K–$20K' },
    hapis:    { r1_5:180, r6_10:300, r11_14:480 },
    kefalet:  { r1_5:2000, r6_10:8000, r11_14:15000 },
    basari:   { 1:.05, 2:.10, 3:.15, 4:.20, 5:.25, 6:.30, 7:.35, 8:.40, 9:.45, 10:.50, 11:.55, 12:.60, 13:.65, 14:.70 },
  },
  armedrob: {
    cooldown: 15,       // dakika = 900 saniye
    xp:       200,
    ks:       0.01,
    para:     { r1_5:'$1K–$5K', r6_10:'$5K–$15K', r11_14:'$15K–$40K' },
    hapis:    { r1_5:120, r6_10:240, r11_14:300 },
    kefalet:  { r1_5:8000, r6_10:20000, r11_14:35000 },
    item_drop: true,
    basari:   { 1:.15, 2:.20, 3:.26, 4:.31, 5:.37, 6:.42, 7:.48, 8:.53, 9:.59, 10:.64, 11:.69, 12:.75, 13:.80, 14:.85 },
  },
  felony: {
    cooldown: 720,      // 12 saat = 43200 saniye
    xp:       3000,
    ks:       0.05,
    rankMin:  8,
    hapis:    { r8:240, r9:300, r10:360, r11:480, r12:600, r13:900, r14:1200 },
    kefalet:  { r8_10:30000, r11_14:50000 },
    item_drop: true,
    // BAŞARI ORANI formül bazlı — sabit tablo YOK
    // baz: R8:50 R9:53 R10:57 R11:65 R12:68 R13:75 R14:80
    // + nişancı KS/100×10 (her nişancı) + 2.nişancı:+5
    // + sürüş/100×15 + TNT:+3
    // SONUÇ SİSTEMİ:
    // 1. Her felony → para kazanılır (oran bazlı, başarısız/başarılı fark yok)
    // 2. Sonra ayrı %30 hapis zar atılır:
    //    %30 → para kazandılar ama yakalandılar → hapis → bustout
    //    %70 → kaçtılar, temiz
    // ≥130 → garantili para $6M+ | ≥140 → $10M + item %100
  },
  bustout: {
    cooldown: 0,        // cooldown yok
    xp:       100,
    bustout_beceri: true,
    hapis_basarisiz: { r1_5:60, r6_10:120, r11_14:180 },
    kefalet_basarisiz: { r1_5:100, r6_10:1000, r11_14:3000 },
  },
};
```

### Bustout Sistemi
```javascript
// BAŞARI ORANI = bustout_becerisi (rank tablosu YOKTUR)
// Başlangıç: %20 | Tavan: %90
// Her 5 başarılı bustout: +%1
// Kendini bustout etmede de geçerli
// Başkasını bustout etmede de geçerli

// Başarısız her denemede hapis süresi + kefalet artar
// Max 3 hak, bittikten sonra buton kaybolur
// Başkasını bustout etmek: başarısız → kurtarıcı da hapse düşer
```

### Kendini Bustout Etme
```
- Hapisteyken kendini bustout etmeyi deneyebilirsin
- Max 3 hak
- Her başarısız denemede hapis süresi + kefalet artar
- 3 hak bittikten sonra buton kaybolur
- Bustout becerisi burada da geçerli
```

### Bustout Detayları
```
BASE_URL = https://mericaltinors1983-max.github.io/LaFamilia/

POPUP (prefix: bu-) — matrix 700ms → şeffaf popup → bottom:116px sabit

HEADER: YOK — close_icon.png KULLANILMAZ
CLOSE : btn_close_bar.png — ALT ORTADA — popup div'i içinde — onclick: bu_close()

EKRAN 1 — SC-LIST (başkasını kurtarma):
  prisoner.png (120×120) üstte ortalı + "BUST OUT" yazısı
  Altında: hapisteki oyuncuların scroll listesi
  Boşsa: building_hapishane.png + "HABİSANE BOŞ"

EKRAN 2 — SC-JAIL (kendi hapis ekranı):
  Şehir/rank bilgisi → "YAKALANDIN" (kırmızı) → büyük sayaç (52px)
  [KEFALET ÖDE — $XXX] | [BUST OUT — %XX ŞANS  X/3 HAK]
  3 nokta hak göstergesi (kullanılan → soluk)

ASSET'LER:
  prisoner.png ✅   bustout_w.png ✅   building_hapishane.png ✅   btn_close_bar.png ✅
```

### Felony (OC) Detayları
```javascript
const FELONY_ROLLER = {
  lider:        { zorunlu:true,  sayi:1     },
  sofor:        { zorunlu:true,  sayi:1,    arac:'araba' },
  nisanci:      { zorunlu:true,  sayi:'1-2' },
  bomba_uzmani: { zorunlu:false, sayi:'0-1', malzeme:'TNT' },
};

// BAŞARI ORANI:
// Baz: R8-10:%50–60 | R11-13:%65–75 | R14:%80
// +Lider rank bonusu: her rank +%3
// +Nişancı KS bonusu: KS/100 × %10 (her nişancı için)
// +2. nişancı: +%5
// +Sürüş becerisi: beceri/100 × %15
// +TNT: +%3

// PARA: baz para × toplam başarı oranı
// %130+ başarı → para $6M+, başarı garantili
// %140+ başarı → para $10M, tüm item drop %100

// ITEM DROP (başarılıda):
// Normal: %0.2→T5 | %2→T4 | %10→T3 | %20→T2
// %130+:  T5:%50 / T4:%90 / T3:%70 / T2:%50
// %140+:  Tümü %100
// Item rastgele ekip üyesine düşer
```

### TNT
```javascript
// Fiyat: $50.000 (NPC market)
// Kullanım: Felony'de Bomba Uzmanı kullanır
// Başarı oranına +%3 katkı sağlar
```

### Offender Detayları
```
BASE_URL = https://mericaltinors1983-max.github.io/LaFamilia/

POPUP (prefix: of-) — matrix 700ms → şeffaf ekranlar → bottom:80px sabit

ANA EKRAN : offeender.png (120×120) + do-it.png (90px)
BAŞARILI  : 2.5sn → $AMOUNT yeşil + +50 XP turuncu → float → kapanır
BAŞARISIZ : 2.5sn → policecar.png + HAPİS → float +50 XP → Bustout açılır

BAŞARI ORANLARI:
  R1:%20 R2:%25 R3:%31 R4:%36 R5:%42
  R6:%47 R7:%52 R8:%58 R9:%63 R10:%68
  R11:%74 R12:%79 R13:%85 R14:%90

ASSET'LER:
  https://mericaltinors1983-max.github.io/LaFamilia/offeender.png  ✅
  https://mericaltinors1983-max.github.io/LaFamilia/do-it.png       ✅
  https://mericaltinors1983-max.github.io/LaFamilia/policecar.png   ✅
```

### Wheelman Detayları
```
BASE_URL = https://mericaltinors1983-max.github.io/LaFamilia/

- Başarılı: araba çalınır → garaja eklenir (50 model, 5 tier×10)
- Sürüş becerisi efektif hızı belirler

POPUP (prefix: wm-) — matrix 700ms → şeffaf ekranlar → bottom:80px sabit

ANA EKRAN : wheelman.png (120×120) + do-it.png (90px)
BAŞARILI  : 3sn → araba_tX_XX.png (110×75) + araba adı | level.png (75×75) + +75 XP
            Float: +75 XP turuncu → 🚗 ARABA EKLENDİ altın
BAŞARISIZ : 3sn → policecar.png + HAPİS → float +75 XP → Bustout açılır

BAŞARI ORANLARI:
  R1:%10 R2:%15 R3:%21 R4:%26 R5:%32
  R6:%37 R7:%43 R8:%48 R9:%54 R10:%59
  R11:%64 R12:%70 R13:%75 R14:%80

ARABA PNG: araba_t[1-5]_[01-10].png — arka plan ŞEFFAF zorunlu

ASSET'LER:
  https://mericaltinors1983-max.github.io/LaFamilia/wheelman.png   ✅
  https://mericaltinors1983-max.github.io/LaFamilia/do-it.png       ✅
  https://mericaltinors1983-max.github.io/LaFamilia/policecar.png   ✅
  https://mericaltinors1983-max.github.io/LaFamilia/level.png       ✅
  https://mericaltinors1983-max.github.io/LaFamilia/araba_t1_01.png ... araba_t5_10.png  ⏳
```

### Armed Robbery Detayları
```
BASE_URL = https://mericaltinors1983-max.github.io/LaFamilia/

POPUP (prefix: ar-) — matrix 700ms → şeffaf ekranlar → bottom:80px sabit

ANA EKRAN : armedrobbery.png (120×120) + do-it.png (90px)
BAŞARILI  : 3sn → $AMOUNT yeşil | +200 XP turuncu + ksks.png + +0.01 KS kırmızı
            Item düşerse: item PNG (70×70) + item adı + tier
            Float: +$X → +200 XP → +0.01 KS → ITEM DROPPED! (sırayla)
BAŞARISIZ : 3sn → policecar.png + HAPİS → float +200 XP → Bustout açılır

ITEM DROP ŞANSI: T2:%20 | T3:%10 | T4:%2 | T5:%0.2

BAŞARI ORANLARI:
  R1:%15 R2:%20 R3:%26 R4:%31 R5:%37
  R6:%42 R7:%48 R8:%53 R9:%59 R10:%64
  R11:%69 R12:%75 R13:%80 R14:%85

ASSET'LER:
  https://mericaltinors1983-max.github.io/LaFamilia/armedrobbery.png  ✅
  https://mericaltinors1983-max.github.io/LaFamilia/ksks.png           ✅
  https://mericaltinors1983-max.github.io/LaFamilia/do-it.png          ✅
  https://mericaltinors1983-max.github.io/LaFamilia/policecar.png      ✅
```

### Inside Job Detayları
```
BASE_URL = https://mericaltinors1983-max.github.io/LaFamilia/

POPUP (prefix: ij-) — matrix 700ms → şeffaf ekranlar → bottom:80px sabit

EKRAN AKIŞI:
  1. ANA EKRAN  : insidejob.png (120×120) + do-it.png → bas
  2. PARTNER    : empathy.png (120×120) + "PARTNER SEÇ" etiketi → bas
  3. İSİM GİRİŞ: "PARTNER" etiketi ortalı + input (beyaz border) + checked.png butonu
                 → nick yaz + bas → bildirim gönderilir
                   Input: altın border (bekleniyor) | KABUL: yeşil border | RED: temizlenir
  4. BEKLEME   : partner adı + "ONAY BEKLENİYOR" + [KABUL DEMO] butonu
  5. WIN / JAIL

BİLDİRİM SİSTEMİ (Inside Job + Felony — aynı sistem):
  ✓ basınca → 3 kanal eş zamanlı:
  1. Sağdan kayan panel (6sn): rol ikonu + nick + kaynak + KABUL/RED
  2. BİLDİRİM paneli: pending liste + KABUL/RED (badge +1)
  3. MESAJ inbox: kayıt düşer (badge +1)

BAŞARILI  : 3sn → $AMOUNT yeşil | +500 XP turuncu + ksks.png + +0.01 KS kırmızı
            +0.005 SÜRÜŞ (mavi) — lider için
            Float: +$X → +500 XP → +0.01 KS → +0.005 SÜRÜŞ (sırayla)
BAŞARISIZ : 3sn → policecar.png + HAPİS → float +500 XP → Bustout açılır

BAŞARI ORANLARI:
  R1:%5  R2:%10 R3:%15 R4:%20 R5:%25
  R6:%30 R7:%35 R8:%40 R9:%45 R10:%50
  R11:%55 R12:%60 R13:%65 R14:%70

ASSET'LER:
  https://mericaltinors1983-max.github.io/LaFamilia/insidejob.png   ✅
  https://mericaltinors1983-max.github.io/LaFamilia/empathy.png     ✅
  https://mericaltinors1983-max.github.io/LaFamilia/checked.png     ✅
  https://mericaltinors1983-max.github.io/LaFamilia/back.png        ✅
  https://mericaltinors1983-max.github.io/LaFamilia/ksks.png        ✅
  https://mericaltinors1983-max.github.io/LaFamilia/do-it.png       ✅
  https://mericaltinors1983-max.github.io/LaFamilia/policecar.png   ✅
```

### Felony Detayları
```
BASE_URL = https://mericaltinors1983-max.github.io/LaFamilia/

POPUP (prefix: fe-) — matrix 700ms → şeffaf ekranlar → bottom:80px sabit
RankMin: R8 (Operator)

EKRAN AKIŞI:
  1. ANA EKRAN  : mafia.png (120×120) + do-it.png → bas
  2. INTRO      : contribution.png (160×160) + "Make Team" (CorleoneDue altın) → bas
  3. EKİP KURMA :
       direksyon.png → şoför input + checked.png  (zorunlu)
       ksks.png      → nişancı 1 input + checked.png (zorunlu)
       ksks.png      → nişancı 2 input + checked.png (opsiyonel, +%5)
       bomb.png      → bomba uzmanı input + checked.png (opsiyonel)
       TNT checkbox  → +%3 başarı, $50.000
       [HESAPLA →]
  4. HESAPLAMA  : Büyük %XX başarı oranı + ✓ GARANTİLİ (≥130%) + [BAŞLAT]
  5. WIN → para + XP + KS + item floatları (window.innerHeight-210px'ten yukarı)
     3.5sn sonra %30 hapis zar:
       %30 → jail ekranı → bustout açılır
       %70 → fe_close(), temiz

CLOSE BUTONU (of/wm/ar/ij/fe/bu/kc/po — tüm suçlar):
  ❌ close_icon.png KULLANILMAZ — sağ üstte buton YOK
  ✅ btn_close_bar.png — ALT ORTADA — popup div'i içinde

MİNİMİZE (SADECE FELONY):
  − butonu → top:10px; right:46px (X'in yanında)
  → popup translateY(110%) ile ekran dışına kayar, overlay kapanır
  → fe_team state + input değerleri (altın/yeşil border dahil) KORUNUR
  Bottom bar üstünde "FELONY ●" floating badge görünür (mafia.png + altın pill)
  Badge'e basınca → translateY(0) + opacity:1 → direkt açılır (matrix YOK)
  ✕ butonu → transform/opacity sıfırlanır, open/show class kaldırılır, state sıfırlanır

BİLDİRİM: fe_addMember → 3 kanal (sağdan kayan + bildirim paneli + inbox)
           Input: altın border (bekleniyor) → yeşil border (kabul) → temiz (red)

FLOAT POZİSYONU (tüm suçlar): window.innerHeight - 210px'ten başlayıp yukarı kayar

ASSET'LER:
  https://mericaltinors1983-max.github.io/LaFamilia/mafia.png         ✅
  https://mericaltinors1983-max.github.io/LaFamilia/contribution.png  ✅
  https://mericaltinors1983-max.github.io/LaFamilia/direksyon.png     ✅
  https://mericaltinors1983-max.github.io/LaFamilia/ksks.png          ✅
  https://mericaltinors1983-max.github.io/LaFamilia/bomb.png          ✅
  https://mericaltinors1983-max.github.io/LaFamilia/checked.png       ✅
  https://mericaltinors1983-max.github.io/LaFamilia/do-it.png         ✅
  https://mericaltinors1983-max.github.io/LaFamilia/policecar.png     ✅
```

### Suç Sonuç Ekranı Akışı
```
1. Butona basılır
2. GIF bir kez oynar (o suça ait)
3. Sonuç ekranı gelir
4. Float efektleri sırayla yukarı kalkar (XP → para → KS → ...)
```

### Hapis Ekranı
```
3 çıkış:
A) Kefalet öde
B) Kendini Bustout et (max 3 hak)
C) Başkasının Bustout etmesini bekle

TopBar + TopNav + BottomBar GİZLENİR
```

---

## POLIGON

```javascript
// 2 ayrı poligon modu — bottom bar POLIGON butonuna basınca
// Matrix 700ms → şeffaf popup → 2 PNG kart (POLİGON 1 | POLİGON 2)
// PNG'ler: target.png (P1) | shooting-target.png (P2)
// Her modun ayrı CD'si var

const POLIGON_ORTAK = {
  ks_kazanc: 0.005,    // skor ≥ 10 → +0.005 KS
  ammo:      6,        // 6 mermi
  win_esik:  10,       // 10 puan → KS kazanılır
  cd:        600000,   // 10 dakika (ms) — girince hemen başlar
};

// localStorage keys:
// POLİGON 1 → 'po1_cd_end'
// POLİGON 2 → 'po2_cd_end'
// CD ayrı ayrı — P1 kilitliyken P2 açık olabilir
```

### POLİGON 1 — Joystick + Sabit Kağıt Hedefler
```javascript
// Tam ekran, beyaz arka plan
// Kontrol alanı: beyaz bg, siyah joystick + altın oklar, kırmızı ATEŞ butonu
// Soldaki KS bar: oyuncunun mevcut KS seviyesini gösterir

// 5 sabit kağıt hedef (tel/klipsle asılı görünüm):
// Küçük (üst orta)    → 5pt
// Orta  (üst sol/sağ) → 4pt
// Büyük (alt sol/sağ) → 3pt

// Joystick → crosshair hareketi (kırmızı, 48px)
// KS etkisi: BASE_KS düşükse crosshair titrer
//   wobble = (100 - KS) / 100 * 2.2
// Tüm hedefler vurulunca 500ms → yeniden spawn

// KS ateş etkisi: hedef merkezi arası mesafeye göre ZATEN puanlama var
// (ek hitChance YOK — vurulunca direkt puan)
```

### POLİGON 2 — Hareket Eden Hedefler (Tap)
```javascript
// Tam ekran, koyu gradient arka plan (lacivert)
// Silüetler (2pt) ve sandıklar (1pt) soldan/sağdan kayar

// KS etkisi:
// 1. Hedef boyutu + hızı:
//    ksRatio = MIN(100, KS) / 100
//    minSz = 22 + ksRatio * 24   // KS0:22px → KS100:46px
//    minSpd = 0.5 + (1-ksRatio)*1.2  // KS0:1.7hız → KS100:0.5hız
//
// 2. hitChance (isabet şansı):
//    hitChance = 0.30 + (MIN(100, KS) / 100) * 0.70
//    KS 0  → %30 isabet
//    KS 50 → %65 isabet
//    KS 100 → %100 isabet
//    → Hedefi vursan bile ıska çıkabilir!

// Vurulunca puan (hedef merkezine yakınlık):
//    ratio = dist / (size/2)
//    ratio < 0.3 → 3pt (merkez)
//    ratio < 0.7 → 2pt (orta)
//    ratio ≥ 0.7 → 1pt (kenar)
//    Iska → 0pt, hedef ekranda kalmaya devam eder
```

### Popup Mimarisi
```
Bottom bar POLIGON → showCrimePopup('poligon') → po_open()
→ Matrix 700ms (320×520px, bottom:116px, şeffaf canvas)
→ po-pop açılır (position:fixed, bottom:116px, transparent bg)
   ├── target.png (110×110) → onclick: po_openGame1()  → "POLİGON 1"
   └── shooting-target.png (110×110) → onclick: po_openGame2() → "POLİGON 2"
   └── btn_close_bar.png (alt)

po1-wrap / po2-wrap: position:fixed;inset:0;z-index:10100
← GERİ butonu → po_closeGame()
```

### Asset'ler (LaFamilia repo)
```
target.png          — POLİGON 1 seçim kartı PNG'si
shooting-target.png — POLİGON 2 seçim kartı PNG'si
```

---

## ARABA YARIŞI

```javascript
const ARABA_YARISI = {
  dongu_suresi:   20,   // dakika — sürekli döngü
  lobi_suresi:    5,    // dakika — yarıştan önce
  yaris_animasyon:15,   // saniye — hızlandırılmış
  gunluk_max:     12,   // oyuncu başına
  yariscilardsa:  10,   // yarış başına kişi
};

// DÖNGÜ AKIŞI:
// 00:00–15:00 → Bekleme: "Sonraki yarış: XX:XX" sayacı
// 15:00–20:00 → Lobi (5dk): katılımcılar listelenir, [KATIL] butonu
// 20:00       → Yarış başlar (matrix efekti → tam ekran)
// 20:10–20:15 → Sonuç ekranı → float: puan + para

// KAYIT:
// Her yarış için ayrı kayıt — lobide [KATIL] basılmazsa araba start'ta durur
// Katılmayan: animasyonda başlangıçta sabit, sonuç listesinde en sonda
// Ücret yok — bedava

// BİLDİRİMLER:
// -5dk → "YARIŞ LOBİSİ AÇILDI — KATILMAK İÇİN DOKUN"
// Yarış bitti → "YARIŞ SONUCU: X. SIRA — +Y PUAN"
```

### Ekran Layoutu
```
┌─────────────────────────────────────┐
│  ← GERİ    YARIŞ #247    ⏱ 00:12  │  ← Header (44px)
├─────────────────────────────────────┤
│  🏁 ════════════════════════ 🏁   │
│     [🚗][🚗][🚗] yan scroll       │  ← Pist (180px)
│     kendi araban ortada             │
│     arka plan kayar                 │
├─────────────────────────────────────┤
│  #  │ OYUNCU     │ ARABA  │ HIZ    │
│  1  │ IRON_WOLF  │ T5 #3  │ ████░ │
│  2  │ SEN ←      │ T4 #7  │ ███░░ │  ← 10 kişi
│  3  │ ...        │        │       │    anlık sıralama
├─────────────────────────────────────┤
│  Lobi: [KATIL] / Yarış: progress   │  ← Alt (64px)
└─────────────────────────────────────┘
// TopBar + TopNav + BottomBar GİZLENİR
```

### Hız Hesabı
```javascript
// Efektif hız = araba_hizi × (surus_becerisi / 100)
// Araba hızı: T1:40 T2:55 T3:70 T4:85 T5:100
// Sürüş becerisi: 0–100 (araba yarışıyla artar)
```

### Puan & Ödül
```javascript
const YARIS_PUAN = { 1:100, 2:60, 3:40, 4:20, 5:10, 6:5, 7:5, 8:5, 9:5, 10:5 };
// Beraberlikte: rastgele biri kazanır
// Sürüş becerisi sıfırlanmaz, ay sonu yarış puanları sıfırlanır

const YARIS_AYLIK_ODUL = {
  1: { araba:'en hızlı T5 özel', para:5000000 },
  2: { araba:'T4',               para:3000000 },
  3: { araba:'T4',               para:1500000 },
};
```

### Asset'ler
```
araba_t1_01.png … araba_t5_10.png  (50 araba ✅)
pist_zemin.png    — yol arka planı
bitis_cizgisi.png — bitiş çizgisi
```

---

## SEYAHAT SİSTEMİ

```javascript
// Sadece uçakla seyahat edilir
// Baştan açık, uçak şartı yok
// Daha iyi uçak alınınca süre düşer

const SEYAHAT_SURE = {
  ic:         2,   // dakika (aynı ülke)
  komsu:      3,
  ayni_kita:  4,
  farkli:     5,
};

// Seyahatte:
// - Saldırılamaz, saldıramaz
// - Hiçbir suç işleyemez, kill yapamaz
// - Casino, kaçakçılık, gazete, market, auction house erişilebilir

// Seyahat mini banner gösterilir
// İptal = %50 ceza
```
---

## KAÇAKCILIK

### 3 Kanal
```javascript
// KK_KANALLAR — prototype + RN canonical
const KANALLAR = {
  konteyner: { arac:false,  personel:'conductor', personelZorunlu:false },
  port:      { arac:'gemi', personel:'kaptan',    personelZorunlu:true  },
  airport:   { arac:'ucak', personel:'pilot',     personelZorunlu:true  },
};
// Konteyner: şartsız NORMAL. Conductor sadece süreyi kısaltır (AUTO'da zorunlu).
// Port: Gemi + Kaptan olmadan çalışmaz (NORMAL ve AUTO)
// Airport: Uçak + Pilot olmadan çalışmaz (NORMAL ve AUTO)
// Rank şartı YOK — tüm kanallar rank:0'dan açık
```

### Bekleme Süreleri (dakika)
```javascript
const KAÇAKCILIK_SURE = {
  //              konteyner  port  airport
  ic:           [ 15,        10,   5   ],
  komsu:        [ 20,        15,   10  ],
  ayni_kita:    [ 25,        20,   15  ],
  farkli_kita:  [ 30,        25,   20  ],
};
```

### Personel Süre İndirimi
```javascript
const PERSONEL_INDIRIM = {
  T1: '-%0',    // baz süre
  T2: '-%10',
  T3: '-%25',
};
// Conductor → konteyner süresini düşürür
// Kaptan    → port süresini düşürür
// Pilot     → airport süresini düşürür
```

### Auto Kaçakçılık
```javascript
// KK_AUTO_SARTLAR — prototype + RN canonical
const AUTO_SARTLAR = {
  konteyner: { npc:'conductor', vipMin:0 },  // Conductor zorunlu, VIP gerekmez
  port:      { npc:'kaptan',    vipMin:3 },  // Gemi + Kaptan + VIP3
  airport:   { npc:'pilot',     vipMin:4 },  // Uçak + Pilot + VIP4
};

// KİLİT MANTIĞI (canonical):
// Her kanal kendi içinde kilitler — diğer kanalları etkilemez
//
//   Aktif olan          →  Kilitli olan
//   NORMAL Tren         →  NORMAL Tren + AUTO Tren
//   AUTO Tren           →  AUTO Tren   + NORMAL Tren
//   NORMAL Gemi         →  NORMAL Gemi + AUTO Gemi
//   AUTO Gemi           →  AUTO Gemi   + NORMAL Gemi
//   NORMAL Uçak         →  NORMAL Uçak + AUTO Uçak
//   AUTO Uçak           →  AUTO Uçak   + NORMAL Uçak
//
// Tren AUTO yaparken Gemi/Uçak NORMAL veya AUTO yapılabilir. ✅
// Kilit kontrolü: kk_checkKanal(arac) — KK_TB[arac].active === true ise kilitli

// AUTO DÖNGÜ:
// 10 sefer yapar, durur
// Her sefer tamamlanınca: ara toast ("SIGARA · 3/10 · +$120")
// 10. sefer tamamlanınca: büyük toplam toast ("✅ AUTO TREN · SIGARA · TOPLAM +$1200")
// kkStartSefer(arac) — tek sefer timer'ı, bitince otomatik bir sonrakini çağırır

// İPTAL (kkTbIptal):
// Auto iptal edilirse tamamlanan seferler ödenir
// Toast: "AUTO TREN İPTAL · 5/10 TAMAMLANDI · +$600"
// 0 sefer tamamlanmışsa sadece normal iptal tostu
```

### Fiyat Sistemi (Ekonomi)
```
PROTOTIP: Saat başı (60dk) localStorage bazlı random fiyat
  - Her şehir × her ürün için min–max arası tam sayı üretilir
  - kacFiyatYukle() → localStorage'dan okur, saat geçmişse yeniler
  - kacGetFiyat(sehir, urun) → anlık fiyatı döner
  - kacGetTrend(p, fiyat) → ↓ ucuz / → orta / ↑ pahalı
  - Her dakika kontrol — saat geçince tüm fiyatlar yenilenir
  - localStorage key: lf_kac_fiyat

REACT NATIVE (hedef): Server-side arz/talep ekonomisi
  - 1000 kişilik gerçek ekonomi — çok alım → fiyat↑, çok satış → fiyat↓
  - kacFiyatYukle() içi localStorage → API çağrısına dönüşür
  - Fiyatlar min/max sınırında kalır (sonsuz şişme olmaz)
```

### Şehirler (40 şehir — 10 ülke × 4)
```
Türkiye  : Istanbul(L), Izmir(L), Trabzon(L), Diyarbakir
İtalya   : Napoli(L), Roma(L), Sicilya(L), Milano        — KOMŞU
Rusya    : Moskova, St.Petersburg(L), Kazan, Vladivostok(L) — KOMŞU
Almanya  : Hamburg(L), Berlin, Munih, Frankfurt           — KOMŞU
ABD      : New York(L), Chicago(L), Miami(L), Las Vegas
Meksika  : Tijuana(L), Mexico City, Guadalajara, Monterrey
Kolombiya: Medellin, Bogota, Cartagena(L), Cali
Brezilya : Sao Paulo(L), Rio de Janeiro(L), Salvador, Fortaleza
Japonya  : Tokyo(L), Osaka(L), Yokohama(L), Kyoto
Çin      : Sanghay(L), Hong Kong(L), Shenzhen(L), Pekin
(L) = liman şehri — port kanalında kullanılabilir
```

### Kaçakçılık Popup Mimarisi (canonical)
```
BottomBar KAÇAKÇILIK butonuna basınca:
→ Matrix rain (kk-mx canvas, 700ms) → kk-pop açılır (background:transparent, border:none)
→ kk-pop içinde şeffaf zemin — PNG'ler ve close bar görünür

Screen akışı:
  sc-kk-main  → NORMAL / AUTO PNG seçimi (2 kart, space-evenly)
  sc-kk-kanal → TREN / GEMİ / UÇAK PNG seçimi (3 kart, space-evenly)
                Kilitli kanallar opacity:0.45 + 🔒 + sebep yazısı
  sc-kk-trade → Ürün listesi (renkli satırlar: yeşil/sarı/kırmızı)
                Ürüne basınca: kk-psheet (fixed, popup dışında) açılır
                Şehir seçilince: kk_sendGonder() → popup kapanır + trade banner çıkar

Overlay  : kk-ov
Canvas   : kk-mx (matrix rain)
Popup    : kk-pop (display:none → .open → .show animasyonu)
Screens  : kk-screens (.sc / .sc.on)
Psheet   : #kk-psheet (position:fixed, popup dışında, z-index:10100)

Kanal PNG'leri:
  TREN (konteyner) → kacak_konteyner.gif
  GEMİ (port)      → cargo-ship.gif  + harbour.png (seçim ekranı)
  UÇAK (airport)   → kacak_airport.gif

Kanal kilit şartları:
  KONTEYNER Normal: şartsız | Auto: Conductor zorunlu
  PORT      Normal: Gemi + Kaptan | Auto: +VIP3
  AIRPORT   Normal: Uçak + Pilot  | Auto: +VIP4
  Rank şartı YOK — tüm kanallar rank:0'dan açık

Ürün listesi görünümü:
  - Şeffaf zemin (bustout satır stili rgba(0,0,0,0) arkaplan)
  - Sol renkli bg: yeşil=ucuz(≤%33) / sarı=orta / kırmızı=pahalı(≥%66)
  - Her satır: PNG | isim | alış fiyatı | potansiyel kâr
  - Kilitli ürünler (rank şartı) opacity:0.35

Şehir seçim sheet (#kk-psheet):
  - Siyah arka plan (rgba(10,10,10,0.92))
  - Her satır: city_[id].png (32×32) | isim · tag · süre · satış fiyatı | kâr
  - Top 3 şehir: en karlı sıralama (current city hariç)
  - Port kanalı: sadece liman şehirleri

Trade banner (3 bağımsız banner — her kanal için ayrı):
  ID'ler: #kk-tb-konteyner | #kk-tb-port | #kk-tb-airport
  CSS class: .kk-tb → display:none | .kk-tb.on → display:flex
  - Beyaz arka plan, siyah yazı, bottom:64px, height:40px
  - İçerik: [kanal GIF] [ürün → şehir] [time.gif] [süre sayacı] [✕ İPTAL]
  - Sayaç bitince: banner kaybolur + kk-arrival-toast bildirimi
  - Urgent (<10sn): sayaç kırmızıya döner
  - 3 banner aynı anda aktif olabilir (her kanal bağımsız)

  NORMAL banner → border-top: 2px solid #111 (siyah)
  AUTO banner   → .kk-auto-active class eklenir:
    - border-top: 2px solid #C9A84C (altın)
    - shimmer animasyonu: altın/beyaz, 1.8sn (NORMAL: 3sn)
    - Mini yuvarlak hali: border: 2px solid #C9A84C + hafif altın glow
    - Görsel içerik AYNI (aynı GIF, aynı route, aynı timer) — yazı farkı YOK
    - Tek fark: altın border/shimmer

  KK_TB state (her kanal):
  { active, remainingSecs, timerInt,
    autoMode, autoSeferNo, autoTotalKar,
    autoUrun, autoQty, autoSure, autoKar, autoHedef, autoGif }
```

### Ürünler
```javascript
// ALL_PRODUCTS — 10 kaçakçılık ürünü (prototip + RN canonical)
const SMUGGLE_PRODUCTS = [
  { id:'sigara', name:'SIGARA',  rankMin:0,  min:3,    max:6,    img:'urun_sigara.png' },
  { id:'bira',   name:'BIRA',    rankMin:0,  min:8,    max:16,   img:'urun_bira.png'   },
  { id:'pill',   name:'PILL',    rankMin:0,  min:15,   max:30,   img:'urun_pill.png'   },
  { id:'kan',    name:'KAN',     rankMin:0,  min:85,   max:170,  img:'blood.png'        },
  { id:'viski',  name:'VISKI',   rankMin:3,  min:45,   max:90,   img:'urun_viski.png'  },
  { id:'chip',   name:'CHIP',    rankMin:6,  min:120,  max:240,  img:'urun_chip.png'   },
  { id:'drone',  name:'DRONE',   rankMin:5,  min:140,  max:280,  img:'dronee.png'       },
  { id:'altin',  name:'ALTIN',   rankMin:8,  min:300,  max:600,  img:'urun_altin.png'  },
  { id:'elmas',  name:'ELMAS',   rankMin:11, min:750,  max:1400, img:'urun_elmas.png'  },
  { id:'white',  name:'WHITE',   rankMin:13, min:1500, max:2600, img:'urun_white.png'  },
];
// Kan: HP iyileştirici + kaçakçılık malı (img: blood.png)
// Drone img: dronee.png (çift e)
// Fiyat saat başı (60dk) yenilenir — prototipte localStorage, RN'de server API
```

### Kapasite (Slot) Sistemi
```javascript
const kapasiteHesapla = (p) =>
  p.cantaSlot    // T1:5 T2:10 T3:18 T4:28 T5:40
  + p.suitSlot   // T1:10 T2:20 T3:30 T4:40 T5:50
  + p.gemiSlot   // T1:25 T2:50 T3:90 T4:140 T5:230
  + p.ucakSlot;  // T1:40 T2:75 T3:100 T4:150 T5:220
// Envanter sınırsız, kapasite sadece kaçakçılık seferi için
```

---

## ARAÇLAR & PERSONEL

### Gemiler (NPC — her tier 1 kez)
```javascript
const NPC_GEMILER = [
  { tier:1, name:'Rusty Barge',    alis:300000,  slot:25  },
  { tier:2, name:'Dark Harbor',    alis:800000,  slot:50  },
  { tier:3, name:'Iron Smuggler',  alis:2000000, slot:90  },
  { tier:4, name:'Black Tide',     alis:4000000, slot:140 },
  { tier:5, name:'The Leviathan',  alis:7000000, slot:230 },
];
```

### Uçaklar (NPC — her tier 1 kez)
```javascript
const NPC_UCAKLAR = [
  { tier:1, name:'Green Prop',   alis:500000,   slot:40  },
  { tier:2, name:'Red Duster',   alis:1500000,  slot:75  },
  { tier:3, name:'Air Courier',  alis:3000000,  slot:100 },
  { tier:4, name:'Sky Liner',    alis:5000000,  slot:150 },
  { tier:5, name:'Shadow Jet',   alis:10000000, slot:220 },
];
// Satış: alış × 0.50 | Max 1 gemi, 1 uçak
// Daha iyi uçak → seyahat süresi düşer
```

### Personel (NPC — her tier 1 kez)
```javascript
const NPC_PERSONEL = [
  { id:'conductor', T1:1000000,  T2:1500000, T3:3000000 },
  { id:'kaptan',    T1:750000,   T2:2000000, T3:4000000 },
  { id:'pilot',     T1:1000000,  T2:2500000, T3:5000000 },
];
```

### Araçlar Sekmesi (Karakter Ekranı)
```
- Tüm sahip olunan uçak, gemi, arabalar listelenir
- Aktif kullanılacak seçilir (1 aktif gemi, 1 aktif uçak, 1 aktif araba)
- Personel de buradan seçilir
```

---

## BANKA

```javascript
// POPUP (standart 320×520px):
// AÇILIŞ: TopNav BANKA → showBankaPopup() | Harita banka binası → showBankaPopup()
// Sol: nav_banka.png | Orta: lafamilia_logo.png | Sağ: icon_info.png + close_icon.png
// Shimmer efekti → 1.1sn → içerik fade+scale

const FAIZ = [
  { sure:'6 SAAT',  oran:'%3',  napoliOran:'%5'  },
  { sure:'12 SAAT', oran:'%5',  napoliOran:'%7'  },
  { sure:'24 SAAT', oran:'%7',  napoliOran:'%10' },
];
// Süre dolunca otomatik cebe girer
// Max 3 eş zamanlı | Min: $100.000
// Ölünce bankadaki %50 → vasiyet sistemine
// Napoli bankası +%2 ekstra faiz (tüm vadelerde)

// İÇERİK: Faiz tablosu + Napoli özel oranı + kurallar + BANKAYA GİR › butonu
// Para transferi: oyuncular arası + aile kasasına banka üzerinden
```

---

## CASINO (7 Oyun)

```javascript
// EKRAN: Tam ekran — TopBar/BottomBar görünür (gizlenmez)
// AÇILIŞ: TopNav CASİNO → direkt tam ekran | Harita casino binası → direkt tam ekran

// HEADER (standart):
// Sol: nav_kumarhane.png | Orta: lafamilia_logo.png | Sağ: icon_info.png + close_icon.png
// border-bottom: 3px double #111

// JACKPOT BANNER:
// beyaz arka plan | jackpot.png + $500,000 miktar | font: Bebas Neue 24px
// border-bottom YOK
// 10sn'de bir parlama efekti (altın → beyaz glow → altın)
// Jackpot banner altındaki oyun grid'i -25px margin-top ile yukarı taşınmış

// OYUN LİSTESİ — 3+3+1 grid:
// oyun_meyve.png     → LUCKY FRUITS    (3-reel slot)
// oyun_makine.png    → 5 REEL DELUXE   (5-reel slot)
// oyun_blackjack.png → BLACKJACK       (dealer 17'de durur)
// oyun_poker.png     → VIDEO POKER     (Jacks or Better)
// oyun_rulet.png     → RULET           (Avrupa, tek sıfır)
// oyun_at.png        → AT YARIŞI       (6 at, random odds)
// oyun_boks.png      → BOKS            (2 dövüşçü, 6 raunt) — 2. sıranın ortasında

// CLOSE BAR: border-top: 3px double #111 | KAPAT yazısı

// KASA MEKANİĞİ:
// Sahip kasayı fonlar
// Oyuncu kaybedince: %98 kasaya, %2 şehri kontrol eden aile kasasına
// Oyuncu kazanınca: ödeme kasadan gelir → kasa boşalırsa "CASINO CLOSED"
// Jackpot havuzu: slot + rulet paylaşır, başlangıç $500K

const BAHIS_BUTONLARI = [100, 500, 1000, 5000, 10000];
// Çipler oyun içinde gösterilir — lobide gösterilmez

// ASSET'LER:
// nav_kumarhane.png ✅  jackpot.png ✅
// oyun_meyve.png ✅    oyun_makine.png ✅   oyun_blackjack.png ✅
// oyun_poker.png ✅    oyun_rulet.png ✅    oyun_at.png ✅
// oyun_boks.png ✅
```

---

## MARKET

### NPC Shop
```javascript
// Mermi: 1.000 paket → $1.000.000 (CD yok)
// TNT: $50.000
// Gemi, Uçak, Personel, BG (her birinden 1 kez)
// Arabalar SADECE Auction House'da (NPC'de yok)
```

### Auction House
```javascript
// Server geneli (şehre özgü değil)
// Satılabilir: Silah / Kolye / Çanta / Araba / Mermi(1K paket) / Witness Report
// Max 10 aktif listing | Süre: 6 saat
// Min teklif artışı: %5
// Buyout: başlangıcın min %150si
// Anti-snipe: son 60sn teklif → +2dk
// İptal: item geri gelir, 10dk tekrar listeleyemez
// Oyuncular arası item/araba alım satımı SADECE buradan
```

### Arabalar
```javascript
// 50 model, 5 tier × 10
// SADECE: Inside Job + Felony + Crusher'da kullanılır
// Kaçakçılıkta KULLANILMAZ
// T1:$1K–$10K | T2:$11K–$20K | T3:$21K–$30K | T4:$31K–$40K | T5:$41K–$50K
// T5 altın parlama animasyonu
```
---

## SAVAŞ SİSTEMİ

### Saldırı Akışı
```javascript
// 1. Dedektif tut → 30dk arama (hedefe bildirim GİTMEZ)
// 2. Hedef bulundu → Push + email → [ÖLDÜR] butonu
// 3. Mermi sayısı gir → [SALDIR]
// 4. Kontrol: aynı şehirde mi + sığınakta/seyahatte değil mi?
//    Evet → saldırı gerçekleşir | Hayır → iptal, dedektif ücreti yanmış
// 5. Atılan mermi × (KS/100) = efektif hasar
//    Efektif hasar > toplam can → ÖLÜM

// Kill cooldown: 12 saat
// Rank kuralı: Max 1 üst ranka saldırabilirsin
// Seyahatteyse → saldırı iptal
// Sığınaktaysa → BULUNAMAZ
```

### Dedektif Maliyeti
```javascript
const DEDEKTIF_MALIYET = {
  1:1000,  2:1000,  3:4000,  4:4000,  5:9000,
  6:16000, 7:25000, 8:36000, 9:49000, 10:64000,
  11:64000, 12:81000, 13:81000, 14:100000,
};
```

### Kill Ödülleri
```javascript
const KILL_ODUL = {
  xp_ayni_rank: 1500,
  xp_ust_rank:  1800,
  ks_ayni_rank: 0.01,
  ks_ust_rank:  0.02,
};
// Öldürülen oyuncunun cep parası → öldürene geçer
```

### Backfire Sistemi
```javascript
// Karakter ekranında ayarlanır (4 seçenek):
const BACKFIRE = {
  kapali:  0,    // backfire yok
  yarisi:  0.5,  // yarı hasar saldırana döner
  ayni:    1.0,  // aynı hasar saldırana döner
  iki_kat: 2.0,  // iki katı hasar saldırana döner
};
```

### Başarısız Saldırı
```
- Hedefe attack_alert mesajı gönderilir
```

### Witness Report
```
- Öldürme anında random online oyuncuya (katil/kurban/aynı aile hariç) düşer
- Envanterde DOCUMENTS sekmesinde görünür
- Sadece Auction House'da satılabilir (NPC'ye satılamaz)
- Fiyatı satıcı belirler
```

### KS Etkisi
```
Efektif hasar = atılan mermi × (KS / 100)
KS 0   → %0 isabet (sıfır hasar)
KS 50  → %50 isabet
KS 100 → %100 isabet
```

---

## ÖLÜM & LEGACY

### Ölüm Sonrası
```javascript
// Cep parası     → öldürene
// Banka %50      → vasiyet önceliğine
// Arabalar       → vasiyet önceliğine
// Uçak/Gemi/Item/BG → YOK
// Binalar        → SAHİPSİZ (aynı fiyatla)
```

### Ölüm Ekranı
```
- Tam ekran, tüm menüler gizlenir
- Beyaz arka plan üzerine skull animasyonu (PNG/GIF)
- Öldüren nick, rank, şehir bilgisi
- Vasiyet/Legacy seçim ekranı
- Ticker'da Rank 10+ ölümü altın manşet olarak yayınlanır
```

### Vasiyet Sistemi
```javascript
// OYUNCU VASİYETİ (her zaman yazılabilir):
// 1. LEGACY   — Rank10+ veya VIP4 ile ölündüyse → yeni hesaba (1 kez)
// 2. MANUAL   — Manuel seçilen kişiye (nick yazılır, anlık kontrol)
// 3. BURN     — Yok olur

// AİLE VASİYETİ (sadece Patron yazabilir):
// Patron ölünce aile bu kişiye geçer
// Patron vasiyetsiz ölürse → aile düşer, dağılır
```

### Legacy Avantajları
```javascript
// CD -%50
// Başlangıç rank: R5-7→R2 | R8-10→R3 | R11-12→R4 | R13-14→R5
// 2 hafta 2x XP + ölümsüzlük
// VIP + aile ilişkisi korunur (aynı ailede başlar)
// 48 saatte seçilmezse Legacy hakkı kaybolur
```

### Ölünce Server'dan Silinme
```
Legacy kullanılmazsa → hesap server'dan silinir, tüm veriler temizlenir
Legacy kullanılırsa  → yeni hesap açılır
```

---

## SAFE HOUSE

```javascript
const SAFEHOUSE = {
  maliyet: 100000,    // $/saat, tüm ranklar sabit
  sureler: [1,3,6,12,24],  // saat seçenekleri
};
// Saldırıya uğranamaz, dedektifle bulunamaz
// Sadece gazete okunabilir
// TopBar + TopNav + BottomBar GİZLENİR
// Kullanılmayan süre iade edilmez
```

---

## HİTLİST

```javascript
const HITLIST = {
  sure:    72,    // saat
  dagitim: { oldurene:0.80, ailesi:0.20 },
  // %80 öldürene, %20 öldürenin aile kasasına
  // 72 saat içinde öldürülmezse → ödül burn
};
```

---

## AİLE SİSTEMİ

### Aile Kurma
```javascript
// Rank 12 (Boss) ve üzeri kurabilir
// Slot sistemi: her slot $5.000.000, +25 üye kapasitesi
// Max 4 slot → max 100 üye (+2 yönetici)
// Kurulan şehir = HQ şehri (değiştirilemez)
```

### Hiyerarşi
```javascript
const AILE_HIYERARSISI = {
  patron:      1,   // Aile lideri
  consigliere: 1,   // Yardımcı
  capo:        4,   // Her 25 kişilik grubun lideri (4 slot = 4 Capo)
  uye:         'kalan',
};
```

### Aile Şehri Kuralı
```
- Her aile sadece 1 şehre egemen olabilir (HQ şehri)
- Üyeler sadece HQ şehrindeki binaları satın alabilir
- Başka şehirde bina alınamaz
```

### Üyelik
```
- Aile sayfasından başvuru yapılır
- Boss veya Consigliere onaylar/reddeder
- Rank veya para şartı yok
- İstediği zaman ayrılabilir
- Kovma: Boss veya Consigliere yapabilir
```

### Aile Kasası
```
- Her üye banka üzerinden para yatırabilir
- Sadece Boss ve Consigliere çekebilir
```

### Aile Özellikleri
```javascript
// Aile kurulunca: isim + renk (beyaz seçilemez) + simge seçilir
// Kapak görseli: Patron yükler (JPEG/PNG), moderasyon var
// İttifaklar ve düşmanlar: sadece görsel etiket, oyun mekaniğine etkisi yok
// Boss + Consigliere tüm üyelere toplu mesaj atabilir
// Aile sohbet: 3 sekme — Aile | Server | Global
```

### Crusher
```javascript
const CRUSHER = {
  acan:       'Boss veya Consigliere',
  sehir:      'sadece HQ şehrinde',
  araba_basi: 12,  // mermi
};

// AKIŞ:
// 1. Boss/Consigliere crusher açar
// 2. Tüm aile üyelerine sol taraftan bildirim kayar (sabit kalır, X ile kapanır)
// 3. Üye [ARABA GÖNDER] → garaj listesi + onay popup
// 4. Onaylayınca → araba silinir → +12 mermi
// 5. BottomBar'da ilgili buton pulse (yanıp söner)

// BİLDİRİM:
// position:fixed; left:0; bottom:80px; soldan slide-in
// Sabit kalır — X'e basılana kadar
// crusherAc('BOSS_ADI') ile tetiklenir

// KISITLAMALAR:
// Sadece HQ şehrindeki üyeler araba gönderebilir
// Garajdaki arabalar şehirsiz — crush hariç
// Boss/Consigliere rankı gerekli (açmak için)
```

### Saldırı Sistemi
```
❌ Family War mekaniği YOKTUR.
✅ Her oyuncu istediği oyuncuya serbestçe saldırabilir.
✅ Aynı şehirde olma şartı geçerlidir.
✅ Saldırı için aile üyesi olmak gerekmez.
✅ Aileden biri saldırıya uğrarsa aile kasasına %2 düşer (kill payı).
```

### Aile Sıralama
```
Aile sayfasında ayrı sekme:
- Server'daki tüm aileler güç skoruna göre sıralanır
- Güç skoru = toplam üye XP + bina puanları
- Kontrol ettiği şehir gösterilir
```

---

## DETEKTIF & SALDIRI DIŞI KORUMALAR

```javascript
// Yeni oyuncu: 5 gün koruma. Saldırırsa anında kalkar.
// Seyahatte: saldırılamaz
// Safe House: bulunamaz, saldırılamaz
// Aynı şehirde olmak zorunlu (saldırı için)
```
---

## VIP SİSTEMİ

### VIP Puan ile Kazanılır (Para ödenmez)
```javascript
const VIP_PUAN_ESIK = {
  1: 500,
  2: 1500,
  3: 3000,
  4: 5500,
  5: 9000,
};
// 90 günde günde 100 puan yaparak VIP5 olunabilir
// Sandık 1 (herkese): 40 puan/gün
// Sandık 2 (görev yapana): 60 puan/gün
```

### VIP Avantajları
```javascript
const VIP = {
  1: { fiyat:4.99,  avantaj:['Tüm suç CD -%5', 'Günlük giriş ×1.5'] },
  2: { fiyat:9.99,  avantaj:['...VIP1', 'Tüm suç CD -%10', 'Günlük giriş ×2'] },
  3: { fiyat:19.99, avantaj:['...VIP2', 'Tüm suç CD -%15', 'Günlük giriş ×3',
                              '1× T1 Kaptan hediyesi (1 kez)', 'Her gün T4 BG kafası'] },
  4: { fiyat:29.99, avantaj:['...VIP3', 'Tüm suç CD -%20',
                              '1× T1 Pilot hediyesi (1 kez)', 'Her gün T5 BG kafası'] },
  5: { fiyat:49.99, avantaj:['...VIP4', 'Tüm suç CD -%25', 'Kaçakçılık bekleme -%20'] },
};
// Auto Konteyner: Conductor + VIP0 (VIP gerektirmez)
// Auto Port:      Gemi + Kaptan + VIP3
// Auto Airport:   Uçak + Pilot + VIP4
```

---

## MONETİZASYON

### Para Paketleri
```javascript
const PARA_PAKETLERI = [
  { fiyat:0.99,  para:250000    },
  { fiyat:4.99,  para:1500000   },
  { fiyat:9.99,  para:3500000   },
  { fiyat:19.99, para:8000000   },
  { fiyat:49.99, para:25000000  },
  { fiyat:99.99, para:60000000  },
];
```

### Reklam (AdMob)
```
- Server 1: reklam yok
- Server 2+: günde max 25 gönüllü reklam
```

### Top Spender
```javascript
// Aylık harcama sıralaması — ilk 5'e ödül
const TOP_SPENDER_ODUL = {
  1: { para:10000000, odul:'T5 BG + özel unvan + T5 nadir item' },
  2: { para:5000000,  odul:'T5 BG + özel rozet'                 },
  3: { para:2000000,  odul:'T5 BG + T4 BG'                      },
  4: { para:1000000,  odul:'T5 BG'                               },
  5: { para:500000,   odul:'T5 BG'                               },
};

// Milestone ödülleri (harcama bazlı, 1 kez):
const MILESTONE = [
  { hedef:0.99,  odul:'$100K'                  },
  { hedef:4.99,  odul:'$500K'                  },
  { hedef:9.99,  odul:'$1M + T2 BG kafası'     },
  { hedef:19.99, odul:'$2M + T3 BG + rozet'    },
  { hedef:49.99, odul:'$5M + T4 BG + unvan'    },
  { hedef:99.99, odul:'$10M + T5 BG + nadir item' },
];
```

---

## EVENTS SİSTEMİ

### Günlük Giriş Ödülleri
```javascript
const GUNLUK_ODUL = {
  1:5000,   2:10000,  3:20000,  4:30000,  5:40000,
  6:50000,  7:60000,  8:70000,  9:80000,  10:85000,
  11:90000, 12:95000, 13:100000,
  14: { para:200000, bonus:'T4 BG kafası' },
  15: { para:250000, bonus:'T5 BG kafası' },
};
// Gün atlanırsa sıfırlanır
// VIP çarpanı sadece paraya uygulanır (kafaya değil)
```

### Günlük VIP Sandıkları
```javascript
// Sandık 1 (herkese açık): 40 VIP puanı
// Sandık 2 (günlük görevi tamamlayana): 60 VIP puanı
```

### Günlük Görev Puanları (toplam 100)
```javascript
const GUNLUK_GOREV = {
  giris:     10,
  offender:  5,
  wheelman:  5,
  insidejob: 10,
  armedrob:  12,
  bustout:   5,
  seyahat:   5,
  kacakcilik:8,
  felony:    25,
  kill:      15,
};
// 100 puana ulaşınca Sandık 2 açılır
```

### Görev Sandık Ödülleri
```javascript
const GOREV_SANDIK = {
  20:  2000,
  40:  5000,
  60:  10000,
  80:  25000,
  100: { para:100000, bonus:'T4 BG kafası' },
};
```

### Haftalık Sıralama Ödülleri
```javascript
// 4 kategori: en çok suç | en çok kill | en çok kaçakçılık | en çok bustout
const HAFTALIK_ODUL = {
  1: 5000000,
  2: 3000000,
  3: 1000000,
};
```

### Aylık Görevler
```javascript
const AYLIK_GOREVLER = [
  { görev:'30 gün üst üste giriş',    odul:15000  },
  { görev:'Offender: 4.000',          odul:60000  },
  { görev:'Wheelman: 2.000',          odul:55000  },
  { görev:'Inside Job: 700',          odul:40000  },
  { görev:'Armed Robbery: 60',        odul:75000  },
  { görev:'Felony: 25',               odul:100000 },
  { görev:'Bustout: 30',              odul:30000  },
  { görev:'Kaçakçılık: 1.000',        odul:70000  },
  { görev:'Kill: 1',                  odul:5000   },
  { görev:'Seyahat: 25',              odul:20000  },
  { görev:'Auction'da item sat: 5',   odul:10000  },
  { görev:'Poligon: 2.000',           odul:50000  },
];

// Tüm aylık görevleri tamamlayana:
const AYLIK_BUYUK_ODUL = {
  para:   300000,
  bonus1: '10× T5 BG kafası',
  bonus2: '1× T5 Bodyguard',
};
```

### Aylık Sıralama Ödülleri
```javascript
// Aynı 4 kategori
const AYLIK_SIRALAMA_ODUL = {
  1: { para:2000000, bonus:'T5 BG kafası + 500 VIP puan' },
  2: { para:1000000, bonus:'T4 BG kafası + 250 VIP puan' },
  3: { para:500000,  bonus:'T3 BG kafası + 100 VIP puan' },
};
```

---

## SOSYAL SİSTEM

### Evlilik
```javascript
// Rank Mobster+ her iki taraf için
// Kayıtta cinsiyet seçilir
// Evlilik bonusu: +%2 savunma | Eşin villası varsa +%5
// Ölünce: banka %50 + arabalar → eşe (vasiyet 2. önceliği)
```

### Villa Sistemi
```javascript
// Rank 13 (Crew Chief) ile alınır
// Her villa +%0.3 defence bonus (max 40 villa → +%12)
// Aktif villa: +%3 | Aile HQ villası: +%3
// 40 villa tamamlama: +%5
// MAX villa bonus: +%23

// TAM SAVUNMA MAX BONUS:
// +%23 (villa) + %5 (evlilik) + %20 (Godfather) = +%48
```

### Profil
```javascript
// Oyuncu profil resmi yükler (karakter ekranından)
// Admin moderasyonu — uygunsuz kaldırılır
// Başkasının profilinde görünenler:
//   Nick | Rank | Para | Aile | Profil resmi
//   Mesaj gönder | Hitlist koy | Arkadaş ekle
// Görünmeyenler: Kill sayısı | Mermi | Online/offline
```

### Profil Kartı Paylaşımı
```javascript
// Karakter ekranından paylaşılır
// Platform: Instagram | Facebook | WhatsApp | Genel
// Ödül (her platform 1 kez): Instagram/Facebook/WhatsApp → $2.500.000
//                             Profil kartı paylaşımı → $2.500.000
//                             Diğer → $1.000.000
```

### Mesaj Sistemi
```javascript
// Oyuncular arası mesaj
// Sistem mesajları da aynı inbox'ta (hapis, saldırı, witness report)
// Mesaj hem inbox'a düşer hem ekranda toast/banner çıkar (kimden geldiği yazar)
// Admin duyuruları: hem ticker'da hem inbox'ta
// Okundu/okunmadı işareti var
```

### Chat
```javascript
// FLOAT BUTON:
// position:fixed; left:12px; bottom:76px
// 50×50px daire | background:#fff | border:2px solid #111
// İkon: sohbet_balonu.png (30px) | fallback: 💬
// Okunmamış badge: kırmızı, sağ üst köşe
// Her ekranda görünür — Ölüm/Hapis/Tutorial/Sığınak'ta GİZLENİR

// PANEL:
// Soldan slide-in | genişlik:%80 (max 300px) | tam yükseklik
// border-right:2px solid #111
// Header: background:#111 | CHAT yazısı #C9A84C | ✕ butonu #C9A84C

// 3 SEKME: AİLE | SERVER | GLOBAL
// Arka plan: beyaz | Yazı: siyah bold 12px
// PNG ikonlar sekme üstünde (18px): sohbet_aile.png | sohbet_server.png | sohbet_global.png
// Aktif sekme: alt kırmızı çizgi (3px solid #c62828) | pasif: şeffaf + opacity:0.6
// Çerçeve YOK

// MESAJLAR:
// Nickname: kırmızı (#c62828) + bold 10px
// Kendi mesajlar: sağda, background:#111, renk:#fff
// Diğerleri: solda, background:#f5f5f5, renk:#111
// Balon border-radius: 12px

// INPUT:
// max 100 karakter | border-radius:20px
// Gönder butonu: beyaz bg | turuncu çerçeve (#C9A84C) | turuncu ok ➤
// Küfür filtresi aktif → yasaklı kelimeler *** olur

// ASSET'LER:
// sohbet_balonu.png  ✅
// sohbet_aile.png    ✅
// sohbet_server.png  ✅
// sohbet_global.png  ✅
```

### Ban/Kick
```javascript
// Admin tarafından uygulanır
// Kick: oyundan atılır, tekrar girebilir
// Ban: hesap kapatılır (süreli veya kalıcı)
// Kişiye bildirim gönderilir
```

### Günlük Giriş & Sosyal
```javascript
const GUNLUK_ODULLER_GUNLUK = {
  // Para ödülleri + gün 14: T4 BG kafası, gün 15: T5 BG kafası
  // Gün atlanırsa sıfırlanır
};
```
---

## TUTORIAL

```
Yeni oyuncu kaydolunca otomatik başlar.
O ranka ait açık olan her şeyi sırayla yaptırır:
1. Suç işle (Offender)
2. Hapse düş → kefalet öde
3. Bustout dene
4. Kaçakçılık yap
5. Casino gir
6. Poligona gir (KS)
7. BG tak (Defence)
8. Aile sayfasına bak

Her adımda ekranda yönlendirme ok/highlight gösterilir.
Tamamlanınca bir daha açılmaz.
```

---

## GÖRSEL EFEKTLER

### Float Efektleri
```javascript
const FLOAT_COLORS = {
  para:    '#2a7a3a',   // yeşil  — $+500
  xp:      '#f97316',   // turuncu — +50 XP
  ks:      '#c62828',   // kırmızı — +0.01 KS
  defence: '#111111',   // siyah  — +500 DEF
  suruş:   '#3b82f6',   // mavi   — +0.01 SÜRÜŞ
  bustout: '#C9A84C',   // sarı   — +0.01 BUSTOUT
};
// Sırayla çıkar — biri bitmeden diğeri başlamaz
// Suç/aksiyon sonrası: sonuç ekranı → ardından float'lar
// Kullanım: spawnFloat('para', '+$500') | spawnFloat('xp', '+150 XP')
// Font: Bebas Neue 18px | Animasyon: 1.1sn yukarı kayarak solar
// Ekran ortasında çıkar
```

### Rank Atlama
```
- Beyaz arka plan, tüm menüler gizlenir
- Yeni rankın hayvan PNG'si küçükten büyüye (pop animasyonu)
- Altın halkalar yayılır
- Altın konfeti patlar
- Rank adı + numarası belirir
- [DEVAM ET] butonu
```

### Kill Efekti
```
Ekranda kısa kırmızı flash + titreme (haptic)
```

### Ölüm Ekranı
```
Ekran kararır (tam ekran, tüm menüler gizlenir)
Skull animasyonu (PNG/GIF)
Öldüren + rank + şehir bilgisi
```

### Hapis Efekti
```
Popup veya ekranda parmaklık animasyonu (GIF)
```

### Crusher Aktifken
```
BottomBar'da Crusher butonu pulse/yanıp söner
```

### Ticker
```
Gerçek zamanlı oyun olayları:
- Kill: "[OYUNCU_A] — Rank X — [ŞEHİR]'da öldürüldü."
  KATİL BİLGİSİ ASLA YAZILMAZ — gizli bilgi
- Şehir kontrolü değişince
- Rank atlayınca
- Admin duyuruları
- Jackpot (casino)
- Yeni üye kaydı
- Yeni aile kuruldu

Ticker tasarımı:
- Font: Oswald 400 11px #111 — bold DEĞİL; alıntılar italic #888
- Sol köşe: sabit 🟢 online sayısı (ticker_online-num) — kayan yazının önünde
- Her haber arası: ticker_ayrac.png (10px) — class: ticker-ayrac
  CSS filter: brightness(0) saturate(100%) invert(28%) sepia(89%) saturate(600%) hue-rotate(115deg) brightness(0.8) !important
  (koyu yeşil — brightness(0) ile PNG rengi bağımsız çalışır)
- Ölüm haberleri: death.png (14px) | NICK — Rank — Şehir'de öldürüldü. | death.png
- Online sayısı değişince badge anlık güncellenir, ticker'a ayrı haber düşmez

Ticker dönen alıntılar & puf noktaları (oyun olayları arasında dönüşümlü gösterilir):
```javascript
const TICKER_QUOTES = [
  // Alıntılar
  "Never interrupt your enemy when he is making a mistake.",
  "Guns. A lot of guns.",
  "The world is yours.",
  // Oyun puf noktaları
  "İyi bir ekiple Felony başarı oranını %140'a çıkarabilirsin.",
  "KS ne kadar yüksekse nişan o kadar isabetli.",
  "Bustout becerisini artırmak için hapse düş ve çık.",
  "Wheelman sana araba kazandırır — garaja bak.",
  "Şehri kontrol eden aile tüm gelirden %5 komisyon alır.",
  "TNT, Felony başarı oranına +%3 katkı sağlar.",
  "Inside Job'da iyi bir şoför başarı şansını artırır.",
  "Armed Robbery'de item drop şansın T2:%20, T5:%0.2.",
  "Rank atlamak için suç sayısı, mermi ve kill şartları var.",
  "Kefalet ödemek yerine Bustout daha ucuza gelebilir.",
  "Aynı anda birden fazla bina satın alarak şehri kontrol et.",
];
// Ticker'da oyun haberleri ile alıntılar dönüşümlü gösterilir
// Her alıntı italik, hafif gri renkte (#888) gösterilir
```

Gazete (GZ) oto-haber fonksiyonları — backend tetikler:
- gzOlumHaberi(oldurulen, rank, sehir) — katil bilgisi parametre olarak alınmaz, gösterilmez
- gzJackpotHaberi(nick, rank, miktar, oyun)
- gzYeniUyeHaberi(nick, sehir)
- gzYeniAileHaberi(aileAdi, boss, sehir)
- gzOnlineGuncelle(sayi)
Her fonksiyon hem Gazete popup'ına hem Ticker'a ekler.
```

### Hava Durumu & Gece/Gündüz
```
- Sadece şehir haritası ekranında aktif
- Gece/gündüz döngüsü
- Yağmur efekti (şehir haritasına özel)
```

### Skeleton Loading
```
Suç popupları     → Matrix efekti (şeffaf, beyaz karakterler, 700ms) → popup fade+scale
Diğer popuplar   → Açık siyah skeleton shimmer (koyu gri tonlar, 1.1sn) → içerik belirir
```

---

## GÖRSEL EFEKTLER — ÖZEL DURUMLAR

```javascript
// Araba yarışında:
// - Seçilen arabanın PNG'si ekranda görünür
// - Sanki gidiyormuş gibi animasyon efekti

// Ülkeye/şehire haritada basınca:
// - GIF bir kez oynar → içerik açılır
```

---

## SES & HAPTİK

```javascript
const HAPTIC = {
  attack:    'Medium',
  hit:       'Error',
  death:     'Error',
  rankUp:    'Success',
  tier5Equip:'Heavy',
  bigWin:    'Success',
  crimeSuccess:'Light',
  insidejobDone:'Success',
};

const MUSIC_SCREENS = {
  default:      'music_main.mp3',
  casino:       'music_casino.mp3',
  bina_open:    'music_buildings.mp3',
};

// Müzik dosyaları (underground reposu):
// BASE: https://raw.githubusercontent.com/mericaltinors1983-max/underground/main/
// music_main      → Till Paradiso - Be Part of My Universe (TP 024).mp3
// music_casino    → Sneaky Snitch.mp3
// music_buildings → Dark Fog.mp3

// SFX dosyaları (underground reposu):
// sfx_click.mp3   sfx_success.mp3   sfx_fail.mp3
// sfx_rankup.mp3  sfx_kill.mp3      sfx_money.mp3

// SOUND MANAGER (smPlayMusic / smPlaySfx / smToggleMusic / smToggleSfx):
// - İlk dokunuşta aktif olur (mobil browser kısıtı)
// - Casino ekranında → Sneaky Snitch otomatik
// - Bina popupunda  → Dark Fog otomatik
// - Ekranlar arası smooth fade in/out (0.45 max volume)
// - SFX pool: aynı ses üst üste çalabilir
// - Ayarlar: TopNav AYARLAR → müzik/sfx toggle + şu an çalan gösterir
// - Ses ve haptic ayarlardan ayrı ayrı kapatılabilir
```

### localStorage Anahtarları
```
lf_tut_done   : '1' → tutorial tamamlandı, bir daha açılmaz
lf_music      : '0' → müzik kapalı | '1' veya yok → açık
lf_sfx        : '0' → sfx kapalı  | '1' veya yok → açık
```

---

## KARİYER EKRANI (Karakter)

```javascript
// Orta ekranda açılır (tam ekran değil, menüler görünür)
// 5 sekme:
const KARAKTER_SEKMELER = ['KARAKTER', 'ENVANTER', 'VILLA', 'PERSONALS', 'GARAJ'];

// KARAKTER sekmesi:
// - Üstte profil resmi (tıklayınca değiştirilebilir)
// - Altında rank hayvanı PNG
// - Nick, rank adı, aile
// - Stats: KS, DEF, XP, sürüş becerisi, bustout becerisi
// - Equipped items + BG slotları
// - Backfire ayarı
// - Vasiyet butonu (nick yazma, anlık kontrol)
// - Arkadaşlar listesi

// GARAJ sekmesi:
// - Tüm arabalar listelenir
// - Inside Job'a katılırken buradan araba seçilir
// - Crusher için buradan araba gönderilir
```

---

## PROTOTYPE DURUMU

| Bileşen | Durum |
|---|---|
| AppShell (TopBar/Nav/BottomBar) | ✅ |
| Dünya + Ülke + Şehir Haritası | ✅ |
| Building Popupları | ✅ |
| Offender | ✅ |
| Armed Robbery | ✅ |
| Inside Job | ✅ |
| Felony | ✅ |
| Bustout | ✅ |
| Kaçakçılık | ✅ |
| Market | ✅ |
| Karakter Ekranı | ✅ |
| Items/Envanter | ✅ |
| Villa | ✅ |
| Marriage | ✅ |
| Casino | ✅ |
| Banka | ✅ |
| VIP | ✅ |
| Settings | ✅ |
| Notification | ✅ |
| Store (Satın Alma) | ✅ |
| Events | ✅ |
| Top Spender | ✅ |
| Safe House | ✅ |
| Travel Banner | ✅ |
| Attack Popup | ✅ |
| Death Screen | ✅ |
| Hitlist | ✅ |
| Profile Share | ✅ |
| Poligon 1 (Joystick) | ✅ |
| Poligon 2 (Tap / Hareketli) | ✅ |
| Splash Screen | ✅ |
| Wheelman | ✅ (yeni tasarım) |
| Araba Yarışı | ✅ |
| Chat | ✅ |
| Crusher | ✅ |
| Gazete | ✅ |
| Tutorial | ✅ |
| Rank Up Ekranı | ✅ (demo) |
| Matrix Popup Efekti | ✅ (demo) |
| Gold Shimmer Skeleton | ✅ (demo) |
| SoundManager | ✅ |


---

## ASSET LİSTESİ — LaFamilia GitHub Pages

**BASE_URL:** `https://mericaltinors1983-max.github.io/LaFamilia/`

### Ürün PNG'leri (10 adet)
```
urun_sigara.png   urun_bira.png    urun_pill.png
blood.png         urun_viski.png   urun_chip.png
dronee.png        urun_altin.png   urun_elmas.png
urun_white.png
```
> NOT: Kan → blood.png | Drone → dronee.png (çift e)

### Şehir PNG'leri (40 adet — city_[id].png)
```
Türkiye : city_istanbul  city_izmir      city_trabzon    city_diyarbakir
İtalya  : city_napoli    city_roma       city_sicilya    city_milano
Rusya   : city_moskova   city_stpetersburg city_kazan    city_vladivostok
Almanya : city_hamburg   city_berlin     city_munih      city_frankfurt
ABD     : city_newyork   city_chicago    city_miami      city_lasvegas
Meksika : city_tijuana   city_mexicocity city_guadalajara city_monterrey
Kolombiya: city_medellin city_bogota     city_cartagena  city_cali
Brezilya: city_saopaulo  city_rio        city_salvador   city_fortaleza
Japonya : city_tokyo     city_osaka      city_yokohama   city_kyoto
Çin     : city_sanghay   city_hongkong   city_shenzhen   city_pekin
```

### Rank Hayvanı PNG'leri (14 adet)
```
rank_animal_1.png  → Fare        (Street Rat)
rank_animal_2.png  → Tavşan      (Runner)
rank_animal_3.png  → Tilki       (Hustler)
rank_animal_4.png  → Maymun      (Crook)
rank_animal_5.png  → Yaban Domuzu (Thug)
rank_animal_6.png  → Yılan       (Gangster)
rank_animal_7.png  → Kobra       (Enforcer)
rank_animal_8.png  → Kurt        (Operator)
rank_animal_9.png  → Köpekbalığı  (Hitman)
rank_animal_10.png → Çita        (Underboss)
rank_animal_11.png → Timsah      (Strategist)
rank_animal_12.png → Kaplan      (Boss)
rank_animal_13.png → Kartal      (Crew Chief)
rank_animal_14.png → Aslan       (Godfather)
```

### Kaçakçılık Kanal Asset'leri
```
Seçim ekranı (sc-kk-main):
  kacak_normal.png   — NORMAL mod kartı
  icon_auto.png      — AUTO mod kartı

Seçim ekranı (sc-kk-kanal):
  icon_konteyner.png — TREN kartı (seçim görseli)
  harbour.png        — GEMİ kartı (seçim görseli)
  icon_airport.png   — UÇAK kartı (seçim görseli)

Trade banner GIF'leri:
  kacak_konteyner.gif — TREN aktif banner ikonu
  cargo-ship.gif      — GEMİ aktif banner ikonu
  kacak_airport.gif   — UÇAK aktif banner ikonu
  time.gif            — Sayaç yanındaki saat animasyonu
```

### Poligon Asset'leri
```
target.png          — POLİGON 1 seçim kartı
shooting-target.png — POLİGON 2 seçim kartı
```

---