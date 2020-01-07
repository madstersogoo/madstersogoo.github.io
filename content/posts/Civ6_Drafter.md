---
title: "Civ6_Drafter"
date: 2020-01-05T18:11:03+01:00
draft: False
---

## Présentation du Projets, Comment l'utiliser et modifier son code.
<!--more-->

Civ6_Drafter est un programme écrit en pyhton qui a pour but de faciliter la phase de draft.

### Civilization possible.

pour rajouter des Civilizations pour les extensions il faut les rajouter a la liste_civ.

{{< highlight python >}}
liste_civ = ["American","Arabian","Aztec","Brazilian","Chinese","Egyptian","English","French","German","Greek","Indian","Japanese","Kongolese","Norwegian","Roman","Russian","Scythian","Spanish","Sumerian"]
{{< /highlight >}}

Il faut ensuite rajouter un module de ban qui correspond a la civilization

{{< highlight python >}}
def addban1(buttonframe):
    ban.append("American")
{{< /highlight >}}

Pour terminer if faut rajouter le bouton qui correspond ainsi que définir sa position dans la grid.

je conseil de les mettres a la suite par ligne de 9 boutons.

{{< highlight python >}}
    button1=Button(buttonframe,text="American", command=addban1)
    button1.grid(row=0,column=0)
{{< /highlight >}}

### Présentation du code.

Voici le code qui permet de désigner de manière aléatoire les Civs dans les deux équipes.

{{< highlight python >}}
        for i in range(0,7):
            value=rd.randint(0,len(liste_civ)-1)
            equipe1.append(liste_civ[value])
            liste_civ.remove(liste_civ[value])
{{< /highlight >}}

Voici le code qui remove les civilizations qui vont être ban.

{{< highlight python >}}
        for i in ban:
            liste_civ.remove(i)
{{< /highlight >}}

## TODO

Pour la suite de se projet je compte rajouter un support pour **Rise and Fall** ainsi que **Gathering storm** avec un menu qui,
permettra de selectionner les extensions majeurs du jeu.

### TODO moins important

- changer les boutons pour qu'ils soit plus propre et montre une selection et pouvoir remove un ban.

- montrer les civs sélectionner.

- faire un code beaucoup plus propre.

- le publish sous forme .exe pour avoir une application native windows et linux.

