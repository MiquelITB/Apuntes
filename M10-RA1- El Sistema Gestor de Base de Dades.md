# El Sistema Gestor de Base de Dades

## Els Fitxers
Els fitxers emmagatzemmen informació amb les mateixes característiques en quant a estructura significant i tractament. Hi ha de 3 categories:

#### 1. Registre Lògic:
Conjunt d’informació que identifica un dels elements a que fa referència el fitxer. Un registre està format per unitats elementals que s’anomenen **camps**.

#### 2. Registre Físic:
Registre físic (o bloc) és la unitat de transmissió sobre memòries auxiliars. Serveix com a transport de memòria principal a suport extern i vicebersa. Generalment un bloc és de 512 bytes.

#### 3. Factor de Bloqueig
És la relació que existeix entre el R.Lògic i el R.Físic. Quants R.Lògics caben en un R.Físic.

FB = Nº RL / Nº RF

## Tipus de Fitxers

- **Fitxers Permanents** Són aquells que perduren més en el sistema. I els podem subdividir en tres tipus:

  - Fitxers Constants
Pràcticament mai canvien (Taules periòdiques, taules matemàtiques, ...)

  - Fitxers Mestres o de Situació
Son susceptibles de tenir canvis (Alumnes, els meus llibres, ...)

  - Fitxers Històrics
O també anomenats d’informació referent (Resum de transaccions de l’empresa...)

- **Fitxers de moviments**: Són els que contenen registres que son el resultat d’actualitzacions en un fitxer de situació. La seva vida és curta, quan s’ha fet l’actualització del fitxer de situació, el podem esborrar-lo o esperar en el següent fitxer d’actualització per esborrar-lo.

- **Fitxers de maniobra (Temporals)**: Són els fitxer amb resultat intemitjos en una aplicació. El mateix procés que els crea els destrueix.

## Organització dels Fitxers

### 1. Organització Seqüencial
Els registres s’insereixen l’un darrera l’altre. Després de creat, el fitxer es pot ordenar per algun dels seus camps. Serà una bona organització quan després s’ha de consultar gran part del fitxer

### 2. Organització Directa
Ens trobarem amb dos tipus diferents. En els dos casos tenim reservat el nombre màxim de registres que utilitzarem.

a) La direcció física de emmagatzemen la dona el propi identificador.

b) La direcció de emmagatzemen s’obté d’haver fet una operació s’obre
l’identificador.

### 3. Organització Seqüencial Indexada
Intenta agafar el millor de l’organització seqüencial (accés a un gran nombre de registres) i el millor de l’organització directa (ràpid accés a un registre). Consta de dues parts les dades i els índex.

## Accés a les dades

a) **Accés Seqüencial per Posició**:
Després d’haver accedit al registre que ocupava la posició p accedirem al registre que ocupa la posició p+1

b) **Accés Directe per Posició**:
En el accés directe per posició es demana accedir al registre que ocupa una posició determinada sense que prengui rellevància el contingut. Es fa servir en recerques dicotòmiques 1 , o també en el Hashing.

c) **Accés Seqüencial per Valor**:
Després d’haver accedit al registre que té un determinat valor, en un dels seus camps, accedirem al registre amb el valor següent en el camp. Ens caldrà tenir un Índex per aquest camp.

d) **Accés Directe per Valor**:
Ens demana accedir al registre que té un determinat valor en un dels seus camps. També ens cal la presencia d’un índex per el camp en contret.

|              | Seqüencial | Directe |
|-------------|-----------|---------|
| **Posició** | SP        | DP      |
| **Valor**   | SV        | DV      |


## Nivell Lògic i Nivell Físic
El registre de les dades, l’organització i l’accés es pot veire des d’un punt més o menys llunyà a la realització física (com estan realment gravades les dades, com s’accedeix al disc,...)

- Nivell Lògic:
És el nivell del que s’encarrega un programador (amb C, Cobol, Pascal, ...) Pot pensar que un fitxer està composat per registres i que aquest estan format per camps i no preocupar-se de com s’accedeix a les dades.

- Nivell Físic:
És el nivell del que s’encarrega un programador de sistemes, un dissenyador de BD. Necessita saber com és la realització física.












