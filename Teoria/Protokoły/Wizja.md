# Omówienie
### Analog
Analogowy system FPV to klasyczne rozwiązanie stosowane w modelarstwie od ponad dekady. Wykorzystuje transmisję obrazu w standardzie **PAL/NTSC** przez pasmo **5.8 GHz**. Popularność zawdzięcza prostocie, niskim kosztom i minimalnemu opóźnieniu. Nadal jest powszechnie używany w wyścigach FPV i projektach DIY.

**Cechy:**
- Bardzo małe opóźnienia (ok. 10–20 ms)
- Niska złożoność sprzętowa – proste VTX, VRX i kamera
- Niska cena i szeroka kompatybilność (40CH, różne marki)
- Obraz SD (576i / 480p) o ograniczonej jakości
- Brak cyfrowej transmisji danych (np. OSD w obrazie analogowym)

|           _**Band**_           | **CH1** | **CH2** | **CH3** | **CH4** | **CH5** | **CH6** | **CH7** | **CH8** |
| :----------------------------: | :-----: | :-----: | :-----: | :-----: | :-----: | :-----: | :-----: | :-----: |
|        **A (BOSCAM A)**        |  5865   |  5845   |  5825   |  5805   |  5785   |  5765   |  5745   |  5725   |
|        **B (BOSCAM B)**        |  5733   |  5752   |  5771   |  5790   |  5809   |  5828   |  5847   |  5866   |
|        **E (BOSCAM E)**        |  5705   |  5685   |  5665   |  5645   |  5885   |  5905   |  5925   |  5945   |
| **F (FatShark / ImmersionRC)** |  5740   |  5760   |  5780   |  5800   |  5820   |  5840   |  5860   |  5880   |
|        **R (RaceBand)**        |  5658   |  5695   |  5732   |  5769   |  5806   |  5843   |  5880   |  5917   |

### HDZero
System **HDZero** (wcześniej Shark Byte) został opracowany przez firmę **Divimath** i rozwijany wraz z **FatShark**. Wprowadził **cyfrowy obraz HD (720p)** z bardzo niskim opóźnieniem, zachowując zalety analoga. Jest jednym z niewielu **otwartych systemów cyfrowych** FPV.

**Cechy:**
- Rozdzielczość do **1280×720 @ 60 FPS**
- Opóźnienie porównywalne z analogiem (~20–25 ms)
- Przesył obrazu bez kompresji stratnej (OFDM)
- Kompatybilność z różnymi goglami FPV
- System **modułowy i otwarty** (możliwość integracji z własnymi kontrolerami lotu)
- Nieco mniejszy zasięg niż DJI, ale stabilniejszy obraz w wyścigach
### WalkSnail Avatar
**Opis / historia:**  
WalkSnail Avatar to cyfrowy system FPV od **Caddx** (we współpracy z WalkSnail). Oparty na **kodeku H.265**, oferuje obraz **1080p** z bardzo dobrą kompresją i niskim opóźnieniem. Został zaprojektowany jako alternatywa dla DJI, kompatybilny z goglami **FatShark Dominator HD**.

**Cechy:**
- Obraz **1080p @ 60 FPS**, transmisja H.265
- Opóźnienie około **22 ms**
- Dobra jakość obrazu i odwzorowanie kolorów
- Integracja z OSD Betaflight
- Aktualizacje OTA i możliwość nagrywania HD w kamerze
- Ekosystem półzamknięty (ograniczona kompatybilność z innymi urządzeniami)

### DJI FPV / O3 Air Unit
**DJI** zrewolucjonizowało FPV, wprowadzając w 2019 r. cyfrowy system FPV HD z niskim opóźnieniem i wysoką jakością. Obecna generacja (**O3 Air Unit**) umożliwia nagrywanie w **4K/60kl**, jednocześnie transmitując obraz HD do gogli w czasie rzeczywistym.

**Cechy:**
- Transmisja **H.265** w pasmach **2.4 GHz / 5.8 GHz**
- Obraz **1080p @ 120 FPS**
- Zasięg do **10 km (FCC)**
- Opóźnienie ~30 ms
- Wbudowane nagrywanie (DVR 4K)
- Bardzo stabilne połączenie i zarządzanie kanałami
- Wadą jest **zamknięty ekosystem** i wysoka cena




# Ważne informacje
|System|Typ transmisji|Charakterystyka|Zalety|Wady|
|:--|:--|:--|:--|:--|
|**Analog (5.8 GHz)**|Analogowa|Klasyczny system FPV wykorzystujący sygnał wideo w paśmie 5.8 GHz (PAL/NTSC).|Bardzo małe opóźnienia (~10–20 ms), niska cena, szeroka kompatybilność, lekka elektronika.|Niska rozdzielczość obrazu (SD), podatność na zakłócenia, brak telemetrii cyfrowej.|
|**HDZero (formerly Shark Byte)**|Cyfrowa (5.8 GHz, OFDM)|Otwarty system cyfrowy rozwijany przez Divimath i FatShark. Wideo HD 720p przy bardzo małym opóźnieniu.|Niskie opóźnienie (~17-20 ms), obraz HD, mniejsze zakłócenia niż analog, współpraca z różnymi goglami.|Droższy niż analog, mniejszy zasięg niż DJI, ograniczona kompresja obrazu.|
|**WalkSnail Avatar**|Cyfrowa (5.8 GHz, H.265)|System od Caddx (we współpracy z WalkSnail). Wysoka jakość obrazu i integracja z goglami FatShark Dominator HD.|Obraz 1080p, dobra kompresja, niskie opóźnienia (~22 ms), integracja z OSD.|Wysoka cena, ekosystem zamknięty, mniejsza dostępność niż DJI.|
|**DJI FPV / O3 / Air Unit**|Cyfrowa (2.4 GHz / 5.8 GHz, H.265)|Najbardziej zaawansowany i stabilny system wideo FPV. Używa transmisji cyfrowej o wysokiej przepływności.|Bardzo wysoka jakość obrazu (1080p/120fps), duży zasięg, małe opóźnienie (~30 ms), stabilna łączność.|System zamknięty, wysoka cena, ograniczona kompatybilność, brak pełnej integracji z niestandardowymi kontrolerami.|
|**OpenIPC** _(ciekawostka)_|Cyfrowa, otwarta (Ethernet / Wi-Fi)|Projekt open-source zamieniający kamery IP z SoC Hisilicon / Ingenic w nadajniki wideo. Możliwy rozwój w kierunku FPV IP (Wi-Fi 5/6).|Otwarty kod, duża konfigurowalność, potencjał dla tanich rozwiązań HD.|Wysokie opóźnienia, wymaga mocnego SoC i sieci, nieprzystosowany do real-time FPV.|

# Zadania
1. Wylicz, które pasmo analogowe jest najbardziej optymalne do lotów w wiele osób na raz (Największy i równy odstęp częstotliwości)
# Powiązane tematy