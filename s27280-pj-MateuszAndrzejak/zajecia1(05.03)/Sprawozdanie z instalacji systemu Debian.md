# Sprawozdanie z instalacji systemu Debian 11 w VMware Workstation 17

## 0. Jakie będzie wykorzystanie?

Maszyna ta jest moim eksperymentem w którym próbuje rozwiązań których nigdy wczesniej próbowałem. Nie przewiduję dla niej instalacji środowiska graficznego, głównie mam zamiar uruchamiać na niej skrypty lub programy w C.

## 1. Konfiguracja maszyny
na wstepnie Workstation pyta się o obraz dysku, pomijam ten krok ponieważ moje srodowisko ma mozliwosc automatycznej instalacji systemu na vm'ce a ja nie chce z tego korzystac i przebrnac przez instalacje wlasnorecznie.

W kolejnym kroku program pyta się jaki OS będzie zainstalowany, z opcji są:

Microsoft Windows z opcjami dla :

    -Windows od 3.1 do 11 (mam tu na mysli te konsumerskie)
    -Windows Server od 2000 do 2022
    -Hyper-V

Linux z opcjami dla:

    -Asianux 3 i 4 oraz 3 Server
    -CentOS od 5(opcja 5 podobno tez wspiera starsze) do 8
    -Debian od 5 do 11 (ten wybieram)
    -Fedora (tu bez wersji)
    -Mandriva
    -Novell Linux 9
    -Oracle Linux od 5 i wczesniejsze do 8
    -RHEL od 2 do 9
    -Red Hat Linux
    -Sun java Desktop system
    -SUSE Linux Enterprice od 7/8/9 do 15
    -SUSE Linux
    -Turbolinux
    -Ubuntu
    -VMware Photon OS
    -Other Linux, tu wybieramy wersje kernela, są od  2.2.x do 5.x

Apple Mac OS X (ta opcja domyslnie niedostepna dla normalnej wersji programu, jednak sa unlockery pozwalajace na "hackintosh" w tym srodowisku)

    -macOS 10 od 10.8 do 10.15
    -macOS od 11 do 15
    -macOS X Server od 10.5 do 10.6

Other

    -MS-DOS
    -eComStation 1 i 2
    -FreeBSD od 10 i wczesniejsze do 12
    -NetWare 5 i 6
    -Other
    -Solaris 8 i 9 (niewspierane)
    -Solaris 10 i 11

Jak napomniałem wczesniej ja zaznaczyłem Debian 11.x 64bit bo taka jest moja instalka systemu

W nastepnym oknie wybieram nazwe maszyny oraz lokalizacje plikow.

W nastepnym kroku mam wybrać pojemność dysku, w moim przypadku zdecydowałem się na 10GB przestrzeni dyskowej.
Program pyta się mnie czy chce plik z dyskiem miec w:

    -jednym pliku
    -w kilku plikach (rozwiazanie to ulatwia migracje maszyny z PC na PC ale przy wiekszym dysku spowolni działanie)

10GB mi nie straszne wiec wybralem rozwiazanie w jednym pliku, a ja nie zamierzam transportować tej maszyny

Nastepnie mam okno podsumowania w ktorym jest:

    -Nazwa
    -Lokalizacja
    -Wersja programu
    -System operacyjny
    -Pojemność dysku

    -Pamieć RAM -  tu vmware ustawil domyslnie 2GB które zmienie na czas instalacj na aż 6GB (bo po coś ostatnio dokładałem tego ramu) aby po instalacji wrócic do domyslnej wartości ale o tym pózniej

    Karty sieciowe z nastepujacymi opcjami:

        Network Connection:

            -Brigded (polaczy bezposrednio z siecia tworzac nowy mac, ip itd..)
            -NAT (czyli bedzie korzystalo z IP hosta) i na tą opcje się zdecyduje
            -Host Only (Prywatna siec dzelona z hostem)
            -Custom (tu mam do wyboru 20 wirtualizowanych kart sieciowych)

    inne urzadzenia:

        -tu do napedu CD/DVD ładuje iso pobrane ze strony debiana
        -moge tez uzyc fizycznego napedu ale go nie posiadam wiec daruje sobie ta opcje
        - W USB controller wybieram :

            -USB compability - USB 2.0 (wszystkie peryferia mam spiete w HUB w tym standardzie)
            -Moge rowniez udostepnic modul BT mojej maszynie ale w skrzynce takowego nie mam wiec to rowniez sobie daruje

    karta dzwiekowa:

        -moge uzyc defualtowego endpointu (to wybieram)
        -przekierować maszyne na konkretne wyjscie(sluchawki, monitory, glosniki, gamepad)

    drukarka:

        Tą opcje mam wylaczona ponieważ nie posiadam takiego sprzetu

    ekran:

        Akceleracja grafiki 3d - wylaczam bo szkoda zasobów, nie bede potrzebował

        Monitory:

            -uzyj ustawien host (zostawiam)
            -ilosc ekranów (u mnie wybieram 1) i ewentualna rozdzielczość

Przebrnałem przez wstepna konfiguracje, pora potwierdzić stan maszyny
Maszyna została utworzona ale na ponownie wchodzę w ustawienia

na czas instalacji chciałbym zwiekszyć ilość rdzeni z 1 na 2 bo chciałbym skrócić czekanie

w opcjach procesora moge rownież zmienić silnik wirtualicaji

    Intel VT-x/EPT and AMD-V/RVI (gdybym chciał odpalać vm w vm ale to za duzo jak dla mnie i moich potrzeb)


## 2.Instalacja systemu

Uruchamiam VM i po odpaleniu klikam klawisz aby zbootować system z iso

maszyna wystartowała z pliku iso a mnie powitało menu instalatora z nastepującymi opcjami:

    Instalacja graficzna

    Instalacja tekstowa

    Opcje zaawansowane:

        -Graficzna instalacja tekstowa
        -Graficzny tryb odzyskania systemu
        -Graficzna instalacja w trybie zautomatyzowanym
        -Ekspercka instalacja
        -Tryb odzyskiwania systemu
        -Zautomatyzowana instalacja
        -Instalacja z możliwoscią czytania opcji przez komputer

    Ciemnokontrastowe menu

    Pomoc

    Instalacja z syntezatorem mowy


Ja postanowiłem wybrać instalacje ekspercka

Po jej odpaleniu zobaczyłem nastepujące opcje:

    Wybierz język

    Dostęp dla osoby ślepej używajacej wyswietlaczy brailla

    Konfiguracja klawiatury

    Wykryj i zamontuj pliki instalacji

    Zapisz logi do debugowania

    Odpal shell

    Anuluj instalacje

Przechodze do menu wybierz język, zaznaczam angielski i przechodze do wyboru mojej lokacji. Wybieram Polske, a jako defaultowe ustawienia klawiatury en_US.UTF-8, następnie wybieram pl_PL.UTF-8

Po skonfigurowaniu klawiatury zamontowałem pliki instalatora i załadowałem je.

Na ekranie wyskoczyła możliwosć wyboru elementow instalatora i wybranie serwera lustrzanego

    Pakiety udeb (Micro Deb) to wersja minimalna przeznaczona dla maszyn z ograniczonymi zasobami

    Crypto-dm-modules - moduł kryptograficzny

    driver-injection-disk-detect - narzędzie do automatycznego wykrywania nowych urządzen i instalacji sterowników

    espeakup-udeb - systemowy syntezator mowy

    event-modules - zestaw modułów do obsługi i wykrywania zdarzeń systemowych

    f2fs-modules - moduły do obsługi pamięci flash

    fdisk-udeb - narzedzie do partycjonowania dysku

    fuse-modules - obsługa Filesystem in Userspace czyli interfejsu do tworzenia i montowania systemów plików.

    load-media - załadowanie komponentów instalatora z iso

    lowmem - tryb pracy kernela minimalizujacy zuzywanie pamieci RAM

    mbr-udeb - program do zarządzania MBR dysku

    multipatch-modules - moduł zawierajacy zestaw łatek dla kernela

    nbd-modules - moduł kernela umożliwiający korzystanie z protokołu NBD czyli udostępnianie bloków dyskowych przez sieć.

    network-console - możliwość podłaczenia się do konsoli Debiana zdalnie

    openssh-client-udeb - obsługa jako klient SSH

    parted-udeb - instalacja narzędzia Parted do zarządzania dyskami

    ppp-modules - moduł kernela z obsługa protokołu Point-to-Point

    ppp-udeb - pakiet instalacyjny zawierajacy program do połaczeń mioedzy dwoma urządzeniami podczas instalacji systemu

    reiserfsprogs-udeb - zarzadzanie systemem plików ReiserFS podczas instalacji

    rescue-mode - tryb odzyskiwania

    sound-modules - obsługa dzwięku

    scsi-nic-modules - Sterowniki dla SCSI

    squashfs-modules - system plików dostepny tylko do odczytu

    udf-modules - moduł do obsługi płyt CD, DVD i blu-ray


W następnym kroku wybiore mój serwer lustrzany i wybiore autokonfiguracje adresów ip.

Nazwe hosta zostawie domyslna jako debian, nazwe domeny zostawię pustą i przejdę do konfiguracji użytkownika

System proponuje wlaczenie Shadow passwords czyli zaszyfrowanych haseł przechowywanych w odizolowanym pliku który mogą odczytać tylko specjalne programy. W tym przypadku niezdecyduję się na tą opcje ponieważ nie mam zamiaru trzymać tam wrażliwych danych a być może w przyszłości wykorzystam tą luke w jakimś skrypcie.

Następnie system pyta o możliwość logowania się jako root, wybieram tą opcje.

Wybieram hasło roota. System pyta się o dodanie nowego użytkownika ponieważ konto root nie jest bezpieczne do używania na codzień.

Zdecydowałem się na dodanie usera o nazwie user.

W następnej kolejności konfiguruje date i czas protokołem Network Time Protocol.

Przechodzę do wykrycia dysku twardego, gdy system go wybrał, przeszedłem do partycjonowania dysku.

Moge wybrać partycjonowanie z przewodnikiem, skonfigurować dysk iSCSI czyli dysk udostępniany sieciowo lub samemu od podstaw stworzyć partycję po partycji. Ja zdecydowałem się na trzecią opcje.

W pierwszej kolejnosci wybrałem tablice partycji i wybieram gpt.

W systemach linux mozna zainstalowac wszystko na jednej partycji lub podzielić dysk na konkretne.

    / -  partycja głowna, zawierająca system plików i całą reszte systemu

    /home - partycja zawierająca dane użytkownika

    /swap - przestrzen wymiany, umozliwia dodanie pamieci RAM zabierajac miejsce z dysku

    /boot - partycja odpowiedzialna za start systemu

    /tmp - zawiera pliki tymczasowe które są tworzone przez aplikacje w trakcie ich działania

    /var - ta partycja posiada dane zwiazane z działaniem systemu takie jak logi, pliki konfiguracyjne itp.

    partycja danych - dodatkowa partycja na dane


U siebie zastosowałem następujący podział:

    /boot - 500 MB

    / - 4 GB

    /home - 4 GB

    /var - 1 GB

    /tmp - 500MG

Nie zdecydowałem się na partycję /swap ponieważ, łatwiej mi będzie przydzielić więcej ramu z hosta niż dzielić okrojony dysk.

Następnie przechodze do instalacji bazy systemu.
Instalator zapytał mnie o wersję kernela, wybieram tą w wersji 5.10.0.20, następnie dostałem pytanie o sterowniki używane przez kernel.

    Generic - zastosuj wszystkie dostępne sterowniki

    Targeted - zainstaluj sterowniki potrzebne tylko dla tego systemu

Zdecydowałem się na opcje targeted, następnie przeszedłem do konfiguracji managera pakietów
W tej opcji instalator poinformował mnie o tym, że już takowego managera posiadam (apt) i ten krok może być pominięty lub mogę dodać kolejne źródło z instalatorem, zdecydowałem o pominięciu. System zaproponował mi użycie lustrzanej sieci, która uzupełni mój okrojony instalator, zaznaczyłem opcje pozwalajacą na jej użycie, protokołem HTTP. Wybrałem serwer ftp.task.gda.pl, ten znajduję się najbliżej mojej lokalizacji.

System pyta się czy chce korzystać z serwera proxy, nie podaje zadnego adresu, nie chce używać tej opcji.

Teraz stoje przed wyborem pomiedzy dwoma opcjami

    Instalacja boot loadera GRUB

    Instalacja bez boot loadera

Aby móc sprawnie uruchamiać vm, zainstaluje GRUB.

Jedyne co zostało mi do zrobienia to finalizacja instalacji, odpalam opcje, po chwili ładowania system się odpalił.

Po instalacji wyłaczyłem maszyne i wróciłem do 2GB RAM.

## 3. Co tu się stało?

Jak pisałem w podpunkcie 0 moim założeniem było odkrywanie nowych opcji, dlatego zdecydowałem się na instalacje ekspercka.

Liczyłem że tak poznam więcej możliwości lecz ku mojemu zdziwieniu okazało się ze instalacja ta jest okrojona o np. dodanie środowisk graficznych które miałem uwzględnić w tym sprawozdaniu. Dlatego poniżej dodaje listę środowisk graficznych i ich cechy.

    GNOME - najpopularniejsze środowisko graficzne, ma wiele "bajerów" ale czasem ma problemy ze stabilnością

    KDE - środowisko które cechuje się bogatą paletą mozliwosci co do konfiguracji UI

    XFCE - środowisko o niskim zapotrzebowaniu zasobów sprzętowych

    Cinnamon - intuicyjne środowisko zbliżone do Windows 7 i starszych

    LXDE - kolejne środowisko o niskim zapotrzebowaniu na zasoby

    MATE - środowisko oparte na GNOME

    Unity - środowisko z minimalistcznym wyglądem

    Razor-Qt - niewspierane już środowisko, jego założeniami była szybkość i wydajność

    LXQt - połaczenie LXDE i Razor-Qt, ma niskie wymagania,  jest konfigurowalne i modularne a przy tym szybkie


Moja instalacja również nie zapytała się o instalacje "Standard system utilities" więc opiszę jej składniki 
(żródło: https://csmojo.com/posts/what-debian-standard-system-utilities-include.html)

    apt-listchanges - narzędzie do wyswietlania zmian w pakietach
    
    lsof -  wyswietlanie otwartych plików lub procesów

    mlocate - wyszukiwanie plików na podstawie nazwy lub zawartości 
    
    w3m -  przegladarka internetowa z poziomu teminala
     
    at - narzędzie do planowania zadań w systemie
    
    libswitch-perl - biblioteka umożliwiająca korzystanie z instrukcji switch w języku Perl
    
    xz-utils - narzędzie do kompresji i dekompresji plików w formacie XZ
    
    telnet - narzędzie umożliwiające połączenie z innym systemem przez protokół Telnet
    
    dc -  kalkulator w linii poleceń
    
    bsd-mailx - program do wysyłania i odbierania poczty e-mail w systemie
    
    file - narzędzie służące do identyfikacji typu pliku na podstawie jego zawartości
    
    exim4-config - konfiguracja serwera pocztowego Exim
    
    m4 - narzędzie służące do przetwarzania makr tekstowych
    
    bc - kalkulator w linii poleceń
    
    dnsutils - zestaw narzędzi do wykonywania zapytań DNS
    
    exim4 - serwer pocztowy
    
    python2.7 - interpreter języka Python w wersji 2.7
    
    openssh-client - klient SSH
    
    aptitude - zaawansowane narzędzie do zarządzania pakietami w systemie
    
    bash-completion - narzędzie umożliwiające uzupełnianie poleceń w powłoce Bash
    
    python - interpreter języka Python w najnowszej wersji
    
    host - narzędzie do wykonywania zapytań DNS
    
    install-info - narzędzie służące do aktualizacji informacji o zainstalowanych pakietach
    
    bzip2 - narzędzie do kompresji i dekompresji plików w formacie BZip2
    
    reportbug - narzędzie do zgłaszania błędów w pakietach
    
    krb5-locales - zestaw narzędzi umożliwiających korzystanie z protokołu Kerberos
    
    bind9-host - zestaw narzędzi do wykonywania zapytań DNS
    
    time - narzędzie umożliwiające mierzenie czasu wykonywania poleceń
    
    info - narzędzie umożliwiające mierzenie czasu wykonywania poleceń
    
    liblockfile-bin - biblioteka umożliwiająca zarządzanie plikami blokady
    
    whois - narzędzie umożliwiające wyświetlenie informacji o domenach internetowych i ich właścicielach
    
    aptitude-common - wspólne pliki dla narzędzia do zarządzania pakietami aptitude
    
    patch - narzędzie służące do łatania plików
    
    ncurses-term - zestaw terminali obsługujących bibliotekę ncurses
    
    mutt - klient poczty e-mail w linii poleceń
    
    mime-support - biblioteka umożliwiająca obsługę typów plików MIME
    
    exim4-daemon-light - serwer pocztowy Exim w wersji ograniczonej
    
    ftp - klient FTP
    
    nfs-common - narzędzia umożliwiające montowanie systemów plików NFS
    
    python-reportbug - zglaszanie błedów związanych z interpreterem języka Python
    
    rpcbind - narzędzie umożliwiające wykonywanie zdalnych wywołań procedur
    
    texinfo - zestaw narzędzi do generowania dokumentacji w formacie Texinfo
    
    python-minimal - minimalna instalacja interpretera języka Python
    
    procmail - program umożliwiający przetwarzanie poczty e-mail

    libclass-isa-perl - biblioteka umożliwiająca korzystanie z mechanizmu dziedziczenia klas w języku Perl
    
    python-apt - biblioteka umożliwiająca dostęp do repozytoriów pakietów w Pythonie
    
    python-support - narzędzia umożliwiające korzystanie z bibliotek Pythona
    
    exim4-base - podstawowe narzędzia do obsługi serwera pocztowego Exim
    
    debian-faq - dokumentacja zawierająca najczęściej zadawane pytania i odpowiedzi dotyczące systemu Debian
     
    doc-debian - dokumentacja zawierająca opisy różnych aspektów systemu Debian











