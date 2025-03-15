<!-- Markdown comments are html ones -->

([Tornada al web de problemes](index.md))

# FAQ #

Preguntes freqüents que sorgeixen als grups G10 i G40 de problemes de mecànica.

<!-- Bon curs a tots!  -->

## Índex

iP = Sessió de la setmana i-èssima

+ [1P: Derivació geomètrica](#1p-derivació-geomètrica)  
+ [2P: Derivació analítica](#2p-derivació-analítica)  
+ [3P: Angles d'Euler](#3p-angles-deuler)  
+ [4P: Composició de moviments](#4p-composició-de-moviments)  
+ [5P: Cinemàtica del sòlid rígid 3D](#5p-cinemàtica-del-sòlid-rígid-3d)  
+ [6P: Cinemàtica del sòlid rígid 2D](#6p-cinemàtica-del-sòlid-rígid-2d)   
+ [Bibliografia](#bibliografia) 
+ [Enllaços](#enllaços) 
 


## 1P: Derivació geomètrica

**Dieu que un vector té valor i direcció, però sempre ens han dit que té mòdul, direcció i sentit. Com es reconcilien les dues caracteritzacions?**

A l'assignatura representem un vector amb una fletxa i un valor indicat a sobre. La fletxa indica la "direcció i el sentit genèric positiu" del vector, és a dir la direcció i el sentit del vector, tal i com us els han ensenyat fins ara. El valor és, diguem-ho així, el "mòdul amb signe". Si el signe és positiu, vol dir que el vector apunta cap on indica la fletxa. Si és negatiu, apunta en sentit contrari. A l'assignatura acostumem a dir que un vector ve donat "pel seu valor i la seva direcció", però en realitat volem dir "pel seu valor i la seva direcció *amb sentit genèric positiu*". Per no fer-ho tan llarg diem simplement "pel seu valor i direcció". És un petit abús de llenguatge que permet agilitzar les descripcions.

En alguns exercicis parlarem de la direcció d'un vector per a referir-nos a l'orientació de la seva recta suport, sense sentit associat. Per context ja quedarà clar que ens estem referint a això, i no a la "direcció amb sentit genèric positiu del vector".

## 2P: Derivació analítica

Pendent d'afegir preguntes.

## 3P: Angles d'Euler

**En l'exercici del dau fet a 3P, els eixos psipunt, thetapunt i phipunt de la configuració final es troben en una singularitat. Vol dir això que l'eix thetapunt en realitat no està definit?**

No, no ho vol dir! L'eix thetapunt sí que està definit en aquest problema, perquè ens diuen la seqüència de rotacions que pateix el dau fins arribar a la configuració final. Si no ens la diguessin, i haguéssim de deduir on és aquest eix a partir de l'orientació final dels eixos psipunt i phipunt, és cert que thetapunt quedaria indeterminat, perquè ha de ser en la intersecció dels plans 
"ortogonal a phipunt" i "ortogonal a psipunt", que en la configuració final del dau coincideixen per causa de la singularitat. Les singularitats dels angles d'Euler tenen impacte en la simulació dinàmica de sistemes multisòlid, però en aquest curs no entrarem en aquests aspectes avançats. Els problemes que donen aquestes singularitats es poden resoldre utilitzant dues famílies d'angles d'Euler diferents, i saltant de l'una a l'altra quan arribem a una singularitat, o bé utilitzant quaternions.

## 4P: Composició de moviments

**Quina és la diferència entre un vector general (o "pel·lícula") i un vector particularitzat (o "foto")?** 

* Vector general, o "pel·lícula" = Un que és vàlid per a tota configuració del sistema (per a tot instant de temps). Són els vectors obtinguts a partir d'una configuració genèrica del sistema (per a valors genèrics de les coordenades x, theta, phi, ... amb les que treballem). N'és un exemple el vector velocitat de G per a la placa articulada giratòria.

* Vector particularitzat, o "foto" = Un que només és vàlid per a una configuració concreta. Són els obtinguts a partir d'una configuració especial del sistema, en un cert instant. N'és un exemple, la velocitat de P en el disc de 2 GL, quan P passa per la posició més alta.

Els vectors pel·lícula es poden derivar per obtenir velocitats o acceleracions. Per exemple, a la placa articulada giratòria, podem derivar la velocitat absoluta de **G** i obtindrem l'acceleració de **G** de manera correcta. A classe vam obtenir l'acceleració per composició de moviments, però a [4P.pdf](problemes/4P.pdf) hi trobareu també l'altra via: derivant un vector pel·lícula de posició (dues vegades). 

Els vectors foto no es poden derivar. En el disc de 2 GL no podem derivar el vector de velocitat obtingut a classe per obtenir l'acceleració, perquè està obtingut per al cas en que **P** passa pel punt més alt. ¿Com obtindríem un vector pel·lícula de velocitat en aquest exemple? Ho teniu explicat a [4P.pdf](problemes/4P.pdf), on ensenyo, a més, que si particularitzem aquest vector per al cas en que **P** passa pel punt més alt, obtenim el vector de classe, com era d'esperar! Aquesta via alternativa és més feixuga, fent palesa la superioritat de la composició de moviments en aquest cas.

La denominació vector "pel·lícula" o "foto" és del tot informal. Quan hagueu de ser formals digueu vector "general" o "particularitzat", respectivament.

## 5P: Cinemàtica del sòlid rígid 3D

**A la qüestió de les rodes dentades, O és un punt de la roda vertical "RV" perquè la distància des de O a qualsevol punt de RV és fixa. Fins aquí, d'acord. Però, aplicant el mateix argument, ... no podem veure O' com a punt de RV també?**

No, no podem. Fixem-nos, per exemple, que **O'** no manté fixa la seva distància al punt **S** de **RV**. En l'instant del dibuix, aquesta distància val $2r$, però instants més tard ja no. En concret, quan **S** tingui l'altura de **Q**, aquesta distància valdrà $\sqrt{r^2 + r^2 + (2r)^2} = r\sqrt{6} \approx 2.45 r$, que és més gran que $2r$.

**A l'exercici de l'anell sobre plataforma, podem deduir la relació $\dot{\theta} = f(\dot{\psi},\dot{\varphi})$ utilitzant el fet que JO és $\textsf{EI}^\text{Roda}_\text{Plat}$?**

Sí, efectivament! Seria un mètode alternatiu. Us en dono pistes per tal que l'intenteu: 

Adonem-nos que

$$\bar{\Omega}^\text{Roda}_\text{T} = \bar{\Omega}^\text{Roda}_\text{Plat} + \bar{\Omega}^\text{Plat}_\text{T}.$$

Partint d'aquesta equació, podem aillar $ {\bar{\Omega}^\text{Roda}_\text{Plat}} $ en funció de les altres dues omegues. Aquestes dues omegues es poden escriure vectorialment en funció de $\dot{\psi}$, $\dot{\theta}$, i $\dot{\phi}$, i han de donar, sumades, un vector en la direcció de $\textsf{EI}^\textsf{Roda}_\textsf{Plat}$ (la recta **JO**). Això genera un triangle rectangle d'omegues que permet deduir la relació $\dot{\theta} = f(\dot{\psi},\dot{\varphi})$ desitjada!

## 6P: Cinemàtica del sòlid rígid 2D

Pendent d'afegir preguntes.

