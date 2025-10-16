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
Pour trouver notr adresse réseau on peut appliquer l'opération AND sur l'ip et le masque de sous-réseau<br/>
<br/>

| 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  1  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  1  |  0  |  1  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  1  |  1  |  0  |  1  |  0  |  1  |  0  |  0  |  0  |  0  |  1  |  1  |
|  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
|  1  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  1  |  0  |  1  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  1  |  1  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
<br/>
Ca nous donne donc 11000000.10101000.00001101.00000000, ce qui nous donnerais en décimal: 192.168.13.0
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
  
| IPv4 | 128 (2<sup>7</sup>) | 64 (2<sup>6</sup>) | 32 (2<sup>5</sup>) | 16 (2<sup>4</sup>) | 8 (2<sup>3</sup>) | 4 (2<sup>2</sup>) | 2 (2<sup>1</sup>) | 1 (2<sup>0</sup>) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
|  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
|  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
|  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
</details>

<details>
<summary>Méthode du chiffre magique</summary>  
<br/>
Pour 255.255.255.0 l'octet significatif est le dernier octet, 0<br/>
On soustrait 0 de 256, on a donc 256<br/>
On cherche le multiple de 256 le plus proche pour 67, dernier octet de l'adresse IP, ici on obtient 0<br/>
L'adresse réseau est donc 192.168.13.0<br/>
Pour le le broadcast on prend le multiple supérieur le plus proche, ici 256, on soustrait 1<br/>
Cela nous donne pour le broadcast: 192.168.13.255<br/>

</details>
l’adresse de réseau:
l’adresse de broadcast:
le nombre d’adresses utilisables par des machines:
la plage d’adresses disponibles:
</details>

<!-- 3e block - 172.16.27.32/23 -->  
<details>

<summary>Pour l'adresse 172.16.27.32/23</summary>

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
