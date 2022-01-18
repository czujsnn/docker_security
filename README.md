# DOCKER SECURITY - LABORATORIA


## [PREZENTACJA](https://docs.google.com/presentation/d/1NpSKP3a9LD0olcxBPlbMGAGW8fOFvbmn/edit?usp=sharing&ouid=107243582246751591466&rtpof=true&sd=true)


## Przed rozpoczęciem

Przed rozpoczęciem pracy z laboratoriami należy pobrać oraz uruchomić maszynę wirtualną: [Maszyna](https://1drv.ms/u/s!AvkfILhpQ62nhFH_BMR7wTQoOB6_?e=jjwcUx).

Maszynę należy uruchomić w programie VMware

---

## Zadanie 1

Odzyskaj z warstw obrazu flagę
<br/>
[Link do obrazu](https://hub.docker.com/layers/qxxxb/layers/latest/images/sha256-a89678536727abc0fbfe693b19ac0f8454502351dc792dabbee47bc9ab7420b2?context=explore)

---
## Zadanie 2

Uzyskaj dostęp na konto root za pomocą podatności CVE 2019-5736 <br/>
Wszystkie pliki potrzebne do wykonania zadania znajdują się w folderze **RunC-CVE-2019-5736** na pulpicie pobranej maszyny wirtualnej <br/>

**W razie problemów prosimy skorzystać z pliku README.md**
```
~/Desktop/RunC-CVE-2019-5736/README.md
```

**UWAGA!** Przed każdą próbą uruchomienia obrazu należy wykonać następujące polecenia:<br/>
![komendy](https://cdn.discordapp.com/attachments/279340834074263561/932684626512728124/unknown.png)

---
## Zadanie 3

Zabezpiecz obraz z zadania numer 2, aby uniemożliwić ucieczkę z kontenera.
`(podpowiedź - Docker Image best practices)`

## Zadanie 4

Zainstaluj Skaner obrazów - Trivy - polecenia:
```
wget https://github.com/aquasecurity/trivy/releases/download/v0.18.3/trivy_0.18.3_Linux-64bit.deb
sudo dpkg -i trivy_0.18.3_Linux-64bit.deb
```

Następnie stwórz prosty Dockerfile:
```
FROM debian:latest
```
a) Zbuduj obraz za pomocą docker build

b) Dokonaj skanu obrazu: trivy image `<nazwa_obrazu>` > wynik.txt

c) Wynik skanu będzie dostępny w pliku wynik.txt, otwórz go, przenalizuj i zwróć uwagę na liczbę poszczególnych podatności i ich dotkliwość.

Następnie stwórz kolejny Dockerfile:
```
From ubuntu:latest
```

i wykonaj kroki a) b) c) ponownie, wnioski nasuwają się same :)

<br/><br/>
---
<br/><br/><br/><br/><br/><br/>
Analyze image from dockerhub - "revert deletion of a file from layer"

Presentation stuff:

1. Co to docker (5/10 min) - co to kontenery/konteneryzacja itd, jak działają warstwy, kontenery - shared kernel, namespace dockera - po co, najwazniejsza szkoda - dostep do kernela - mamy wszystkie kontenery) zalety dockera - skalowanie, oszczednosc pamieci - budowanie na warstwie, 
2. Zastosowanie dockera, jakies staty, https://www.docker.com/blog/docker-index-dramatic-growth-in-docker-usage-affirms-the-continued-rising-power-of-developers/
 chyba najwazniejsze zastosowanie dockera - kubernetes, orkiestracja kontenerów,
 kontenery praktycznie tylko wykorzystywane bo góruja mikroserwisy
3. security dockera - case study z obrazem debiana - 150 błędów, w chuj krytycznych, a po upgradzie na ubuntu bazowego obrazu - mamy 0 krytycznych i calosciowo z 20 średnich błędów - nic takiego
narzedzia skanowania - snyk/ to gówno z github actions - ja wiem ocb

4. Best practices - albo to włączyć do security bo jeden pies, 
nie tworzenie dodatkowych userów - te principale,
przelaczanie sie na zwyklego usera na koncu zeby nie byc rootem bo execu terminala na kontenerze, nie towrzenie root userów, omijanie uzywania tagu latest
