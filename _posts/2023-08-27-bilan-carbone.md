---
layout: post
title:  Bilan Carbone de notre tour Inter-Rail
author:
  display_name: Bruno Thomas
tags:
- voyage
- inte-rail
---

Nous avons noté tout au long de notre périple les moyens de transports que nous avons pris, ainsi que les caractéristiques de ces transports au niveau de l'impact C0<msub>2</msub>.

Voici la synthèse :

| trajet                            | type         | km  | kgEqCO2/pers. | scénario |
| --------------------------------- | ------------ | --- | ------------- | -------- |
| Paris – Luxembourg                | train élec.  | 287 | 0,8           | réel     |
| Luxembourg - Koblenz – Hambourg   | train élec.  | 526 | 9,8           | réel     |
| Hambourg - Flensburg - Copenhague | train élec.  | 361 | 6,3           | réel     |
| Copenhague - Malmö - Stockholm    | train élec.  | 522 | 0,8           | réel     |
| Stockholm - Oslo                  | train élec.  | 523 | 1,1           | réel     |
| Stockholm - Oslo                  | bus          | 171 | 18,8          | réel     |
| Oslo - Bergen                     | bus          | 551 | 60,6          | réel     |
| Bergen – Stavanger                | bateau       | 160 | 19,2          | réel     |
| Stavanger - Kristiansand          | train élec.  | 230 | 0,6           | réel     |
| Kristiansand - Hirtshals          | bateau       | 132 | 56            | réel     |
| Hirshals - Aalborg                | train diesel | 67  | 8             | réel     |
| Aalborg - Fredericia              | train diesel | 165 | 20            | réel     |
| Fredericia - Hambourg             | train diesel | 232 | 28            | réel     |
| Hambourg – Paris                  | train élec.  | 575 | 6,3           | réel     |
| Total                             |              | 4502| 236,3         | réel     |

Résultat, nous avons parcouru **4502km** et produit **236kgEqCO<msub>2</msub>** pour nos déplacements.

![résumé en diagramme](/images/interrail-charts.png)

Quelques notes sur ces données.

Premièrement, elles ne comptent que le scope 2, la fabrication des équipements (trains, bateaux, bus), leur acheminement n'est pas pris en compte.

Niveau méthodologique nous avons utilisé :

- pour le train électrique la distance parcourue en km, multipliée par [le nombre de kW/h par passager par km](https://fr.wikipedia.org/wiki/Efficacit%C3%A9_%C3%A9nerg%C3%A9tique_dans_les_transports#Transport_ferroviaire), multipliée par l'impact carbone de chaque kWh. Pour cette dernière données nous avons pris les données sur [electricitymaps.com](https://app.electricitymaps.com) ;
- pour le bateau nous avons utilisé [futur.eco](https://futur.eco/) ;
- pour le bus nous avons utilisé les données de [impactco2.fr](https://impactco2.fr/transport/busthermique)

Nous avons subi [la tempête "Hans"](https://en.wikipedia.org/wiki/2022%E2%80%9323_European_windstorm_season) qui nous a obligé à prendre le bus pour arriver à Oslo. Hans nous a également privé de notre trajet Oslo-Finse et Finse-Bergen (un des gros intérêts de ce voyage). Nous avons du prendre un bus Oslo-Bergen. Si nous n'avions pas eu cette tempête, nous aurions eu un impact de **158kgEqCO<msub>2</msub>** c'est à dire que Hans nous a coûté 78kgEqCO<msub>2</msub> soit **33% de l'impact global**. C'est aussi ce que nous dit le GIEC : le dérèglement climatique va empirer l'impact environnemental de l'activité humaine (cf la climatisation, etc.).

Par ailleurs, les trains diesel nous ont aussi coûté beaucoup en CO<msub>2</msub>. Or nous avons vu lors de notre voyage que la [Nordjyske Jernbaner](https://nj.dk) est entrain d'électriser les lignes : nous avons vu les portiques pour caténaires qui sont en cours d'installation. Si nous avions eu des trains électriques au Danemark, nous aurions eu un impact de **108kgEqCO<msub>2</msub>**.

Enfin on peut même pousser plus loin. Nous avons observé que le mix énergétique notamment en Allemagne n'était pas bon car il y a pas mal de production d'électricité avec des centrales à charbon. Le nombre de gramme de CO<msub>2</msub> par kWh produit allait de 25g (pour la France et la Norvège) à presque 300g pour l'Allemagne, c'est à dire 12 fois plus ! Si on mettait un mix énergétique bas carbone (sans Hans, avec éléctrification des lignes danoises), alors l'impact du voyage était de **85kgEqCO<msub>2</msub>**.

Et si nous avions pris l'avion ? Alors dans ce scénario on n'aurait pas pu aller partout où nous sommes allés (du moins par le seul moyen aérien). Mais en supposant qu'on redescende directement de Bergen à Paris, alors l'impact aurait été de **882kgEqCO<msub>2</msub>** (source [furtur.eco](https://futur.eco/))

Vous pouvez retrouver tous ces scénarii et jouer avec [ici](https://github.com/bamthomas/lagrappe/blob/master/files/interrail-2023.ods).

Si vous avez des remarques, corrections, interrogations n'hésitez pas à [me contacter](https://blog.iroco.co/author/bruno/).
