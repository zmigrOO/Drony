# Omówienie
### Silniki bezszczotkowe - brushless
Silniki bezszczotkowe (ang. _Brushless DC Motor_, w skrócie **BLDC**) to najczęściej stosowany typ napędu w nowoczesnych dronach, w tym w systemach FPV (First Person View). Ich konstrukcja pozbawiona szczotek eliminuje tarcie mechaniczne pomiędzy komutatorem a uzwojeniami, co znacząco zwiększa żywotność i niezawodność napędu. Dodatkową zaletą jest wysoka sprawność energetyczna oraz lepsza kontrola momentu obrotowego i prędkości obrotowej w szerokim zakresie napięć.

W zastosowaniach FPV silniki bezszczotkowe sterowane są przez dedykowane regulatory [ESC](ESC) (ang. _Electronic Speed Controller_), które odpowiadają za generowanie odpowiednich sekwencji sygnałów trójfazowych w celu obracania wirnika. ESC interpretuje sygnały sterujące (zazwyczaj w postaci sygnału PWM lub protokołów cyfrowych, takich jak DShot czy OneShot) pochodzące z kontrolera lotu i na ich podstawie reguluje prędkość każdego z silników z dużą precyzją.

Każdy silnik BLDC charakteryzuje się parametrem **KV** (ang. _RPM per Volt_), który określa liczbę obrotów na minutę generowaną przez silnik na każdy wolt zasilania, przy braku obciążenia. Przykładowo, silnik o wartości 2300 KV przy zasilaniu 12 V może osiągnąć prędkość około 27 600 obr./min. W praktyce rzeczywista prędkość zależy od obciążenia, zastosowanych śmigieł oraz sprawności całego układu napędowego. W dronach FPV dobór odpowiedniego silnika (oraz ESC) uzależniony jest od masy konstrukcji, pojemności akumulatora i docelowej charakterystyki lotu (np. stabilność vs. zwrotność).

Silniki bezszczotkowe w konfiguracji FPV wymagają również odpowiedniego chłodzenia, ponieważ przy dużych prądach (rzędu kilkudziesięciu amperów) mogą się nagrzewać, co prowadzi do spadku efektywności. Ze względu na ich wysoką dynamikę i stosunkowo niską masę własną, stanowią one obecnie standard w większości platform FPV oraz w dronach wyścigowych.

| Zdjęcie                                            | Nazwa          | Cechy                        |
| -------------------------------------------------- | -------------- | ---------------------------- |
| <img src="Img/motor_Page 1_motor.png" width=300px> | Motor (Silnik) | Silnik                       |
| <img src="Img/motor_Page 2_motor.png" width=300px> | Stator         | Część statyczna silnika      |
| <img src="Img/motor_Page 3_motor.png" width=300px> | Rotor (Wirnik) | Część silnika obracająca się |
### Silniki szczotkowe - brushed
Silniki szczotkowe (ang. _Brushed DC Motor_) to starszy typ silników prądu stałego, w których komutacja prądów w uzwojeniach realizowana jest mechanicznie za pomocą szczotek i komutatora. Choć konstrukcja tego typu napędów jest prostsza i tańsza w produkcji, ich wadą jest zwiększone zużycie elementów mechanicznych, niższa sprawność oraz ograniczona żywotność wynikająca z tarcia szczotek.

W zastosowaniach FPV silniki szczotkowe spotykane są głównie w mikrodronach (tzw. _Tiny Whoop_), w których niska masa i prostota układu sterowania są istotniejsze niż maksymalna wydajność. W takich konstrukcjach sterowanie odbywa się za pomocą prostych regulatorów prędkości, często zintegrowanych z kontrolerem lotu. Silniki szczotkowe zasilane są bezpośrednio napięciem z akumulatora, a zmiana prędkości realizowana jest przez modulację szerokości impulsu (PWM).

Silniki tego typu nie posiadają parametru KV w klasycznym znaczeniu, ponieważ ich prędkość zależy liniowo od napięcia zasilania oraz obciążenia. W porównaniu do silników bezszczotkowych generują one mniejszy moment obrotowy i są mniej wydajne, jednak ich prostota sprawia, że nadal znajdują zastosowanie w tanich konstrukcjach edukacyjnych i rekreacyjnych.

Podsumowując, silniki szczotkowe stanowią rozwiązanie ekonomiczne i proste w implementacji, natomiast silniki bezszczotkowe dominują w bardziej zaawansowanych konstrukcjach FPV ze względu na lepsze parametry pracy, większą precyzję sterowania i wyższą efektywność energetyczną.

> [!INFO] Ważne pojęcia
> **KV** - Parametr określający ilość obrotów przy napięciu 1V

# Ważne informacje
### Porównanie

| Cecha / parametr                | Silnik bezszczotkowy (BLDC)                   | Silnik szczotkowy (Brushed)                           |
| ------------------------------- | --------------------------------------------- | ----------------------------------------------------- |
| **Budowa**                      | Brak szczotek, elektroniczna komutacja faz    | Komutacja mechaniczna za pomocą szczotek i komutatora |
| **Sterowanie**                  | Wymaga zewnętrznego regulatora ESC            | Sterowanie bezpośrednie (PWM lub prosty regulator)    |
| **Sprawność energetyczna**      | Wysoka (80–90%)                               | Niższa (60–75%)                                       |
| **Trwałość i niezawodność**     | Bardzo wysoka, brak zużycia szczotek          | Ograniczona przez zużycie szczotek                    |
| **Moment obrotowy**             | Wysoki, stabilny w szerokim zakresie obrotów  | Niższy, spada wraz ze wzrostem prędkości              |
| **Zakres prędkości obrotowych** | Bardzo szeroki, nawet powyżej 30 000 obr./min | Ograniczony, typowo do kilku tysięcy obr./min         |
| **Charakterystyka KV (RPM/V)**  | Określa prędkość przy danym napięciu          | Nie definiowana, zależna od napięcia i obciążenia     |
| **Sterowanie w FPV**            | Za pomocą ESC i sygnałów PWM/DShot            | Prosty układ PWM, często zintegrowany z kontrolerem   |
| **Koszt i złożoność układu**    | Wyższy koszt, bardziej złożony                | Niższy koszt, prostszy układ                          |
| **Zastosowanie w dronach FPV**  | Drony wyścigowe, freestyle, profesjonalne     | Mikrodrony (Tiny Whoop), konstrukcje edukacyjne       |

### Współczynnik KV silnika bezszczotkowego

Wartość **KV (ang. _RPM per Volt_)** określa, ile obrotów na minutę (_RPM_) wykonuje silnik przy zasilaniu napięciem **1 V**, bez obciążenia (czyli bez śmigła).  
Parametr ten jest jednym z kluczowych elementów doboru silnika w systemach FPV, ponieważ wpływa na moment obrotowy, prędkość oraz efektywność energetyczną napędu.

Im **większa wartość KV**, tym **wyższa prędkość obrotowa**, ale **mniejszy moment obrotowy**.  
Z kolei silniki o **niższym KV** generują **większy moment**, lecz obracają się wolniej.

---

#### Podstawowy wzór

$$
n = KV \times U
$$

gdzie:  
- \( n \) – prędkość obrotowa [obr./min],  
- \( KV \) – współczynnik prędkości silnika [obr./min/V],  
- \( U \) – napięcie zasilania [V].

---

#### Zależność między KV a momentem obrotowym

Dla silników bezszczotkowych zachodzi odwrotna zależność między stałą KV a momentem obrotowym \( K_t \):

$$
K_t = \frac{60}{2\pi \times KV}
$$

gdzie:  
- \( K_t \) – stała momentu silnika [N·m/A],  
- \( KV \) – współczynnik prędkości [obr./min/V].

Z równania wynika, że **im wyższe KV**, tym **mniejszy moment obrotowy** przypadający na 1 A prądu.

---

### Dobór współczynnika KV w dronach FPV

Dobór odpowiedniego współczynnika KV zależy od charakterystyki lotu i napięcia zasilania. W dronach FPV dąży się do kompromisu pomiędzy momentem obrotowym, prędkością i efektywnością energetyczną:

- **Drony wyścigowe (racing FPV)** – wysokie KV (2300–2800 KV, pakiet 4S); duża prędkość, wysoki pobór prądu.  
- **Drony freestyle / akrobatyczne** – średnie KV (1800–2300 KV); balans między mocą a płynnością.  
- **Drony typu cinewhoop / long range** – niskie KV (1200–1700 KV, pakiety 6S–7S); płynny, stabilny lot i dłuższy czas pracy.

Dobór silnika o odpowiednim KV musi uwzględniać masę drona, średnicę i skok śmigieł oraz napięcie akumulatora.  
Nieprawidłowe zestawienie (np. zbyt wysokie KV przy dużych śmigłach i wysokim napięciu) może prowadzić do przeciążenia silników i regulatorów ESC.

# Zadania

# Powiązane tematy