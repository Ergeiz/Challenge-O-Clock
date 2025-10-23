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
Ici j'ai un message d'erreur: *Accès refusé*  
je vais donc chercher sur google, trouve des infos (4)  

3    |    4
:-------------------------:|:-------------------------:
<img width="1051" height="862" alt="3_ ligne de commande" src="https://github.com/user-attachments/assets/1c2ae318-1e32-4f44-8900-42c18486a9ea" /> | <img width="635" height="899" alt="4_ recherches" src="https://github.com/user-attachments/assets/4da7c7ba-a61f-40b0-be7c-22a69e60aa4f" />

Je lance donc **DiskPart** et lui demande d'Afficher les disques et volumes aves les commandes `list disk` et `list vol`  
Je vois les volumes C: au ~ de 50 MO réservé au système et une F: caché de ~ 500 Mo, et le volume E: me parait être la partition windows. (5)  
je me dis que ca doit être la F:, l'autre me parait trop petite, Je fais la commande `bcdboot E:\windows /s F:`  
Je tape ensuite `bootrec /rebuildbcd` , ca me dit que c'est réussi, je redémarre, **ca marche pas** 🤨  
Je retourne dans la ligne de commande en me disant "Bon c'était C: la partition système"

Entre-temps j'apperçois le post sur Slack redonnant les commandes, je recharge une snapshot, je tape les commandes `bootrec /fixmbr`, `bcdboot E:\Windows`, et `bootrec /rebuildbcd`  
Je sors de la ligne de commande, clique sur "poursuivre sur Windows 10" et j'arrive devant l'ecran bleu (6)  

5    |    6
:-------------------------:|:-------------------------:
<img width="1026" height="854" alt="5 DiskPart" src="https://github.com/user-attachments/assets/a8e92aa5-09c6-4223-8d1f-f102570865a2" /> | <img width="1026" height="854" alt="blue" src="https://github.com/user-attachments/assets/d9376c86-b34d-4f4e-aed3-9d4e69a41da9" />

Ainsi je vois sur le blue screen qu'il manque Winload.exe, je retourne à la ligne de commande et me dit qu'un petit chkdsk pourrait être une bonne idée.  
Je tape donc `chkdsk /R /F` sur E:. Et je vais le regretter car j'ai assez vite l'impressions que le chkdsk va durer des plombes ! (7)  
La vérification se termine en ne trouvant pas d'erreur, j'opte donc pour lancer l'**Outil de redémarrage système** voir ce que ça donne.  
Et J'arrive sur l'écran d'accueil Windows 😊(8)  

7    |    8
:-------------------------:|:-------------------------:
<img width="1026" height="854" alt="7 chkdsk" src="https://github.com/user-attachments/assets/b9c9dfbd-ac2c-4dce-a3e7-f1e2830ef5ad" /> | <img width="1154" height="950" alt="8 accueil" src="https://github.com/user-attachments/assets/af6e97a4-a532-408e-b6ae-e0fd23dff8ac" />

à partir de là, je lance le gestionnaire des tâche (9), je vois CPU et RAM surchargé, et aussi pleins de processus ping, je suppose un soucis avec le réseau.  
Je jette un oeil à l'observateur d'événement, je ne vois rien qui me saute au yeux, je vois dans la barre des tâche l'icone du **centre de sécurité Windows** pour des actions recommandés, je vais donc fouiller dans la configuration du centre de sécurité.  
Je regarde les actions recommandées, protection contre les virus et menace, protection du compte, OneDrive, et dans l'onglet "Contrôle des applications et du navigateur", je vois l'option "Protection fondée sur la réputation", je l'active, je ne touche pas à OneDrive et le reste.  
Peu de temps après plus de surcharge du cpu et de la ram. (10)

9    |    10
:-------------------------:|:-------------------------:
<img width="1154" height="950" alt="9 tache1" src="https://github.com/user-attachments/assets/19238934-e0a1-435f-b92c-a88a350ac770" /> | <img width="1154" height="950" alt="10 tache2" src="https://github.com/user-attachments/assets/6f17cd23-162c-4cf9-89f7-a624d7a4bec0" />

Cétait un peu du pif mais bon on va pas se plaindre.  
Maintenant il faut retrouver les fichiers de madame Michu !
J'active l'option "afficher les dossiers cachés" au ca où, je lis le fichier **S O S !**, j'apprend que le dossier York à été effacé.  
Je vais voir si l'**Historique des fichiers** avait été activé, et coup de bol c'est le cas ! (11)
Je cherche donc de rétablir le dossier York à son emplacement, mais apparemment il est sur un volume qui n'est pas connecté (12)

11    |    12
:-------------------------:|:-------------------------:
<img width="1154" height="950" alt="11" src="https://github.com/user-attachments/assets/84e93c01-8111-4d87-943c-d50f886db615" /> | <img width="1154" height="950" alt="12" src="https://github.com/user-attachments/assets/6772d0a8-605e-4562-b368-1740cacec196" />

Je part dans le **Gestionnaire des disques**, je vois le disque 1 Hors co, je le connecte d'un click droit, je retourne dans l'historique des fichiers, et je restaure le dossier York, madame Michu sera ravie ! 😁 

13    |    14    |   15
:-------------------------:|:-------------------------:|:-------------------------:
<img width="1154" height="950" alt="13" src="https://github.com/user-attachments/assets/4e66657f-53f5-4e26-8413-ce1eeada5026" /> | <img width="1154" height="950" alt="14" src="https://github.com/user-attachments/assets/4cedeb1e-a950-4300-a0d6-7b94b0c04f6c" /> | <img width="1154" height="950" alt="15" src="https://github.com/user-attachments/assets/2345c021-7888-4ae7-beb2-ca804717071e" />







