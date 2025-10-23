# SA2 : Atelier Mme Michu
## Énoncé
> Hello 👋
>
> Aujourd’hui, tu vas devoir diagnostiquer et résoudre plusieurs pannes sur l’ordinateur de Madame Michu, une utilisatrice âgée sympathique qui adore les Yorkshires.
> 
> Voici le message qu’elle t’as envoyé :
>
> >    _Bonjour, Mon ordinateur ne veut plus démarrer correctement, et quand j’arrive enfin sur le Bureau, mon processeur et ma RAM sont utilisés à 100% (elle est balaise, Mme Michu, pour le pré-diagnostic). En plus, j’ai remarqué que des fichiers dans mon dossier « Images » ont disparu ! Je suis inquiète pour l’état de mes disques durs aussi, il parait qu’ils sont défectueux, pourrais-tu les vérifier aussi ? Merci beaucoup de ton aide !_
> >
> Ta mission est de diagnostiquer et corriger les différentes pannes présentes sur la machine de Madame Michu en suivant ces quatre étapes :
>
>    1. **Réparer le démarrage de Windows,**
>    2. **Restaurer les performances normales de la machine,**
>    3. **Vérifier l’état des disques durs,**
>    4. **Retrouver les fichiers disparus dans le dossier « Images ».**
>
> Vu que ce serait contraignant de vous envoyer le PC de Mme Michu par la poste, on va travailler sur une machine virtuelle VirtualBox. Télécharge-la ici au format OVA et commence ta mission 💪
>
> Tu n’auras pas besoin de mot de passe que ce soit pour lancer le fichier OVA ou pour la session de Madame Michu.
> 
> Prends ton temps et suis les étapes dans l’ordre !

## Résultat
J'ai importé et lancé la VM dans virtual box, je vois l'écran noir avec l'erreur, je monte Win10 en lecteur virtuel.

 1    |    2
:-------------------------:|:-------------------------:
<img width="520" height="458" alt="1_ initial" src="https://github.com/user-attachments/assets/30046bed-8aa6-40a3-8c7e-0f666e312bde" /> |  <img width="520" height="363" alt="2_ montage iso" src="https://github.com/user-attachments/assets/4acefaa0-f4cf-4b8b-9a3f-e693eba72143" />

J'ai redémarré sur le cd, choisi "Réparer mon ordinateur personnel", puis "Dépannage" et "Ligne de commande".
Une fois sur la ligne de commande (3), je tape la commande `bootrec /fixmbr`, ca me dit que la commande à reussi, je tape ensuite `bootrec /fixboot`
Ici j'ai un message d'erreur: **Accès refusé**  
je vais donc chercher sur google, trouve des infos (4)
3    |    4
:-------------------------:|:-------------------------:
<img width="1051" height="862" alt="3_ ligne de commande" src="https://github.com/user-attachments/assets/1c2ae318-1e32-4f44-8900-42c18486a9ea" /> | <img width="635" height="899" alt="4_ recherches" src="https://github.com/user-attachments/assets/4da7c7ba-a61f-40b0-be7c-22a69e60aa4f" />

Je lance donc **DiskPart** et lui demande d'Afficher les disques et volumes aves les commandes `list disk` et `list vol`
Je vois les volumes C: au ~ de 50 MO réservé au système et une F: caché de ~ 500 Mo, et le volume E: qui me parait être la partition windows.
je me dis que ca doit être la F:, l'autre me parait trop petite, Je fais la commande `bcdboot E:\windows /s F:`
Je tape ensuite `bootrec /rebuildbcd` , ca me dit que c'est réussi, je redémarre, ca marche pas, je retourne dans la ligne de commande

