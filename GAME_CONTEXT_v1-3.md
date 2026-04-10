# GAME CONTEXT — GAME_CONTEXT_v1
# LA FAMILIA / UNDERGROUND — TAM OYUN TASARIM DOKÜMANI
> Versiyon: v1.3.0 — GC_1 v3-5-18 + GC_2 v3-5-17 + GC_3 v3-6-8 + GC_4 v3-6 birleşimi + SoundManager + bug fixes
> Platform: React Native (iOS + Android) — Portrait locked
> Bu dosya canonical source of truth'tur. Tüm prototype ve popup dosyaları buna göre senkronize edilir.

---

## GENEL TEKNİK KURALLAR

```
Platform        : React Native (Expo veya bare RN)
Yönelim         : Portrait only → ScreenOrientation.lockAsync(PORTRAIT_UP)
Dil             : Uygulama dili İngilizce, UI metinleri UPPERCASE
Font ailesi     : CorleoneDue (ana) + Cinzel (popup başlık) + Bebas Neue (sayılar) + Space Mono (etiket) + Oswald (gövde)
Font URL        : https://mericaltinors1983-max.github.io/hustler/CorleoneDue-Wp8v.ttf
Ana arka plan   : #ddeef7
Kart arka planı : #ffffff
Vurgu rengi     : #111111
Altın           : #C9A84C / #B8860B
Border          : 1px solid #e0e0e0
Border radius   : 2px (popup) | 12px (kartlar)
Tier renkleri   : T1 #888  T2 #22c55e  T3 #3b82f6  T4 #a855f7  T5 #C9A84C
```

---

## ASSETS — PNG URL'LERİ

```javascript
const BASE = 'https://mericaltinors1983-max.github.io/hustler/';
```

### Rank Hayvanları
| Dosya | Rank | Hayvan |
|-------|------|--------|
| rank_animal_1.png  | 1  | Fare           |
| rank_animal_2.png  | 2  | Tavşan         |
| rank_animal_3.png  | 3  | Tilki          |
| rank_animal_4.png  | 4  | Maymun         |
| rank_animal_5.png  | 5  | Yaban Domuzu   |
| rank_animal_6.png  | 6  | Yılan          |
| rank_animal_7.png  | 7  | Kobra          |
| rank_animal_8.png  | 8  | Kurt           |
| rank_animal_9.png  | 9  | Köpekbalığı    |
| rank_animal_10.png | 10 | Çita           |
| rank_animal_11.png | 11 | Timsah         |
| rank_animal_12.png | 12 | Kaplan         |
| rank_animal_13.png | 13 | Kartal         |
| rank_animal_14.png | 14 | Aslan          |

### Ülke Bayrakları
```
country_turkey.png   country_usa.png      country_russia.png
country_italy.png    country_mexico.png   country_china.png
country_germany.png  country_colombia.png country_japan.png
country_brazil.png
```

### Şehir İkonları (40 adet ✅)
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
bina_airport.png    ✅  bina_port.png       ✅  bina_bank.png       ✅
bina_ammofab.png    ✅  bina_lab.png        ✅  bina_whiskey.png    ✅
bina_diamond.png    ✅  bina_gold.png       ✅  bina_tobacco.png    ✅
bina_drone.png      ✅  bina_pharmacy.png   ✅  icon_pawn.png       ✅
icon_mall.png       ✅  building_casino.png ✅  building_otel.png   ✅
building_bira_fab.png ✅ building_bar.png  ✅  building_hastane.png ✅
building_hapishane.png ✅ building_poligon.png ✅ building_gar.png ✅
building_gym.png    ✅  bina_chip.png       ⏳
```

### Prototype Geçici PNG Mapping
```
building-t.png → liman       building-d.png → banka       building-h.png → hapishane
building-q.png → casino      building-k.png → mermi_fab   building-e.png → labaratuvar
building-b.png → otel        building-l.png → bira_fab    building-s.png → bar
building-a.png → avm         building-p.png → pawn_shop   building-i.png → hastane
building-r.png → viski_fab   building-n.png → elmas_fab   building-m.png → altin_fab
building-f.png → sigara_fab  building-g.png → drone_fab   building-j.png → eczane
building-c.png → chip_fab
```

### UI / Nav / Stat İkonları
```
icon_bank.png ✅  icon_settings.png ✅  icon_ammofab.png ✅  icon_mall.png ✅
icon_smuggle.gif ✅  icon_travel.gif ✅  icon_oc.gif ✅  icon_pawn.png ✅
back_btn.png ✅  close_icon.png ✅  megaphone.png ✅  icon_info.png ✅
nav_character.png ✅  nav_items.png ✅  nav_family.png ✅  nav_events.png ✅
nav_message.png ✅  nav_notification.png ✅  nav_casino.png ✅
nav_pawnshop.png ✅  nav_lab.png ✅
icon_airport.png ✅  icon_konteyner.png ✅  icon_port.png ✅
icon_auto.png ✅  icon_sell.png ✅  kacak_auto.png ✅  kacak_normal.png ✅
stat_can.png ✅  stat_def.png ✅  stat_ks.png ✅  stat_money.png ✅
stat_xp.png ✅  letter-x.png ✅
```

### Casino Assetleri
```
card_spade.png ✅  card_heart.png ✅  card_diamond.png ✅  card_club.png ✅  card_back.png ✅
slot_sym_cherry.png ⏳  slot_sym_lemon.png ⏳  slot_sym_orange.png ⏳
slot_sym_grape.png ⏳  slot_sym_melon.png ⏳  slot_sym_star.png ⏳
slot_sym_gun.png ⏳  slot_sym_money.png ⏳  slot_sym_whisky.png ⏳
slot_sym_diamond.png ⏳  slot_sym_seven.png ⏳  slot_sym_crown.png ⏳
horse_1.png ✅  horse_2.png ✅  horse_3.png ✅
horse_4.png ✅  horse_5.png ✅  horse_6.png ✅
casino_chip_red.png ✅($100)  casino_chip_green.png ✅($500)  casino_chip_blue.png ✅($1K)
casino_chip_purple.png ✅($5K)  casino_chip_gold.png ✅($10K)
```

### Diğer Sahne / Item PNG
```
inside_job_h1–h8.png ✅   oc_o1.png ✅  oc_o2.png ✅
silah_t1_01 → silah_t5_10 ✅ (50 adet)
yelek_t1_base → yelek_t5_base ✅ (5 adet)
suit_t1_base → suit_t5_base ✅ (5 adet)
canta_t1_01 → canta_t5_10 ✅ (50 adet)
kolye_t1_base → kolye_t5_base ✅ (5 adet)
yuzuk_base.png ✅  witness_report.png
```

---

## UI / APP SHELL

### Genel Layout
```
┌─────────────────────────────────────┐
│         TopBar — Stats (44px)       │
├─────────────────────────────────────┤
│     TopNav — 7 ikon, yatay (42px)  │
├─────────────────────────────────────┤
│                                     │
│         MainContent                 │
│      (switchScreen ile değişir)     │
│                                     │
├─────────────────────────────────────┤
│         BottomBar (48px)            │
└─────────────────────────────────────┘
```
- Tüm arka plan: `#ddeef7`
- Açılışta MainContent = MapScreen
- Sol panel YOK
- TopBar + TopNav + BottomBar şu ekranlarda **GİZLENİR**: Ölüm | Hapis | Tutorial | Sığınak

### TopBar (44px)
```
Sol blok: RANK ADI (CorleoneDue 7px) | [██████░░] XP bar (2px, #22c55e/#e0e0e0)
          ❤ 85  💰 47K  🔫 320 (6.5px) | ŞEHİR (6px) | min-width:72px, border-right
Orta:     Ticker — kayan gazete metni, 10px CorleoneDue, megaphone.png önünde
Sağ:      Arama + Mesaj + Bildirim (3 ikon) | bildirim badge | border-left
```

### TopNav (42px)
```javascript
const TOP_NAV = [
  { id:'karakter',   screen:'karakter'   },
  { id:'map',        screen:'ulkeler'    },
  { id:'kacakcilik', screen:'kacakcilik' },
  { id:'seyahat',    screen:'seyahat'    },
  { id:'casino',     screen:'casino'     },
  { id:'banka',      screen:'banka'      },
  { id:'market',     screen:'market'     },
];
// İkon 22px | Aktif: border-bottom 2px solid #111 | Pasif: #444
```

### BottomBar (48px)
```javascript
const BOTTOM_BTNS = [
  { id:'offender',    label:'OFFENDER',    side:'left'  },
  { id:'insidejob',   label:'INSIDE JOB',  side:'left'  },
  // hustler_logo ortada — 96px, tıklanamaz
  { id:'ulkeler',     label:'MAP',         side:'right' },
  { id:'bustout',     label:'BUSTOUT',     side:'right' },
  { id:'kacakcilik',  label:'KAÇAKCILIK',  side:'right' },
];
// Aktif: #C9A84C (label + ikon)
```

### Popup Stili (Tüm Popup'lar)
```css
/* KONUM & BOYUT */
position: fixed;
bottom: 116px;
left: 50%;
transform: translateX(-50%);
width: 320px;
height: 520px;
z-index: 10001;
background: #fff;
border: 3px double #111;
border-bottom: none;
overflow: hidden;

/* OVERLAY */
position: fixed; inset: 0;
background: rgba(0,0,0,0.65);
z-index: 10000;
/* tıklanınca closePop() */

/* AÇILIŞ ANİMASYONU */
/* .open class eklenir */
@keyframes su {
  from { transform: translateX(-50%) translateY(520px); }
  to   { transform: translateX(-50%) translateY(0); }
}
/* animation: su 0.25s cubic-bezier(0.4, 0, 0.2, 1) */

/* HEADER (44px) */
height: 44px;
border-bottom: 3px double #111;
/* Sol  : gif ikonu 28x28px — boşsa visibility:hidden */
/* Orta : lafamilia-2.png absolute centered, height:36px */
/* Sağ  : info_btn + close_btn, her biri 22x22px */

/* CLOSE-BAR */
border-top: 3px double #111;

/* ZOOM + SCROLL YOK */
/* viewport: maximum-scale=1, user-scalable=no */
/* popup: overflow:hidden */

/* FONT STANDARDI */
Normal metin       : Oswald 700, 13px, #111
Büyük değer/başlık : Oswald 700, 20–22px, #111 (açık bg) | #C9A84C (koyu bg)
Küçük etiket       : Oswald 600, 10px, #888
Bölüm etiketi      : Oswald 700, 11px, #B8860B, letter-spacing:1.5px
Sekme              : Oswald 700, 11px, letter-spacing:1px
Aktif sekme        : color:#111, border-bottom:2px solid #111
Pasif sekme        : color:#999
Primary buton      : background:#111, color:#fff, Oswald 700, letter-spacing:2px
Danger buton       : background:#fff, color:#8B3030, border:1px solid #e0c0c0

/* RENK SİSTEMİ — DURUM BAZLI */
Yeşil  #2a7a3a  → iyi / ucuz / başarılı
Altın  #C9A84C  → orta / dikkat / değer
       #B8860B  → bölüm etiketleri / bar dolgu
Kırmızı #c62828 → tehlike / kayıp / hata
Rank rozet      → r1: gold-gradient | r2: #888 | r3: #a0522d
```

### switchScreen(id)
```javascript
function switchScreen(id) {
  // 1. Tüm .screen gizle  2. #screen-{id} göster
  // 3. BottomBar active güncelle
  // 4. Lazy init: market→mktInitScreen() | aktivite→renderAktivite()
}
```
| id | İçerik |
|---|---|
| `ulkeler` | Dünya + Ülke haritası (açılış) |
| `karakter` | Karakter / Profil |
| `envanter` | Items / Envanter |
| `family` | Aile |
| `offender` | Offender popup |
| `insidejob` | Inside Job popup |
| `felony` | Felony popup |
| `bustout` | Bustout popup |
| `kacakcilik` | Kaçakçılık ekranı |
| `market` | Market |
| `aktivite` | Aktivite |
| `banka` | Banka |
| `casino` | Casino |
| `seyahat` | Seyahat |

---

## HARİTA

### 3 Katman
- **Katman 1 — Dünya:** D3 NaturalEarth1 projeksiyonu; 10 ülke renkli, diğerleri `#cccccc`; Antarktika (id:10) ve Taiwan (id:158) gösterilmez
- **Katman 2 — Ülke + Voronoi:** Şehirler Voronoi ile aile bölgelerine ayrılır; bölge aile rengiyle boyanır; şehir + aile adı overlay; Back → Katman 1
- **Katman 3 — Şehir + Binalar:** 22 bina PNG + isim; bina tıklayınca BuildingPopup; "TRAVEL HERE" → switchScreen('seyahat'); BACK sol altta → Katman 2

```javascript
const COUNTRY_COLORS = {
  '792':'#E30A17', '380':'#009246', '276':'#FFCC00',
  '643':'#003DA5', '156':'#DE2910', '392':'#BC002D',
  '840':'#3C3B6E', '484':'#006847', '76':'#009C3B', '170':'#FCD116',
};
```

### Şehir Kontrol Sistemi
```
Bir aile şu 4 noktayı kontrol ederse şehir onların:
  1. Bullet Factory (mermi_fab)
  2. Casino
  3. Herhangi 2 pasif gelir binası (Pawn / Pharmacy / Gym / Hotel / Bar)

Kontrol kazanılırsa:
  → Haritada şehir rengi aile rengine döner
  → +%5 savunma bonusu (aile üyelerine)
  → Şehirdeki her binadan %10 komisyon
```

### 10 Ülke 40 Şehir
```javascript
const COUNTRY_DATA = [
  { id:'turkey',   cities:[
    { id:'istanbul',   liman:true  },
    { id:'izmir',      liman:true  },
    { id:'diyarbakir'              },
    { id:'trabzon',    liman:true  },
  ]},
  { id:'italy',    cities:[
    { id:'napoli',  liman:true, ozel_banka:true   },
    { id:'sicilya', liman:true, ozel_casino:true  },
    { id:'milano'                                  },
    { id:'roma',    liman:true                    },
  ]},
  { id:'usa',      cities:[
    { id:'newyork', liman:true, ozel_mermi:true, ozel_liman:true, ozel_casino:true },
    { id:'chicago', liman:true, ozel_mermi:true  },
    { id:'lasvegas',             ozel_casino:true },
    { id:'miami',   liman:true, ozel_airport:true },
  ]},
  { id:'russia',   cities:[
    { id:'moskova'                              },
    { id:'stpetersburg', liman:true            },
    { id:'kazan'                               },
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
    { id:'berlin'                              },
    { id:'hamburg', liman:true, ozel_liman:true, ozel_bira:true },
    { id:'munih'                               },
    { id:'frankfurt'                           },
  ]},
  { id:'brazil',   cities:[
    { id:'rio',      liman:true },
    { id:'saopaulo', liman:true },
    { id:'salvador'             },
    { id:'fortaleza'            },
  ]},
];
```

### Liman Şehirleri (Sabit)
```javascript
const LIMAN_SEHIRLER = [
  'istanbul','izmir','trabzon',
  'napoli','sicilya','roma',
  'newyork','chicago','miami',
  'stpetersburg','vladivostok',
  'cartagena','tijuana',
  'tokyo','osaka','yokohama',
  'sanghay','hongkong','shenzhen',
  'hamburg','rio','saopaulo',
];
```

### Özel Şehir Bonusları
```javascript
const BINA_SPECIAL = {
  'medellin_labaratuvar':  { bonus:'3x ÜRETİM',    desc:'900 White/saat'          },
  'chicago_mermi_fab':     { bonus:'1.3x ÜRETİM',  desc:'2.600/saat'              },
  'mexicocity_mermi_fab':  { bonus:'1.2x ÜRETİM',  desc:'2.400/saat'              },
  'newyork_mermi_fab':     { bonus:'1.1x ÜRETİM',  desc:'2.200/saat'              },
  'hamburg_bira_fab':      { bonus:'1.5x ÜRETİM',  desc:'1.500 Bira/saat'         },
  'vladivostok_altin_fab': { bonus:'2x ÜRETİM',    desc:'400 Altın/saat'          },
  'sanghay_elmas_fab':     { bonus:'2x ÜRETİM',    desc:'200 Elmas/saat'          },
  'lasvegas_casino':       { bonus:'SINIRSIZ BAHİS',desc:'Kasa limiti kadar'       },
  'sicilya_casino':        { bonus:'%3 KOMİSYON',  desc:'Her bahsin %3ü sahibine' },
  'newyork_casino':        { bonus:'%3 KOMİSYON',  desc:'Her bahsin %3ü sahibine' },
  'newyork_liman':         { bonus:'+%10 SATIŞ',   desc:'Port malları %10 yüksek' },
  'hamburg_liman':         { bonus:'+%20 SATIŞ',   desc:'Port malları %20 yüksek' },
  'istanbul_liman':        { bonus:'-%20 SÜRE',    desc:'Port ticaret süresi %20 kısa' },
  'miami_havalimani':      { bonus:'-%25 SÜRE',    desc:'Airport ticaret %25 kısa'},
  'napoli_banka':          { bonus:'ÖZEL FAİZ',    desc:'6s:%5 / 12s:%7 / 24s:%10'},
};
```

### Bina Listesi (SEHIR_BINALAR — 22 bina)
```javascript
var SEHIR_BINALAR = [
  {id:'havalimani',     name:'HAVALİMANI',  ico:'✈️', png:BASE+'bina_airport.png'      },
  {id:'liman',          name:'LİMAN',       ico:'⚓', png:BASE+'bina_port.png'         },
  {id:'tren_istasyonu', name:'TREN GARI',   ico:'🚂', png:BASE+'building_gar.png'      },
  {id:'banka',          name:'BANKA',       ico:'🏦', png:BASE+'bina_bank.png'         },
  {id:'hapishane',      name:'HAPİSHANE',  ico:'⛓️', png:BASE+'building_hapishane.png'},
  {id:'casino',         name:'CASİNO',      ico:'🎰', png:BASE+'building_casino.png'  },
  {id:'mermi_fab',      name:'MERMİ FAB',   ico:'🔧', png:BASE+'bina_ammofab.png'     },
  {id:'labaratuvar',    name:'LAB',         ico:'🧪', png:BASE+'bina_lab.png'         },
  {id:'otel',           name:'OTEL',        ico:'🏨', png:BASE+'building_otel.png'    },
  {id:'bira_fab',       name:'BİRA FAB',    ico:'🍺', png:BASE+'building_bira_fab.png'},
  {id:'bar',            name:'BAR',         ico:'🍸', png:BASE+'building_bar.png'     },
  {id:'avm',            name:'AVM',         ico:'🏬', png:BASE+'icon_mall.png'        },
  {id:'pawn_shop',      name:'PAWN SHOP',   ico:'💰', png:BASE+'icon_pawn.png'        },
  {id:'hastane',        name:'HASTANE',     ico:'🏥', png:BASE+'building_hastane.png' },
  {id:'viski_fab',      name:'VİSKİ FAB',   ico:'🥃', png:BASE+'bina_whiskey.png'    },
  {id:'elmas_fab',      name:'ELMAS FAB',   ico:'💎', png:BASE+'bina_diamond.png'    },
  {id:'altin_fab',      name:'ALTIN FAB',   ico:'🥇', png:BASE+'bina_gold.png'       },
  {id:'sigara_fab',     name:'SİGARA FAB',  ico:'🚬', png:BASE+'bina_tobacco.png'    },
  {id:'drone_fab',      name:'DRONE FAB',   ico:'🚁', png:BASE+'bina_drone.png'      },
  {id:'eczane',         name:'ECZANE',      ico:'💊', png:BASE+'bina_pharmacy.png'   },
  {id:'gym',            name:'GYM',         ico:'🏋️', png:BASE+'building_gym.png'    },
  {id:'chip_fab',       name:'CHIP FAB',    ico:'⚙️', png:BASE+'bina_chip.png'       },
];
```

### Bina Veri Yapısı (BINA_INFO)
```javascript
const BINA_INFO = {
  // KAMU — satın alınamaz
  havalimani:      { tip:'kamu', desc:'Uçak seyahati + Airport kaçakçılığı' },
  liman:           { tip:'kamu', desc:'Gemi seyahati + Port kaçakçılığı'    },
  tren_istasyonu:  { tip:'kamu', desc:'Tren seyahati + Konteyner kaçakçılığı' },
  banka:           { tip:'kamu', desc:'Para yatır / çek / transfer'         },
  hapishane:       { tip:'kamu', desc:'Bustout hedefi'                      },

  // FABRİKALAR — satın alınabilir
  sigara_fab:  { tip:'fabrika', urun:'Sigara', uretim:'2.000/saat', sahipsizFiyat:3,    binaFiyat:5000000,  rankMin:4 },
  bira_fab:    { tip:'fabrika', urun:'Bira',   uretim:'1.000/saat', sahipsizFiyat:8,    binaFiyat:5000000,  rankMin:5 },
  eczane:      { tip:'fabrika', urun:'Pill',   uretim:'500/saat',   sahipsizFiyat:15,   binaFiyat:6000000,  rankMin:4 },
  hastane:     { tip:'fabrika', urun:'Kan',    uretim:'500/saat',   sahipsizFiyat:85,   binaFiyat:6000000,  rankMin:4, not:'HP iyileştirici + kaçakçılık malı' },
  chip_fab:    { tip:'fabrika', urun:'Chip',   uretim:'400/saat',   sahipsizFiyat:120,  binaFiyat:7000000,  rankMin:6 },
  drone_fab:   { tip:'fabrika', urun:'Drone',  uretim:'300/saat',   sahipsizFiyat:140,  binaFiyat:7000000,  rankMin:7 },
  viski_fab:   { tip:'fabrika', urun:'Viski',  uretim:'750/saat',   sahipsizFiyat:45,   binaFiyat:8000000,  rankMin:7 },
  altin_fab:   { tip:'fabrika', urun:'Altın',  uretim:'200/saat',   sahipsizFiyat:1200, binaFiyat:8000000,  rankMin:8 },
  elmas_fab:   { tip:'fabrika', urun:'Elmas',  uretim:'100/saat',   sahipsizFiyat:2800, binaFiyat:9000000,  rankMin:9 },
  labaratuvar: { tip:'fabrika', urun:'White',  uretim:'300/saat',   sahipsizFiyat:5500, binaFiyat:9000000,  rankMin:9 },
  mermi_fab:   { tip:'fabrika', urun:'Mermi',  uretim:'2.000/saat', sahipsizFiyat:50,   binaFiyat:10000000, rankMin:6, maxPrice:200, not:'Kaçakçılık malı değil' },

  // SATIŞ MAĞAZALARI — satın alınabilir
  // Satış fiyatı = maxPrice × 1.25 (SABİT, sahip değiştiremez)
  // sigara:$8 | bira:$20 | pill:$38 | viski:$113 | white:$13.750
  // chip:$300 | drone:$350 | elmas:$7.000 | altın:$3.000 | kan:$213
  gym:       { tip:'magaza', binaFiyat:2500000, rankMin:4, satar:['Sigara','Bira','Viski','Pill','White']              },
  pawn_shop: { tip:'magaza', binaFiyat:3000000, rankMin:4, satar:['Altın','Elmas','Drone','Chip']                      },
  bar:       { tip:'magaza', binaFiyat:2000000, rankMin:3, satar:['Sigara','Bira','Viski','Pill','White']              },
  otel:      { tip:'magaza', binaFiyat:3000000, rankMin:4, satar:['Sigara','Bira','Viski','Pill','White']              },
  avm:       { tip:'magaza', binaFiyat:5000000, rankMin:5, satar:['Altın','Elmas','Drone','Chip','Sigara','Bira','Viski'] },

  // DİĞER
  casino:  { tip:'diger', satin_al:true,  desc:'Kumar — kayıp %98 sahibine, %2 şehir ailesi' },
  poligon: { tip:'diger', satin_al:false, desc:'KS geliştirme — Yakında'                     },
};
```

### Bina Popup Sistemi (ONAYLANDI ✅)
```
SAHİPSİZ FABRİKA:
  → Sadece [BİNAYI AL] sekmesi — GEREKLİ RANK + SATIN ALMA FİYATI + [BİNAYI SATIN AL]
  → GİZLENENLER: üretim miktarı, ürün tipi, aile komisyonu, stok hero, stat strip
  → SAHİPSİZKEN SALDIRILAMAZ
  → SAHİPSİZKEN üretim DURUR — stok birikmez

BAŞKASININ FABRİKASI:
  → [ÜRÜNİ AL] sekmesi + SALDIR butonu

BENİM FABRİKAM:
  Tab 1 KASA    → kasa bakiyesi + KASAYI ÇEK + BİNAYI SAT
                  GİZLENEN: TAHMİNİ GÜNLÜK GELİR
  Tab 2 MAL     → üretim durumu + fiyat ayarla (serbest input, alt sınır yok)
  Tab 3 SAVUNMA → mermi bar + OTOMATİK 10.000 mermi + MERMİ YÜKLE / ÇEK

FABRİKA BAŞLANGIÇ FİYATI: Sahip alır almaz fiyat = maxPrice (SMUGGLE_PRODUCTS.maxPrice) olur

SAHİPSİZ MAĞAZA:
  → Sadece rank bilgisi + satın alma fiyatı + [BİNAYI SATIN AL]
  → GİZLENEN: SATIŞ HIZI, AİLE KOMİSYONU, sahip bilgisi
  → SAHİPSİZKEN SALDIRILAMAZ

BAŞKASININ MAĞAZASI:
  → Sadece [SALDIR] butonu

BENİM MAĞAZAM:
  Tab 1 KASA    → biriken para + KASAYI ÇEK + BİNAYI SAT
                  GİZLENEN: SAHİP satırı, SATIŞ HIZI, AİLE KOMİSYONU, TAHMİNİ GÜNLÜK GELİR
  Tab 2 MAL     → mevcut stok listesi + MAL İŞLEMİ (dropdown + miktar + YÜKLE / ÇEK)
  Tab 3 SAVUNMA → mermi bar + OTOMATİK 10.000 mermi + MERMİ YÜKLE / ÇEK

SAVUNMA SİSTEMİ:
  → Otomatik 10.000 mermi (%100 KS) — her saldırıda ateşlenir
  → Sahip ek mermi yükleyebilir — otomatikten sonra devreye girer
  → Akıllı ateş: saldırganı öldürmek için minimum mermi kullanılır
  → Saldırgan hayatta kalırsa: bina kasası saldırgana geçer
  → Bina sahibi değişmez — sadece kasa boşalır
  → SAHİPSİZ fabrikaya SALDIRILAMAZ

KAMU BİNALARI (Havalimanı / Liman / Tren Garı / Banka / Hapishane):
  → Ayrı popup — satın alınamaz, saldırılamaz
  Taşıma binaları: [✈️ SEYAHAT] → switchScreen('seyahat') | [📦 KAÇAKCILIK] → kanal
  Hapishane: [⛓️ BUSTOUT] → bustout popup (en uzun kalan üstte, aile üyeleri renkli)

FABRİKA KURALLARI:
  → Oyuncu başına aynı türden MAX 1
  → Depo sınırı YOK
  → Gelir: %10 şehri kontrol eden aile | %90 fabrika sahibi (kontrol yoksa %100 sahibine)
  → Sahip ölürse → fabrika sahipsiz kalır, aynı fiyatla satışa çıkar
```

### Seyahat Sistemi
```javascript
function getSure(mesafe, kanal) {
  const SURELER = {
    konteyner: { ic:10, komsu:15, ayni_kita:20, farkli_kita:25 },
    port:      { ic:8,  komsu:11, ayni_kita:15, farkli_kita:20 },
    airport:   { ic:3,  komsu:6,  ayni_kita:10, farkli_kita:15 },
  };
  return SURELER[kanal][mesafe]; // dakika
}
// Araç: ✈️ tüm şehirler | ⛵ sadece liman şehirleri | 🚂 her şehir
// Mini banner: [🚂 İSTANBUL → İZMİR | ⏱ 08:42 | ❌ İPTAL]
// İPTAL: bilet ücretinin %50 cezası
// Seyahat sırasında saldırıya uğranamaz
```

---

## EKONOMİ

### Kaçakçılık Kanalları
```javascript
const KANALLAR = {
  konteyner: { label:'CONTAINER', rankMin:0, aracSart:false },
  port:      { label:'PORT',      rankMin:4, aracSart:'gemi' },
  airport:   { label:'AIRPORT',   rankMin:7, aracSart:'ucak' },
};
// Port rankMin altı: "RANK 4 REQUIRED" | gemi yoksa: "YOU NEED A SHIP"
// Airport rankMin altı: "RANK 7 REQUIRED" | uçak yoksa: "YOU NEED A PLANE"
```

### 10 Ürün (SMUGGLE_PRODUCTS)
```javascript
const SMUGGLE_PRODUCTS = [
  { id:'sigara', name:'CIGARETTES', emoji:'🚬', rankMin:0,  minPrice:3,    maxPrice:6     },
  { id:'bira',   name:'BEER',       emoji:'🍺', rankMin:0,  minPrice:8,    maxPrice:16    },
  { id:'pill',   name:'PILL',       emoji:'💊', rankMin:0,  minPrice:15,   maxPrice:30    },
  { id:'kan',    name:'BLOOD',      emoji:'🩸', rankMin:0,  minPrice:85,   maxPrice:170,  not:'HP iyileştirici' },
  { id:'viski',  name:'WHISKEY',    emoji:'🥃', rankMin:3,  minPrice:45,   maxPrice:90    },
  { id:'drone',  name:'DRONE',      emoji:'🚁', rankMin:5,  minPrice:140,  maxPrice:280   },
  { id:'chip',   name:'CHIP',       emoji:'⚙️', rankMin:6,  minPrice:120,  maxPrice:240   },
  { id:'altin',  name:'GOLD',       emoji:'🥇', rankMin:8,  minPrice:1200, maxPrice:2400  },
  { id:'elmas',  name:'DIAMOND',    emoji:'💎', rankMin:11, minPrice:2800, maxPrice:5600  },
  { id:'white',  name:'WHITE',      emoji:'💊', rankMin:13, minPrice:5500, maxPrice:11000 },
];
// Kilitli ürünler listede görünür — opacity düşük, tıklanamaz
// Mermi ticaret ürünü DEĞİLDİR
// SAHİPSİZ fabrika fiyatı = minPrice (fix)
```

### Fiyat Mekanizması
```
→ Her 30 dakikada fiyat yenilenir — ekranda sayaç: "PRICES REFRESH IN: XX:XX"
→ Görsel salınım: her saniye ±%5 animasyon (sadece UI efekti)
→ YEŞİL → MIN'e yakın (AL fırsatı) | SARI → Orta | KIRMIZI → MAX'a yakın
```

### 3 Ticaret Modu
```
BUY & SHIP  → Mal al + şehir seç + yola çık
BUY ONLY    → Mal al, envantere koy
SELL STOCK  → Envanterdeki malı bu şehirde sat

Aktif gönderi iptal cezası: kargo değerinin %50'si
Varınca: para otomatik cebe + push notification
```

### Şehir Seçimi (Top 3)
```javascript
function getTop3Cities(currentCityId, kanal) {
  // 1. Aynı ülkedeki başka şehirlerden max kâr eden
  // 2. Komşu ülkeden en yüksek kâr eden
  // 3. Farklı kıtadan max kâr eden
  // Bulunduğum şehir listede ÇIKMAZ
}
```

### Auto Ticaret
```javascript
const AUTO_SARTLAR = {
  konteyner: { npc:'conductor', vipMin:0, aracSart:false }, // Conductor ($1M) zorunlu — VIP gerektirmez
  port:      { npc:'kaptan',    vipMin:3, arac:'gemi'    }, // Gemi + Kaptan + VIP3
  airport:   { npc:'pilot',     vipMin:4, arac:'ucak'    }, // Uçak + Pilot + VIP4
};
// Her kanal 10 sefer yapar, durur (sefer bazlı — süre bazlı değil)
// Auto aktifken o kanalda MANUEL ticaret YAPAMAZ
// Push: "AUTO [TRAIN/SHIP/FLIGHT] STOPPED. 10 trips completed. Tap to restart."
```

### Banka
```javascript
const FAIZ = [
  { sure:6,  oran:0.03, napoliOran:0.05 },
  { sure:12, oran:0.05, napoliOran:0.07 },
  { sure:24, oran:0.07, napoliOran:0.10 },
];
// Süre dolunca otomatik cebe girer
// Max 3 eş zamanlı | Min: $100.000 | Max: sınırsız
// Ölünce bankadaki %50 → Vasiyet sistemine
```

### Casino — 7 Oyun
```javascript
// KASA MEKANİĞİ:
// Sahip kasayı fonlar → oyuncu kaybedince %98 kasaya, %2 şehri kontrol eden aile kasasına
// Oyuncu kazanınca ödeme kasadan → kasa boşalırsa "CASINO CLOSED"
// Jackpot havuzu: slot + rulet paylaşır — başlangıç $500K

// Lucky Fruits (3-reel, 6 sembol: cherry/lemon/orange/grape/melon/star)
const LUCKY_FRUITS_SYMS = [
  { id:'cherry', weight:30, pay:2   }, { id:'lemon',  weight:25, pay:3   },
  { id:'orange', weight:20, pay:4   }, { id:'grape',  weight:12, pay:6   },
  { id:'melon',  weight:7,  pay:10  }, { id:'star',   weight:3,  pay:'JP'},
];

// 5 Reel Deluxe (5-reel, 6 sembol)
const FIVE_REEL_PAYS = {
  gun:    { 3:2,  4:5,  5:10  }, money:  { 3:3,  4:8,  5:15  },
  whisky: { 3:4,  4:10, 5:20  }, diamond:{ 3:6,  4:15, 5:30  },
  seven:  { 3:12, 4:30, 5:60  }, crown:  { 3:20, 4:50, 5:'JP'},
};

// Blackjack: dealer 17'de durur | kazanma bahis×2 | Double Down: ilk 2 kartta | Split: YOK
// Video Poker (Jacks or Better):
const POKER_PAYOUTS = {
  royal_flush:250, straight_flush:50, four_of_kind:25, full_house:9,
  flush:6, straight:4, three_of_kind:3, two_pair:2, jacks_or_better:1,
};
// Rulet: Avrupa (tek sıfır 0-36) | dışarı 2x | numara 36x | %5 jackpot havuzuna
// At Yarışı: 6 at, odds her yarışta random | kazanma: bahis × odds
// Boks: 2 dövüşçü, 6 raunt, odds random | kazanma: bahis × odds

// Bahis butonları (tüm oyunlar): $100 / $500 / $1K / $5K / $10K
```

### Market (NPC Shop + Auction)
```javascript
// NPC ARAÇLAR
const NPC_GEMILER = [
  {tier:1,name:'Rusty Barge',   alis:300000,  slotlar:25 },
  {tier:2,name:'Dark Harbor',   alis:800000,  slotlar:50 },
  {tier:3,name:'Iron Smuggler', alis:2000000, slotlar:90 },
  {tier:4,name:'Black Tide',    alis:4000000, slotlar:140},
  {tier:5,name:'The Leviathan', alis:7000000, slotlar:250},
];
const NPC_UCAKLAR = [
  {tier:1,name:'Green Prop',  alis:500000,   slotlar:40 },
  {tier:2,name:'Red Duster',  alis:1500000,  slotlar:75 },
  {tier:3,name:'Air Courier', alis:3000000,  slotlar:125},
  {tier:4,name:'Sky Liner',   alis:5000000,  slotlar:190},
  {tier:5,name:'Shadow Jet',  alis:10000000, slotlar:250},
];
// Satış: alış × 0.50 | Max 1 gemi, 1 uçak

// NPC PERSONEL — 3 tier, upgrade sistemi (önceki tier kaybolur, tam fiyat ödenir)
// T1: temel | T2: -%10 süre | T3: -%25 süre
const NPC_PERSONEL = [
  {id:'conductor', ch:'KONTEYNER', t1:{fiyat:1000000}, t2:{fiyat:1500000}, t3:{fiyat:3000000}},
  {id:'kaptan',    ch:'PORT',      t1:{fiyat:750000},  t2:{fiyat:2000000}, t3:{fiyat:4000000}},
  {id:'pilot',     ch:'AIRPORT',   t1:{fiyat:1000000}, t2:{fiyat:2500000}, t3:{fiyat:5000000}},
];

// NPC BODYGUARD
const NPC_BG = [
  {tier:1,fiyat:250000, defMax:2000 }, {tier:2,fiyat:600000,  defMax:5000 },
  {tier:3,fiyat:1200000,defMax:12000}, {tier:4,fiyat:2500000, defMax:30000},
  {tier:5,fiyat:5000000,defMax:50000},
];

// NPC MERMİ: 1.000 paket → $1.000.000 (satılamaz)

// AUCTION HOUSE:
// Satılabilir: Yüzük / Kolye / Çanta / Araba / Silah / Mermi(1K paket) / Witness Report
// Witness Report: sadece Auction'da — NPC'ye satılamaz
// Max 10 aktif listing | Süre: 6 saat | Min teklif artışı: %5
// Buyout: başlangıcın min %150si | Anti-snipe: son 60sn teklif → +2dk
// İptal: item geri gelir, 10dk tekrar listeleyemez, fiyat düşürme YOK

// ARABALAR (Sadece Auction — NPC'de yok):
// 50 model, 5 tier × 10 | SADECE Inside Job + OC + Crush'ta kullanılır
// Kaçakçılıkta KULLANILMAZ | Şehirler arası seyahat YAPAMAZ
// T1:$1K–$10K | T2:$11K–$20K | T3:$21K–$30K | T4:$31K–$40K | T5:$41K–$50K
// Satış: alış × 0.50 | T5 arabalarda altın parlama animasyonu
// Crush: Don/Consigliere açar | $1M aile kasası | 30dk | Her araba → 20 mermi
```

### Envanter
```javascript
// 3 sekme: ITEMS / GOODS / BODYGUARDS
const kapasiteHesapla = (p) =>
  p.cantaSlot   // T1:5 T2:10 T3:18 T4:28 T5:40
  + p.suitSlot  // T1:10 T2:20 T3:30 T4:40 T5:50
  + Math.floor(p.level / 10) * 5; // her 10 seviye +5 | MAX: 105 slot
// Envanter kendisi SINIRSIZ — kapasite sadece kaçakçılık seferi için
```

---

## RANK SİSTEMİ

```javascript
const RANKS = [
  { id:1,  name:'Street Rat', xp:0,       chess:'pawn'   },
  { id:2,  name:'Runner',     xp:1000,     chess:'pawn'   },
  { id:3,  name:'Hustler',    xp:3000,     chess:'pawn'   },
  { id:4,  name:'Crook',      xp:7000,     chess:'knight' },
  { id:5,  name:'Thug',       xp:15000,    chess:'knight' },
  { id:6,  name:'Gangster',   xp:30000,    chess:'knight' },
  { id:7,  name:'Enforcer',   xp:60000,    chess:'rook'   },
  { id:8,  name:'Operator',   xp:120000,   chess:'rook'   },
  { id:9,  name:'Hitman',     xp:250000,   chess:'rook'   },
  { id:10, name:'Underboss',  xp:500000,   chess:'bishop' },
  { id:11, name:'Strategist', xp:1000000,  chess:'bishop' },
  { id:12, name:'Boss',       xp:2000000,  chess:'queen'  },                       // defBonus yok
  { id:13, name:'Crew Chief', xp:4000000,  chess:'queen', defBonus:0.10           },
  { id:14, name:'Godfather',  xp:8000000,  chess:'king',  defBonus:0.20, noCop:true },
];
```

### Rank İlerleme Gereksinimleri (RANK_EXTRA)
```javascript
const RANK_EXTRA = {
  '1→2':  { suc:9 },
  '2→3':  { suc:18, araba:5 },
  '3→4':  { suc:27, araba:9 },
  '4→5':  { insidejob:1, mermi:450 },
  '5→6':  { insidejob:3, mermi:900,   kill:2  },
  '6→7':  { insidejob:5, mermi:4500,  kill:5  },
  '7→8':  { felony:1,    mermi:9000,  kill:7  },
  '8→9':  { felony:3,    mermi:22500, kill:10 },
  '9→10': { felony:5,    mermi:45000, kill:11 },
  '10→11':{ aile:true,   mermi:90000, kill:12 },
  '11→12':{ mermi:180000, kill:13 },
  '12→13':{ mermi:450000, kill:15 },
  '13→14':{ don:true, mermi:900000, kill:20 },
};
// "mermi" = lifetime toplam edinilen mermi (harcansa bile düşmez)
```

### XP Tablosu
```javascript
const XP_TABLE = {
  suc:10, armed_robbery:15, bustout:25,
  ticaret_kara:5, ticaret_liman:10, ticaret_airport:20,
  seyahat:3, insidejob:150, felony:1800,
  kill_ayni_rank:1500, kill_ust_rank:1800,
};
```

### Mermi Limiti (Rank Bazlı)
```
R1:1.000 | R2:2.000 | R3:4.000 | R4:8.000 | R5:12.000 | R6:25.000
R7:40.000 | R8:60.000 | R9:90.000 | R10:130.000 | R11:160.000 | R12:200.000
R13:250.000 | R14:300.000
```

---

## SUÇ

### Offender (Normal Suç)
```javascript
// CD: 5dk başarılı / 10dk başarısız
// BAŞARI ORANI: R1-3:%55–62 | R4-6:%65–71 | R7-9:%74–80 | R10-11:%83–85 | R12-14:%87–90
// PARA ÖDÜLÜ: R1-3:$2–$30 | R4-6:$15–$200 | R7-9:$120–$1.500 | R10-11:$700–$1.700 | R12-14:$1.100–$2.500
// Başarısız → Hapis: R1-5:20sn | R6-10:30sn | R11+:45sn
// Item drop (başarılıda): %1→T1/T2 kafa | %0.1→T3/T4 kafa | %0.01→T5 kafa | %1→Kolye/Yüzük/Suit/Yelek
// Sonuç: %80→suç görseli+flavor text | %20→sadece para+XP+KS
```

### Armed Robbery
```javascript
// Rank: 2+ | CD: 5dk başarılı / 10dk başarısız (Offender ile aynı)
// Başarı oranı: OFFENDER_BASARI tablosunu kullanır
// Ödül: $1.500–$5.000 (sabit aralık, rank bağımsız)
// Araç kazanımı: envanterden rastgele T3 araç
// XP: +15
// Başarısız hapis: Offender tablosuyla aynı
```

### Inside Job
```javascript
// Rank: 5+ | CD: 3 saat
// 2 kişi: Lider + Ortak — her ikisi olmadan başlatılamaz
// Para → Lidere | XP+KS → herkese (+150 XP, +0.005 KS)
// Araç: Lider garajından seçer

// BAŞARI ORANI: R5-7:%50–60 | R8-10:%65–75 | R11-14:%80–95
// + Araç tier bonusu: T1:+0% T2:+2% T3:+4% T4:+7% T5:+10%
// Başarısız araç: %50 geri döner / %50 kaybolur

// PARA ÖDÜLÜ: R5-6:$500–$5.000 | R7-9:$3K–$40K | R10-11:$20K–$90K | R12-14:$50K–$200K

// Ekip KS havuzu bonusu:
// 0-1999→min%30 | 2000-3999→min%50 | 4000-5999→min%70
// 6000-7999→min%85 | 8000-9999→%90 | 10000+→tam max

// Başarısız hapis: R5-10:30sn | R11-13:1dk | R14:2dk
// Mermi hasar: ÖLÜM YOK — min 1 HP'ye düşer

// Item Drop (başarılıda):
// %0.1→T5 | %1.0→T4 | %5.0→T3 | %10.0→T2 | %83.9→yok
// Item liderin envanterine düşer
```

### Felony (OC)
```javascript
// Rank: 8+ | CD: 12 saat
// 3-5 kişi: Lider + Şoför + 1-2 Nişancı + Bomba Uzmanı (opsiyonel)
// Para → Lidere | +1800 XP +30 KS → tüm ekibe

const FELONY_ROLLER = {
  lider:        { zorunlu:true,  sayi:1     },
  sofor:        { zorunlu:true,  sayi:1     },
  nisanci:      { zorunlu:true,  sayi:'1-2' },
  bomba_uzmani: { zorunlu:false, sayi:'0-1', bonus:'+%10 para' },
};
// 2. Nişancı varsa: +%5 başarı oranı

// BAŞARI ORANI: R8-10:%50–60 | R11-13:%65–75 | R14:%80
// PARA ÖDÜLÜ: R8-9:$30K–$240K | R10-11:$120K–$600K | R12-14:$330K–$2.1M
// Başarısız hapis: R8:4dk | R9:5dk | R10:6dk | R11:8dk | R12:10dk | R13:15dk | R14:20dk

// Item Drop (başarılıda — Inside Job'ın 2x'i):
// %0.2→T5 | %2.0→T4 | %10.0→T3 | %20.0→T2 | %67.8→yok
// Item rastgele ekip üyesine düşer
```

### KS Sistemi
```javascript
// KS = isabet yüzdesi (cap: 100) | KS 0→%0 isabet | KS 100+→%100
// Isabetsiz mermiler SIFIR hasar verir

const KS_KAYNAKLAR = {
  suc:           0.001,
  armed_robbery: 0.001,
  insidejob:     0.005,   // her başarılı — her iki oyuncuya
  felony:        0.025,
  poligon:       0.0025,  // cooldown 1 saat
  kill_ayni:     0.05,
  kill_ust:      0.15,
  // + Silah / Kolye / Yüzük ekipman bonusu
};
```

---

## SAVAŞ

### Saldırı Akışı
```javascript
// 1. Dedektif tut → 30dk arama (bildirim GİTMEZ)
// 2. Hedef bulundu → Push + email → [ÖLDÜR] butonu
// 3. Mermi sayısı gir → [SALDIR]
// 4. Kontrol: aynı şehirde mi + sığınakta değil mi?
//    Evet → saldırı gerçekleşir | Hayır → iptal, dedektif ücreti yanmış
// 5. Atılan mermi × KS > Toplam savunma → ÖLÜM

// Rank kuralı: Max 1 üst ranka saldırabilirsin, alt sınır yok
// Seyahatteyse → saldırı iptal | Sığınaktaysa → BULUNAMAZ

const DEDEKTIF_MALIYET = {
  1:1000, 2:1000, 3:4000, 4:4000, 5:9000, 6:16000, 7:25000,
  8:36000, 9:49000, 10:64000, 11:64000, 12:81000, 13:81000, 14:100000,
};
```

### Savunma Formülü
```javascript
const savunmaHesapla = (player) => {
  const base = player.bgDefToplam + player.yelekDef + player.suitDef;
  const bonus = player.villaPct
              + player.evlilikPct
              + (player.rank >= 14 ? 0.20 : player.rank >= 13 ? 0.10 : 0);
  return base * (1 + bonus);
};

// Item max değerleri (10 upgrade sonrası):
// BG:    T1:2000  T2:5000  T3:12000  T4:30000  T5:50000
// Yelek: T1:1000  T2:3000  T3:8000   T4:18000  T5:30000
// Suit:  T1:300   T2:1500  T3:4000   T4:9000   T5:15000
// Max (T5×5BG + T5Yelek + T5Suit): 295.000
```

### Backfire
```javascript
const BF_AYARLARI = { kapali:0, yarisi:0.5, ayni:1.0, iki_kati:2.0 };
// Oyuncu önceden seçer → saldırı gelince otomatik devreye girer
// Geri dönen mermilerde HEDEFİN KS'i uygulanır
```

### Şahitlik (Witness)
```javascript
// Başarılı öldürmede: o an online olan rastgele 1 oyuncuya (katil/kurban/aynı aile hariç)
// in-game email + Witness Report item gönderilir
// Witness Report: ITEMS → DOCUMENTS sekmesi | sadece Auction'da satılabilir
// Online kimse yoksa → kaybolur

const FAILED_ATTACK_MSG = { gonderen:'SYSTEM', konu:'ATTACK ALERT',
  icerik:'[SALDIRAN_ADI] attempted to kill you.' };
// Sığınak/seyahatteyse saldırı iptal → mesaj GİTMEZ
```

### Ölüm & Legacy
```javascript
// ÖLÜNCE:
// Cep parası          → öldürene
// Banka %50           → Vasiyet önceliğine göre
// Arabalar            → Vasiyet önceliğine göre
// Uçak/Gemi/Item/BG   → YOK
// Binalar/Casino      → SAHİPSİZ (aynı fiyatla tekrar satışa)

// VASİYET ÖNCELİK SIRASI:
// 1. LEGACY   — Rank10+ veya VIP4 ile ölündüyse → yeni hesaba (1 kez)
// 2. EVLİLİK  — Eşe
// 3. MANUEL   — Manuel seçilen kişiye
// 4. BURN     — Yok olur

// LEGACY avantajları:
// CD -%50 | Başlangıç rank: R5-7→R2 | R8-10→R3 | R11-12→R4 | R13-14→R5
// 2 hafta 2x XP + ölümsüzlük | VIP + aile ilişkisi korunur
// 48 saatte seçilmezse Legacy hakkı kaybolur

// Rank 10+ ölümü → Ticker altın manşet:
// "[PlayerA] — Rank X — has fallen. Killed by [PlayerB] in [Şehir]."
```

### Hapishane & Bustout
```javascript
// 3 çıkış: A) Kefalet öde  B) Break Out (max 3 hak)  C) Bust Out (başkası kurtarır)

const BREAKOUT_BASARI = {
  1:.20,2:.25,3:.30,4:.35,5:.40,6:.45,7:.50,8:.55,
  9:.60,10:.65,11:.70,12:.75,13:.80,14:.85,
};
// Başarısızda eklenen süre (1./2./3. deneme):
// R1-5: 20/40/60sn | R6-10: 30/60/90sn | R11+: 45/90/135sn
// 3 hak bitti → Break Out butonu kaybolur

// Bust Out: başarısız → kurtarıcı da hapse düşer
// Beceri: %20 ile başlar, her 5 başarılı → +%1 (tavan %90)
// Sıralama: En uzun kalan üstte | Aile üyeleri rengiyle highlight
```

### Sığınak (Safe House)
```javascript
// Saldırıya uğranamaz, dedektifle bulunamaz
// Sadece gazete okunabilir
// TopBar + TopNav + BottomBar GİZLENİR
const SIGINAK_MALIYET = 100000; // $100.000/saat — tüm ranklar SABİT
// Para bitince otomatik çıkılır
```

### Hitlist
```javascript
// Koyma: Hedef profilinde | Süre: 48 saat | Otomatik iptal
// Ödül dağılımı: %80 öldürene | %10 aile kasasına | %10 burn
// Aile savaşında: karşı üyeleri ÜCRETSİZ koyabilirsin
```

### Yeni Oyuncu Koruma
```javascript
// Kayıtta otomatik → 5 gün
// Birine saldırırsa ANINDA kalkar
// 24s kala: "PROTECTION EXPIRES IN 24 HOURS."
// Bitince: "YOUR PROTECTION HAS EXPIRED."
```

---

## ITEM & BODYGUARD

```javascript
// Dayanıklılık YOK | NPC satış: alış × 0.50 | T5 altın parlama animasyonu

const ITEM_ROLLER = {
  celik_yelek: 'defence',
  suit:        'defence + slot',
  canta:       'slot',
  silah:       'KS artış %',  // başarı oranına ETKİSİ YOK — sadece KS
  kolye:       'KS artış %',
  yuzuk:       'KS artış %',
};

const ITEM_RANK_MIN = {
  silah:       { t1:1, t2:3, t3:6, t4:9,  t5:12 },
  kolye:       { t1:1, t2:3, t3:6, t4:9,  t5:12 },
  yuzuk:       { t1:2, t2:4, t3:7, t4:10, t5:13 },
  canta:       { t1:2, t2:4, t3:7, t4:10, t5:13 },
  suit:        { t1:3, t2:5, t3:8, t4:11, t5:14 },
  celik_yelek: { t1:3, t2:5, t3:8, t4:11, t5:14 },
};

// Silah KS artışı (mevcut KS'i % artırır — puan değil):
// T1:%1.0–%3.0 | T2:%3.2–%5.0 | T3:%5.2–%7.0 | T4:%7.2–%10.0 | T5:%10.2–%13.0
// Aynı sistem Kolye ve Yüzük için geçerli
// Suit slot: Suit #1=1slot → #50=50slot | En iyi: Wicks Suit (T5#10 — 50slot, 15.000def)

// BODYGUARD: 5 slot, max 10 upgrade, BG kafası gerekir
// Satılamaz: Upgrade BG + BG kafası | BG ölünce tümü ölür
```

---

## VIP & MONETİZASYON

```javascript
const VIP = {
  1: { fiyat:4.99,  avantajlar:['Günlük giriş x2','Suç CD -%25','Hapis CD -%25','Özel VIP chat rengi','Günde 3 ücretsiz skip'] },
  2: { fiyat:9.99,  avantajlar:['...VIP1 dahil','Market komisyonu -%50','Dedektif ücreti -%20'] },
  3: { fiyat:19.99, avantajlar:['...VIP2 dahil','Auto Port (Gemi+Kaptan+VIP3)','Altın VIP rozeti'] },
  4: { fiyat:29.99, avantajlar:['...VIP3 dahil','Auto Airport (Uçak+Pilot+VIP4)'] },
};
// Auto Konteyner VIP gerektirmez — Conductor ($1M) yeterli
// Ücretsiz VIP: görev zinciri (1/3/7 gün) | günlük VIP kutusu (şans bazlı)

// PARA PAKETLERİ:
// $0.99→$500K | $4.99→$3M(+%20) | $9.99→$7M(+%40)
// $19.99→$16M(+%60) | $49.99→$50M(+%100) | $99.99→$120M(+%200)

// REKLAM (AdMob): başlangıçta KAPALI — ~1.000 oyuncuda açılır
// Günlük max: 10 | Gönüllü (zorla gösterim YOK)
// Skip aksiyonları: suc_CD / hapis_CD / kacakcilik_bekle
```

---

## SOSYAL & DİĞER

### Villa & Evlilik Savunma Bonusları
```javascript
const villaBonus = (player) => {
  const sahiplik  = player.villaCount * 0.003; // max 40 villa → +%12
  const aktif     = player.aktifVilla   ? 0.03 : 0;
  const hq        = player.aileHQVilla  ? 0.03 : 0;
  const tamamlama = player.villaCount >= 40 ? 0.05 : 0; // 40 villa tamamlama bonusu
  return sahiplik + aktif + hq + tamamlama; // MAX: +%23
};
// Rank 13 (Crew Chief) ile alınır | Villada ticaret/suç YAPILAMAZ

const evlilikBonus = (player) => {
  if (!player.evli) return 0;
  return player.esVillasiVar ? 0.05 : 0.02;
};
// Evliyken ölünce: banka %50 + arabalar → Vasiyet #2 (eşe)

// TAM SAVUNMA MAX BONUS: +%23(villa) + +%5(evlilik) + +%20(Godfather) = +%48
```

### Günlük Giriş & Haftalık Ödüller
```javascript
const GUNLUK_ODULLER = {
  1:10000, 2:25000, 3:50000, 4:75000, 5:100000, 6:150000,
  7:'$250.000 + özel item',  // 8-14: artan miktarlar
  15:'$1.000.000 + nadir BG kafası',
};
// Gün atlanırsa sıfırlanır

const HAFTALIK_ESIK = { 3:50000, 5:150000, 7:'$500.000 + T2 BG kafası' };
// Her Pazartesi sıfırlanır
```

### Sosyal Ödüller
```javascript
const SOSYAL_ODULLER = [
  { platform:'facebook',  aksiyon:'share',  odul:100000 },
  { platform:'instagram', aksiyon:'share',  odul:100000 },
  { platform:'facebook',  aksiyon:'like',   odul:50000  },
  { platform:'instagram', aksiyon:'follow', odul:50000  },
];
// Her aksiyon yalnızca 1 kez | Tamamlananlar: gri + onay ikonu
```

### Profil Kartı Paylaşımı
```javascript
// expo-view-shot + react-native-share + expo-sharing
// Boyut: 1080×1920 (9:16) | Arka plan: #0f1520 → #080c10
// Watermark: "HUSTLER — LaFamilia" + hashtag (zorunlu)
// İçerik: oyuncu adı, rank, KS, para, kill, insidejob, aile, XP bar
// Instagram yoksa: genel kaydet/paylaş fallback
```

### Ses & Haptic
```javascript
// ─── MÜZİK ASSET'LERİ ───
// Repo: https://github.com/mericaltinors1983-max/underground
// Base URL: https://mericaltinors1983-max.github.io/underground/

const MUSIC_ASSETS = {
  ana_tema:       'Till Paradiso - Be Part of My Universe (TP 024).mp3', // ✅ yüklendi
  music_casino:   'music_casino.mp3',   // ⏳ yüklenecek
  music_buildings:'music_buildings.mp3', // ⏳ yüklenecek
};

// ─── EKRİN → MÜZİK EŞLEŞTİRMESİ ───
const MUSIC_SCREENS = {
  default:    'ana_tema',      // harita, karakter, market, banka vb.
  casino:     'music_casino',  // casino ekranı
  bina_open:  'music_buildings', // şehir haritası / bina popup'ları
  poligon:    'ana_tema',      // poligon (gerilimli — ileriki sürümde ayrı)
  savas:      'ana_tema',      // saldırı ekranı (dramatik — ileriki sürümde ayrı)
  olum:       'ana_tema',      // ölüm ekranı (karanlık — ileriki sürümde ayrı)
  seyahat:    'ana_tema',      // seyahat (hafif — ileriki sürümde ayrı)
};

// ─── SFX TANIMI ───
const SFX = {
  btn_click:    'kisa click',       // her buton tıklaması
  screen_switch:'hafif whoosh',     // ekran geçişi
  success:      'kisa chime',       // başarılı işlem
  error:        'kisa buzz',        // hata
  money_earn:   'coin ses',         // para kazanma
  notification: 'kisa ping',       // bildirim
  modal_open:   'slide-in',        // popup açılışı
  modal_close:  'slide-out',       // popup kapanışı
  map_zoom:     'hafif whoosh',    // harita zoom
  bina_open:    'kapi gicirtisi',  // bina tıklaması
};

// ─── SOUNDMANAGER ─── (Web Audio API prosedüral fallback dahil)
// Kullanım: SoundManager.play('btn_click') | SoundManager.music('casino')
// Ayarlardan müzik ve SFX ayrı ayrı kapatılabilir
// MP3 asset yüklenemezse Web Audio API ile sentetik ses üretilir
// Desteklenmeyen cihazda sessizce geçer

const SoundManager = {
  BASE_URL: 'https://mericaltinors1983-max.github.io/underground/',
  musicEnabled: true,
  sfxEnabled:   true,
  currentMusic: null,
  audioCtx:     null,

  init() { /* AudioContext lazy init */ },

  play(sfxId) {
    if (!this.sfxEnabled) return;
    // Asset varsa çal, yoksa Web Audio prosedüral fallback
    this._playSFX(sfxId);
  },

  music(screenId) {
    if (!this.musicEnabled) return;
    const track = MUSIC_SCREENS[screenId] || MUSIC_SCREENS.default;
    if (this.currentMusic === track) return;
    this._playMusic(track);
  },

  stop() { /* müziği durdur */ },
  _playSFX(id) { /* MP3 → fallback Web Audio */ },
  _playMusic(track) { /* loop, crossfade */ },
};

// ─── HAPTİK ───
export const haptic = {
  attack:'Medium', hit:'Error', death:'Error', rankUp:'Success',
  tier5Equip:'Heavy', bigWin:'Success', crimeSuccess:'Light', insidejobDone:'Success',
};
// Ayarlardan kapatılabilir | Desteklenmeyen cihazda sessizce geçer
```

### Bildirim Defaults
```javascript
const BILDIRIM_DEFAULTS = {
  // Varsayılan AÇIK:
  saldiriya_ugradim:true, hapsedildim:true, hitliste_konuldum:true,
  kacakcilik_tamamlandi:true, bg_ticaretten_dondu:true,
  teklifim_gesildi:true, seyahat_tamamlandi:true,
  aile_savasi_basladi:true, mesaj_aldim:true,
  // Varsayılan KAPALI:
  dukkan_geliri_hazir:false, aile_daveti:false,
};
```

### Dil & Server
```
9 dil: İngilizce(ana) · Türkçe · Almanca · İspanyolca · Portekizce-BR · Rusça · Japonca · Çince · Fransızca
→ Telefon dili otomatik algılanır, restart gerekmez

Paralel server modeli — her server bağımsız dünya
Server dolunca yeni açılır, otomatik atanır | "Server seç" ekranı yok | Sıfırlama yok — kalıcı
```

### Kurulum Gereksinimleri
```bash
npx expo install expo-haptics expo-view-shot react-native-share expo-sharing expo-screen-orientation
# Sonraki aşama:
# @react-native-google-mobile-ads/google-mobile-ads
# react-native-purchases  (RevenueCat — abonelik)
```

---

## PROTOTYPE DURUMU

| Component | Durum | Dosya |
|---|---|---|
| AppShell (TopBar/Nav/BottomBar) | ✅ | base_prototype_v3-15-62-3-4-7-6.html |
| Dünya + Ülke + Şehir Haritası | ✅ | base_prototype |
| BuildingPopup (Fabrika/Mağaza) | ✅ | fabrikalar_popup_v1-2-12 / magazalar_popup |
| OffenderScreen | ✅ | offender_popup_fixed-7.html |
| ArmedRobberyScreen | ✅ | armed_robbery_popup_v1-1-1.html |
| InsideJobScreen | ✅ | inside_job_popup_v1-1-1.html |
| FelonyScreen | ✅ | felony_popup_v1-1.html |
| BustoutScreen | ✅ | bustout_popup_fixed.html |
| TradeScreen (Kaçakçılık) | ✅ | kacak_popup |
| MarketScreen | ✅ | market_v2.html |
| PersonalsScreen | ✅ | personals.html |
| ItemScreen | ✅ | item_popup_fixed.html |
| VillaScreen | ✅ | villa_popup_v1-6-2.html |
| MarriageScreen | ✅ | marriage_popup_v1-1.html |
| CasinoScreen | ✅ | casino_popup_v2-22-2.html |
| BankScreen | ✅ | banka_popup_v1-6-1.html |
| VIPScreen | ✅ | vip_popup_v1-3.html |
| SettingsScreen | ✅ | settings_popup_v1-4-4.html |
| NotificationPanel | ✅ | notification_panel_v1-2.html |
| StoreScreen | ✅ | store_popup_v1-3.html |
| EventScreen | ✅ | event_popup_v1-6.html |
| TopSpenderScreen | ✅ | toplespender_popup_v1-3.html |
| KamuBinalarScreen | ✅ | kamu_binalar_v2-7-1.html |
| SafeHouseScreen | ✅ | safehouse_popup_v1-0-0.html |
| TravelMiniBanner | ✅ | travel_banner_v1-0-0.html |
| AttackScreen | ✅ | attack_popup_v1-0-0.html |
| DeathScreen | ✅ | death_screen_v1-0-0.html |
| HitlistScreen | ✅ | hitlist_popup_v1-0-0.html |
| ProfileCardShare | ✅ | profile_share_popup_v1-0-0.html |
| HospitalScreen | ✅ | fabrikalar_popup içinde (tip:'fabrika') |
| PrisonScreen | ✅ | bustout'a yönleniyor (kamu bina) |
| HapticFeedback | ✅ | Kod hazır |
| SoundManager | ⏳ | 2 MP3 bekleniyor (music_casino + music_buildings) |
| PoligonScreen | ⏳ | KS geliştirme — Yakında |
| FamilyWarSystem | ⏳ | |

### Bilinen Prototype Bugları (base_prototype)
```
TÜM BUGLAR DÜZELTİLDİ — base_prototype_v3-15-62-3-4-7-6:
1. ✅ Russia flag: src="arussia.png" → "country_russia.png"
2. ✅ BottomBar: switchScreen('seyhat') → 'seyahat' (4 yerde)
3. ✅ updateRankAnimal() onerror crash → wrapper div + innerHTML fix
4. ✅ goSc() — kaçakçılık iç navigasyon için korundu, açıklama eklendi
5. ✅ getTop3Cities() → kanal parametresi eklendi, port → sadece liman şehirleri filtresi
```
