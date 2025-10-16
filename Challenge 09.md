# Challenge 09

## Énoncé

> Pour les adresses IP et masques de sous-réseau suivants, calculez :
>
>   l’adresse de réseau
>   l’adresse de broadcast
>    le nombre d’adresses utilisables par des machines
>    la plage d’adresses disponibles
>
> Certains utilisent la notation « classique », d’autres la notation CIDR :
>
>    192.168.13.67/24\
>    172.16.0.1 – 255.255.255.0\
>    172.16.27.32/23\
>    10.7.5.1 – 255.255.128.0\
>    10.42.0.82/12
>
> Essayez de calculer tout à la main (avec la méthode de votre choix, idéalement essayez d’utiliser les deux !), 
> puis vérifiez vos calculs avec une calculatrice en ligne ([exemple](https://www.subnet-calculator.com/cidr.php)) !

<!-- 1er block - 192.168.13.67/24 -->
<details>

<summary>Pour l'adresse 192.168.13.67/24</summary>


<details>
<summary>Méthode binaire</summary>
  <br/>
Sachant que le masque /24 vaut 11111111.11111111.11111111.00000000 en binaire<br/>
On peut transcrire l'adresse IP en binaire<br/>
<br/>
  
| IPv4 | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  192  |  1  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |
|  168  |  1  |  0  |  1  |  0  |  1  |  0  |  0  |  0  |
|  13  |  0  |  0  |  0  |  0  |  1  |  1  |  0  |  1  |
|  67  |  0  |  1  |  0  |  0  |  0  |  0  |  1  |  1  |
<br/>
L'IP en binaire est donc: 11000000.10101000.00001101.01000011
<br/>
Pour trouver notr adresse réseau on peut appliquer l'opération AND avec l'IP et le masque de sous-réseau<br/>
<br/>

| 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  1  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  1  |  0  |  1  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  1  |  1  |  0  |  1  |  0  |  1  |  0  |  0  |  0  |  0  |  1  |  1  |
|  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
|  1  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  1  |  0  |  1  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  1  |  1  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
<br/>
Ca nous donne donc 11000000.10101000.00001101.00000000, ce qui donnerait en décimal: 192.168.13.0
on a donc notre adresse de réseau<br/>
Puisque que l'on a un masque en /24 (8 bits de 0 sur le dernier octet), ca nous donne le broadcast à 192.168.13.255 
</details>

<details>
<summary>Méthode du chiffre magique</summary>  
<br/>
/24 équivalent à 255.255.255.0, l'octet significatif est le dernier octet, 0<br/>
On soustrait 0 de 256, on a donc 256<br/>
On cherche le multiple de 256 le plus proche pour 67, dernier octet de l'adresse IP, ici on obtient 0<br/>
L'adresse réseau est donc 192.168.13.0<br/>
Pour le le broadcast on prend le multiple supérieur le plus proche, ici 256, on soustrait 1<br/>
Cela nous donne pour le broadcast: 192.168.13.255<br/>

</details>
l’adresse de réseau: 192.168.13.0<br/>
l’adresse de broadcast:192.168.13.0<br/>
le nombre d’adresses utilisables par des machines:254<br/>
la plage d’adresses disponibles: de 192.168.13.1 à 192.168.13.254  ('adresse de réseau ne peut pas être attribué à une machine, ni l'adresse de broadcast)<br/>
</details>



<!-- 2e block - 172.16.0.1 – 255.255.255.0 -->
<details>

<summary>Pour l'adresse 172.16.0.1 – 255.255.255.0</summary>

<details>
<summary>Méthode binaire</summary>
<br/>
On sait qu'en binaire, 255.255.255.0 équivaut à 11111111.11111111.11111111.00000000<br/>
On veut l'adresse IP en Binaire:<br/>
  
| IPv4 | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  172  |  1  |  0  |  1  |  0  |  1  |  1  |  0  |  0  |
|  16  |  0  |  0  |  0  |  1  |  0  |  0  |  0  |  0  |
|  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
|  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  1  |

Ca nous donne : 10101100.00010000.00000000.00000001<br/>
On passe l'IP et le masque de sous-réseau à la moulinette du AND<br/>

| 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  1  |  0  |  1  |  0  |  1  |  1  |  0  |  0  |  0  |  0  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  1  |
|  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
|  1  |  0  |  1  |  0  |  1  |  1  |  0  |  0  |  0  |  0  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
<br/>
ce qui nous donne : 10101100.00010000.00000000.00000000, donc 172.16.0.0<br/>
étant donné que le dernier octet du masque est un 0 (la plage des adresses utilisables est sur 8bits) on sait que le broadcast est 172.16.0.255<br/>
</details>

<details>
<summary>Méthode du chiffre magique</summary>  
<br/>
Pour 255.255.255.0 l'octet significatif est le dernier octet, 0<br/>
On soustrait 0 de 256, on a donc 256<br/>
On cherche le multiple de 256 le plus proche pour 1, dernier octet de l'adresse IP, ici on obtient 0<br/>
L'adresse réseau est donc 172.16.0.0<br/>
Pour le le broadcast on prend le multiple supérieur le plus proche, ici 256, on soustrait 1<br/>
Cela nous donne pour le broadcast: 172.16.0.255<br/>

</details>
l’adresse de réseau: 172.16.0.0 <br/>
l’adresse de broadcast: 172.16.0.255 <br/>
le nombre d’adresses utilisables par des machines: 254<br/>
la plage d’adresses disponibles: de 172.16.0.1 à 172.16.0.254 <br/>
</details>

<!-- 3e block - 172.16.27.32/23 -->  
<details>

<summary>Pour l'adresse 172.16.27.32/23</summary>

<details>
<summary>Méthode binaire</summary>
<br/>
 Le masque /23 équivaut en notation binaire à 11111111.11111111.11111110.00000000<br/>
 On cherche l'adresse IP en binaire<br/>
  
| IPv4 | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  172  |  1  |  0  |  1  |  0  |  1  |  1  |  0  |  0  |
|  16  |  0  |  0  |  0  |  1  |  0  |  0  |  0  |  0  |
|  27  |  0  |  0  |  0  |  1  |  1  |  0  |  1  |  1  |
|  32  |  0  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |

Cela nous donne pour l'adresse IP: 10101100.00010000.00011011.00100000<br/>
Pour l'adresse IP du réseau on met l'adresse IP et le masque de sous-réseau dans le chappeau avec le AND<br/>
<br/>

| 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  1  |  0  |  1  |  0  |  1  |  1  |  0  |  0  |  0  |  0  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  1  |  1  |  0  |  1  |  1  |  0  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |
|  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
|  1  |  0  |  1  |  0  |  1  |  1  |  0  |  0  |  0  |  0  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  1  |  1  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
<br/>
Cela nous donne: 10101100.00010000.00011010.00000000, en decimal:172.16.26.0<br/>
Maintenant on doit trouver le broadcast par une opération NOT sur le masque, puis une opération OR avec l'adresse obtenue et l'adresse réseau:<br/>
NOT masque: 00000000.00000000.00000001.11111111<br/>
Opération OR:<br/>
<br/>

| 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  1  |  0  |  1  |  0  |  1  |  1  |  0  |  0  |  0  |  0  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  1  |  1  |  0  |  1  |  1  |  0  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |
|  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |
|  1  |  0  |  1  |  0  |  1  |  1  |  0  |  0  |  0  |  0  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  1  |  1  |  0  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |
<br/>

Ca nous donne comme adresse de broadcast: 10101100.00010000.00011011.11111111, ce qui nous donne en décimal:172.16.27.255<br/>
</details>
<details>
<summary>Méthode du chiffre magique</summary>  

172.16.27.32/23

L'octet significatif du masque de sous-réseau étant le 3e, la plage se détèrminera sur l'octet 27 de l'adresse IP<br/>
On soustrait 254 de 255, ca nous donne 1, on cherche le multiple de 1 le plus proche inférieur pour 27, ici 26, on met 0 sur les octets suivants<br/>
Donc pour l'adresse réseau: 172.16.26.0
Pour le broadcast, on prend le multiple supérieur le plus proche - 1, donc ici 28-1, et on mets les octets suivants à 255,  donc : 172.16.26.255




</details>
l’adresse de réseau: 127.16.26.0<br/>
l’adresse de broadcast: 127.16.27.255<br/>
le nombre d’adresses utilisables par des machines: 510<br/>
la plage d’adresses disponibles: de 127.16.26.1 à 127.16.27.254<br/>
</details>

<!-- 4e block 10.7.5.1 – 255.255.128.0 -->
<details>

<summary>Pour l'adresse 10.7.5.1 – 255.255.128.0</summary>

<details>
<summary>Méthode binaire</summary>
<br/>
  
| IPv4 | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
|  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
|  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
|  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
</details>
<details>
<summary>Méthode du chiffre magique</summary>  

</details>
l’adresse de réseau:
l’adresse de broadcast:
le nombre d’adresses utilisables par des machines:
la plage d’adresses disponibles:
</details>

<!-- 5e block - 10.42.0.82/12 -->
<details>

<summary>Pour l'adresse 10.42.0.82/12</summary>

<details>
<summary>Méthode binaire</summary>
<br/>
  
| IPv4 | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
|  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
|  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
|  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
</details>
<details>
<summary>Méthode du chiffre magique</summary>  

</details>
l’adresse de réseau:
l’adresse de broadcast:
le nombre d’adresses utilisables par des machines:
la plage d’adresses disponibles:
</details>
