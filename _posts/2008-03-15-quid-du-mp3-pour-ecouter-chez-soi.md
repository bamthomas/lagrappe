---
layout: post
title: "Quid du MP3 pour écouter chez soi ?"
date: "2008-03-15"
---

Je reprends un mail envoyé il y a peu, car d'autres personnes que les destinataires sont intéressées.

Récemment, nous avons eu la chance de pouvoir nous offrir des nouvelles enceintes : des kefs iQ9 et puis nous avons ajouté une [squeezebox](http://www.slimdevices.com/pi_squeezebox.html) (pour mon anniv), pour le côté pratique et informatique.

Du coup, nous avons **vraiment** pu comparer le son du mp3 avec cd d'origine et flac dans la mesure où nous avions une bonne fidélité de la partie hifi, et un bon convertisseur analogique/numérique (constitué par la squeezebox) non perturbé par les ondes electromagnétiques de l'ordinateur (ce qui est le cas avec une carte son). Pour ce faire, on lit une chanson encodée (mp3 ou flac) sur la squeezebox, et on démarre en même temps la même chanson sur CD. Ensuite, on bascule entre les voies auxiliaire et CD sur l'ampli. En mettant un peu fort et en se positionnant bien devant, au milieu des enceintes, ça pardonne pas...

Pour ceux qui ne connaissent pas le flac, c'est un format sans perte de données (un peu comme fait zip mais optimisé pour la musique), et libre qui commence à être de plus en plus répandu (mais il y a d'autres format sans perte, notamment apple a le sien) vous trouverez plein d'info là dessus : [http://flac.sourceforge.net/](http://flac.sourceforge.net/). Mais pour montrer ce qu'est un format sans perte, un exemple vaut mieux qu'une longue explication : Prenons un fichier wav issu d'un CD : `24526700 2008-03-16 11:11 une_chanson.wav` Ce fichier fait 24,5 Mo et des poussières. On l'encode en flac et on regarde sa taille : `flac --best` `une_chanson``.wav 15141465 2008-03-16 10:13` `une_chanson``.flac` On décode maintenant le flac en wav : `flac -dcs` `une_chanson``.flac -o` `une_chanson``.flac.wav 24526700 2008-03-16 10:13` `une_chanson``.flac.wav` On voit que le fichier est à l'octet près (24 526 700) le même que le fichier source. On peut même faire une somme de contrôle pour vérifier si les 2 fichiers sont identiques : `md5sum` `une_chanson``.wav 259acf3400dedea2954cdd1fb516ea38` `une_chanson``.wav md5sum` `une_chanson``.flac.wav 259acf3400dedea2954cdd1fb516ea38` `une_chanson``.flac.wav` Les fichiers sont bien identiques, flac est une fonction bijective.

Réalisons maintenant la même opération avec le mp3 : Encodage : `lame -v --preset extreme -h` `une_chanson``.wav` `une_chanson``.mp3 4099152 2008-03-16 15:48` `une_chanson``.mp3` Décodage : `lame --decode` `une_chanson``.mp3` `une_chanson``.mp3.wav 24533224 2008-03-16 10:42` `une_chanson``.mp3.wav` Surprise ! Le fichier wav résultant de l'encodage en mp3 et du décodage du mp3 en wav est plus gros que fichier wav d'origine (24533224 contre 24526700). En fait c'est parce que le décodage ajoute des 0 en début et en fin de fichier wav. Pour plus d'infos, vous pouvez aller voir [ce lien](http://lame.sourceforge.net/tech-FAQ.txt). Maintenant réencodons ce fichier wav en mp3 pour pouvoir comparer avec le premier mp3 : `lame -v --preset extreme -h` `une_chanson``.mp3.wav` `une_chanson``.mp3.wav.mp3 ls -l` `une_chanson*``.mp3 4043823 2008-03-16 15:59` `une_chanson``.mp3.wav.mp3 4099152 2008-03-16 11:12` `une_chanson``.mp3` Ici, on voit bien que le fichier mp3.wav.mp3 (codage mp3 décodage wav codage mp3) est plus petit que le premier issu du wav d'origine. On a donc perdu de l'information.

Et alors ? Si la différence ne se perçoit pas à l'écoute! C'est pourquoi on a voulu tester dans de bonnes conditions (on peut sûrement faire mieux en chambre d'écoute avec du meilleur matos). On a pu entendre que :

- le mp3 même encodé en `--preset extreme` avec lame (VBR jusqu'à 320kbps) ne tient pas la route : le son est plat, les graves moins dynamiques et les aigus atténuées. C'est vraiment pauvre comme son.

- le flac c'est beaucoup mieux que le mp3. Il semble que c'est quand même moins bien que le cd en direct, mais c'est vraiment très difficile de faire la différence. Si différence il y a, elle vient uniquement de la moindre fidélité de la squeezebox, par rapport à la platine CD. Il faudrait passer au [transporter](http://www.slimdevices.com/pi_transporter.html) (ce serait même sans doute mieux que la platine vu les specs), mais c'est plus cher...

Du coup on était en train de ripper toute notre cdthèque, et on a eu les boules d'avoir numérisé environ pour 1000 mp3 de scuds. On a arrêté le mp3: pas envie d'avoir toute une musicothèque avec un mauvais encodage. Ca ne sert à rien d'avoir du bon son si l'information sonore est imparfaite à l'origine.

Ca prend plus de place, mais pour 300 cd ça donne environ 100Go, et vu le prix du disque dur : un disque de 100Go, coûte entre 85 et 100 euros. En gros un morceau fait entre 25 et 30Mo là où un mp3 en fait 5-8).

Exemple : mp3/flac, l'album de scratch massive, time : `82M mp3/Scratch_Massive/time/ 284M flac/Scratch_Massive/time/`

Le format flac fait entre 3 et 5 fois plus que du mp3 bien encodé (ici 3,46), donc si on dit 4 fois, pour 300 CD, ça fait économiser (en prenant la moyenne du prix du disque de 100Go) 70 euros, 140 avec un disque de sauvegarde pour être certain de ne pas perdre toute sa musique.

L'autre soucis (hormis la qualité du son), c'est l'archivage. Certains disques sont difficiles à ripper : eh oui, le cd qu'on dit super solide, qui sert même dans certains cas pour des sauvegardes, quand on le manipule beaucoup, qu'on le fait un peu tomber ou autre, ça se raye et ça saute. On a même eu un cd de "boards of canada" qui était cassé au centre, sûrement car l'attache centrale était trop robuste, et à force de sortir le CD, il s'est fendu. Et qui dit archive dit information fiable. Archiver de la musique en mp3 c'est comme archiver en photocopies noir et blanc des magazines papier glacé couleur.

La seule chose qui manque maintenant c'est une boutique de vente de musique en ligne avec un catalogue bien fourni en flac, mais c'est pour l'instant introuvable. Le seul truc que j'ai vu c'est [livedownloads.com](http://www.livedownloads.com/) mais c'est essentiellement du live, et ils n'ont pas grand chose. Si vous avez des adresses, ou si vous voulez monter une boite :) , n'hésitez pas.

Sinon, pour les dj amateurs, j'ai vu que numark faisait une sorte de tout en un qui lit un disque dur, et un cd, et qui lit le flac : [http://www.musik-service.de/numark-hdmix-prx395755616fr.aspx](http://www.musik-service.de/numark-hdmix-prx395755616fr.aspx) Ca a l'air assez sexy.

Voila, en résumé, si vous voulez vos transformer vos cd en virtuel, réfléchissez bien au format si vous aimez le bon son... le cas échéant, le mp3 c'est pour la ballade.
