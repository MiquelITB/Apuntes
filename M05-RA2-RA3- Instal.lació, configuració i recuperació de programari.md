# Apuntes de M05 - RA2 i RA3
## Sistema operatiu

Els sistemes operatius són els encarregats de permetre, a l’usuari, l’accés a la màquina d’una manera transparent i senzilla.

Les funcions principals d’un sistema operatiu son:

- Interpretar les instruccions que permeten a l’usuari comunicar-se amb
l’ordinador.
- Coordinar i manipular el maquinari del PC, com la memòria, els processadors,
el sistema d’entrada/sortida.
- Gestionar els possibles errors de maquinari i la pèrdua de dades.
- Organitzar els arxius en diversos dispositius d’emmagatzematge, com discos
flexibles, discos durs.
- Servir de base per a la creació del programari, de manera que pugui ser
compatible amb diversos tipus d’equips.
- Configurar l’entorn per a la utilització del programari i els perifèrics.


![Distribució del software](https://github.com/user-attachments/assets/a7438fe6-6ca1-4586-a477-cd3a20f2d90d)


## Conceptes Bàsics

- Programa: fitxer executable creat generalment mitjançant un compilador.
- Procés: programa en execució, te un espai de direccions propi.
- Serveis associats a processos:
Execució arrencat pel sistema.
Arrencat per l’usuari.
Terminació de processos: normal, per error o per altre procés.

![Funcions y modalitats d'un sistema operatiu](https://github.com/user-attachments/assets/6f1d963a-bc2f-4850-9d0e-47e2ba3ec02a)


## Familias de SO
- MS-DOS.
- Windows. 
- UNIX.
- GNU/Linux.
- MAC OS X.


## Eines bàsiques de seguretat
- Antivirus: Eines contra el programari maliciós
- Tallafoc: Eina dque preveu els atacs al sistema

# Copies de Seguretat
## Copia completa/total
Aquest tipus de copies tenen 2 grans inconvenients:
- Requereix d’una gran capacitat per emmagatzemar copies de seguretat.
- Requereix d’una gran quantitat de temps i recursos

## Copia diferencial
- Només copia els fitxers que han estat modificats o creats des de l'última còpia complerta.
- Si fos necessari restaurar les dades, necessitarem la copia total i la última copia diferencial.

  
![Copia diferencial](https://github.com/user-attachments/assets/848d56d7-fa7d-4904-96eb-08c7251dc581)


## Copia incremental
- Només es copien fitxers que han estat creats o modificats posteriorment a l'última còpia de seguretat incremental.
- Hem de diferenciar una còpia de seguretat incremental realitzada per primera vegada de les successives còpies incrementals realitzades posteriorment.
- Quan es realitza per primera vegada es copien tots els arxius, directoris, etc. seleccionats com si fos una còpia total, és a successives còpies, sempre que siguin incrementals, quan només es copien els fitxers modificats o creats posteriorment a l'última còpia que es va realitzar de forma incremental.


![Copia Incremental](https://github.com/user-attachments/assets/37a9f85f-ad34-4953-b28d-34d775341b8d)


## Monitorització i optimització del sistema
El benchmarking es basa en la realització de comparatives d’uns components amb altres per avaluar-ne la qualitat relativa.
Els bechmarks sintètics (syntethic benchmarks) mesuren la capacitat màxima d’aspectes específics d’un sistema mitjançant càlculs o proves repetitives, mentre que els benchmarks d’aplicacions (application benchmarks) mesuren el rendiment de programes reals.


## Classificació del programari

Les aplicacions no incloses en el Sistema Operatiu poden ser classificades bàsicament en dos tipus:

1. Aplicacions horitzontals:
Són aquelles que es podran utilitzar en tot tipus d’organitzacions o per usuaris individuals, com les eines ofimàtiques, el processat de textos o eines de comptabilitat. També se les coneix per aplicacions de propòsit general.

2. Aplicacions verticals:
Són aquelles aplicacions creades amb un propòsit molt concret o concebudes per realitzar tasques molt específiques dins d’un sector o activitat professional. Alguns exemples serien programes per gestionar una clínica dental, per reserva bitllets...


## Aplicacions Portables

Encara que la major part d’aplicacions requereixen d’algun tipus de procés d’instal·lació per ser utilitzades en un ordinador determinat, aquesta condició no és sempre necessària, ja que depenent del disseny del programari, aquest pot ser autocontingut i no necessitar dependències en llibreries del sistema per funcionar.

Una aplicació portable és un programa d’ordinador dissenyat per funcionar sense necessitat d’estar instal·lat en un sistema operatiu.

Les aplicacions portables es poden executar en qualsevol sistema amb què siguin compatibles, però normalment requeriran un sistema operatiu concret.


## Emmagatzemmatge:

Els suports d’emmagatzematge per a imatges de sistema poden ser:

- Locals: tots aquells suports que es troben connectats directament a l’equip a copiar/restaurar.
1. disc intern
2. disc connectat localment
3. unitat òptica

- Remots: implica la realització de la imatge a través d’una xarxa d’ordinadors, i també el seu emmagatzematge en un equip pertanyent a aquesta xarxa.

1. xarxa local: el més comú en la realització d’imatges i la tendència cap a la que es mou l’administració actualment és la realització de les imatges en una xarxa local (LAN). Un ordinador farà la tasca de servidor d’imatges, de manera que tots els equips que tinguin accés a aquesta xarxa puguin ser copiats o restaurats de manera remota.

2. xarxa de llarg abast: no es tracta d’un mètode generalitzat, ja que les velocitats de transmissió de dades no són prou elevades per transmetre tanta quantitat d’informació (continguts sencers d’un equip) en temps viables per a la seva utilització quotidiana.


# Creació i recuperació d'imatges.

El programari de **clonatge de discos** es basa en la creació d’una imatge exacta del disc dur de l’ordinador, fent una “instantània” de tots els fitxers (tant els ocults com els visibles) que componen el sistema operatiu, les aplicacions i la configuració.

**L’origen** i **la destinació** dels clonatges és un paràmetre decisiu. 

Els clonatges es poden fer de tot un disc o d’alguna de les particions, i emmagatzemar el contingut tal com es troba en l’origen o bé empaquetar-lo en un arxiu imatge.

Hi ha quatre opcions que cal tenir en consideració:

1. Còpia de tot el contingut d’un disc a un altre.
2. Creació d’un arxiu d’imatge d’una unitat i utilització d’aquest arxiu per crear clons complets del disc original.
3. Còpia del contingut d’una partició a una altra.
4. Creació d’un arxiu d’imatge d’una partició de disc, que es pot usar com a plantilla per crear altres particions.

Mitjançant els **sistemes de compressió d’imatges**, es pot reduir significativament la quantitat d’espai que es necessita per a un arxiu d’imatge. De fet, les imatges es poden arribar a comprimir fins a un 70%, en funció del mètode de compressió escollit i el contingut de la partició o del disc.
