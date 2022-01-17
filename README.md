# DOCKER SECURITY - LABORATORIA

<br/>

[PREZENTACJA](https://docs.google.com/presentation/d/1NpSKP3a9LD0olcxBPlbMGAGW8fOFvbmn/edit?usp=sharing&ouid=107243582246751591466&rtpof=true&sd=true)

<br/>

## Przed rozpoczęciem

Przed rozpoczęciem pracy z laboratoriami należy pobrać oraz uruchomić maszynę wirtualną: [Maszyna](https://1drv.ms/u/s!AvkfILhpQ62nhFH_BMR7wTQoOB6_?e=jjwcUx).

Maszynę należy uruchomić w programie VMware

---

## Zadanie 2

Odzyskaj z wartsw obrazu flagę
<br/>
[Link do obrazu](https://hub.docker.com/layers/qxxxb/layers/latest/images/sha256-a89678536727abc0fbfe693b19ac0f8454502351dc792dabbee47bc9ab7420b2?context=explore)

---
## Zadanie 3


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
