# CMD-Command-Prompt
Basic commands in CMD in windows

CMD-Command Prompt 

Partycjonowanie – DISKPART 

list disk - Wyświetla listę dysków. 

select disk 0 – Wybiera dysk z numeren 0. 

detail disk - Wyświetla informacje o dysku. 

list partition - Wyświetla listę partycji. 

select partition 2 – Wybiera partycję z numerem 2. 

shrink querymax – Oblicza o ile można zmniejszyć partycję. 

shrink desired=20000 – Zmniejsza partycję o 20000 megabajtów. 

create partition primary size=20000 – Tworzy partycję podstawową o rozmiarze 20000 MB. 

Partycjonowanie – DISKPART (2) 

format fs=ntfs quick – Formatuje partycje do systemu plików ntfs. 

assign letter j – Przypisuje literę J do partycji. 

clean - Czyści wcześniejszy styl partycji. 

convert gpt – Tworzy styl GPT dla partycji. 

convert mbr – Tworzy styl MBR dla partycji. 

Pliki i katalogi 

md (lub mkdir) nazwa_katalogu – Tworzy katalog o podanej nazwie. 

rd (lub rmdir) nazwa_katalogu – Usuwa katalog o podanej nazwie (ale tylko pusty). 

rd (lub rmdir) nazwa_katalogu /s /q - Usuwa katalg o podanej nazwie, kiedy nie jest pusty. 

del nazwa_pliku – Usuwa plik o podanej nazwie. 

cd\ (lub /) - Przechodzi do katalogu głównego partycji. 

Pliki i katalogi (2) 

cd .. - Przechodzi jeden katalog wyżej. 

dir - Wyświetla zawartość katalogu. 

rename (lub ren) nazwa_katalogu (lub pliku) - Zmienia nazwę katalogu lub pliku. 

Type nyl>nazwa_pliku – Tworzy pusty plik. 

Echo tekst>nazwa_pliku.txt - Tworzy plik tekstowy z zawartością “tekst”. 

Pliki i katalogi (3) 

move źródło  cel  - Przenosi pliki i katalogi z katalogu żródłowego do docelowego. 

copy źródło  cel  - Kopiuje pliki z katalogu żródłowego do docelowego. 

xcopy źródło  cel  - Kopiuje pliki i katalogi z katalogu żródłowego do docelowego. 

help xcopy - wyświetla pomoc dla polecenia xcopy. 

Użytkownicy i grupy 

netstat (lub netstat –a)  – Pokazuje aktywne połaczenia. 

net user nazwa_usera hasło_usera /add - Dodaje użytkownika. 

net user nazwa_usera /delete - Usuwa użytkownika. 

net user nazwa_usera /active:no - Określa konto uzytkownika jako nieaktywne. 

net user nazwa_usera /time:m-f,8:00--16:00 - Określa dni i godziny logowania. 

Użytkownicy i grupy (2) 

net localgroup nazwa_grupy /add - Dodaje grupę użytkowników. 

net localgroup nazwa_grupy /delete - Usuwa grupę użytkowników. 

net localgroup nazwa_grupy nazwa_usera /add - Dodaje użytkownika do grupy. 

Uprawnienia do plików i folderów 

cacls nazwa_folderu - Wyświetla listę ACL dla folderu. 

cacls nazwa_folderu /t /e /g nazwa_usera:f – Nadaje pełne prawa do folderu dla podanego użytkownika. 

cacls nazwa_folderu /t /e /g nazwa_usera:r – Nadaje prawa odczytu do folderu dla podanego uzytkownika. 

cacls nazwa_folderu /t /e /g nazwa_usera:w – Nadaje prawa zapisu do folderu dla podanego użytkownika. 


Konsola w Sieci 

ipconfig - wyświetla konfiguracje ustawień IP. 

ipconfig /all - Wyświetla pełne informacje o konfiguracji. 

ipconfig /release - Zwalnia zajmowany poprawny adress IP z serverem DHCP. 

ipconfig /renew - Nadaje nowy adress IP z serverem DHCP. 

ipconfig /renew “nazwa_karty_sieciowej” - Nadaje adress IP z serverem DHCP dla konkretnej karty sieciowej. 

Ipconfig /displaydns - Historia połączeń ze stronami www czy innych usług sieciowych która wykorzystuje DNS. (Client butter DNS). 

Ipconfig /flushdns - czyszczy pamięć podręczną (cashe) z historii DNS. 

ping adres_hosta (np.: www.wp.pl) - Ping służy do diagnozowania połączenia z innymi hostami. 

ping adres_hosta -t   - Wysyła cały czas żądania echo, aż ręcznie tego nie przerwamy. Aby przerwać (CTRL+C), lub jeżeli chcemy zobaczyc w trakcie procesu statystyki (CTRL+BREAK). 

tracert adres_hosta -Narzędzie do testowania trasy od maszego komputera do hosta docelowego. 

tracert /? -Lista sposobów użycia. 

pathping adres_hosta -Służy głównie do obliczania start pakietów przez poszczególne routery na trasie od hosta źródłowego do docelowego. (Słuzy do szukania wąskich gardeł w sieci, jaki router generuje najwieksze straty). 

arp -Służy do mapowania adresów IP(logicznych) na fizyczne adresy(MAC). 

arp –a  -Tablica wpisów ARP komputera. 

arp –s  adres_ip adres_mac  -Ręczne dodawanie wpisów do tablicy ARP. 

arp –d  -Usuwa wszystkie wpisy z komputera. 

netstat (lub netstat –a)  – Pokazuje aktywne połaczenia. 

netstat –e  -Wyświetla statystyki wysłanych i odebranych pakietów. 

netstat –s -Wyświetla bardzo szczegółowe statystyki pakietów. 

Netstat –r -Wyświetla tablice routingu naszego komputera. 

Netsh 

netsh –Narzędzie do konfiguracji połączenia sieciowego. (czyli jak dodać adres IP). 

interface show inferface  -Pokazuje listę dostępnych połącznień sieciowych. 

interface set interface name=”nazwa_karty_sieciowej” newname=”nowa_nazwa”  -Pozwala na zmianę nazwy  karty sieciowej. 

interface ip set address name=”nazwa_karty_sieciowej” static  adres_ip   adres_maski   adres_bramy -Przypisanie konkretnej adres IP dla danej karty. 

interface ip set dns name=”nazwa_karty_sieciowej” static  adres_ip   -Przypisanie adresa servera DNS. 

interface ip show config name=”nazwa_karty_sieciowej”  -Pokazuje konfiguracje interfejsu. 

interface ip set address name=”nazwa_karty_sieciowej” dhcp  -Zmiana konfiguracji tak aby komputer otrzymywał adress IP w sposób dynamiczny, czyli dzięki usłudze DHCP.(dotyczy maski i bramy). 

Interface ip set dns name=”nazwa_karty_sieciowej” dhcp  -Zmiana konfiguracji tak aby komputer otrzymywał adress IP w sposób dynamiczny, czyli dzięki usłudze DHCP.(dotyczy adres servera DNS). 
