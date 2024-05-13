# Bébite Micro:Bit

## @showdialog
Ce tutoriel a été adapté et traduit en français par: David Cormier
## Étape 1 - La bébite dort
Cette bébite Micro:bit est très endormie. En fait, elle dort presque toujours.

► Saisissez le bloc ``||basic:toujours||``, et glissez-le dans la boîte à outil (l'espace boîte à outils devient rouge et l'îcone poubelle apparaît) car vous n'aurez pas besoin de ce bloc.

► Dans la catégorie ``||basic:Base||``, recherchez ``||basic:montrer l'icône [ ]||`` et insérez-le dans votre conteneur ``||basic:au démarrage||``. Réglez-le pour qu'il affiche le visage -_- endormi.

💡 Dans les options du menu déroulant Afficher l'icône, vous pouvez survoler pour voir comment s'appelle chaque design !

``` blocks
basic.showIcon(IconNames.Asleep)
```
## Étape 2 - La bébite est contente
► Depuis la catégorie ``||input:Entrée||``, recherchez le conteneur ``||input:sur le logo [appuyé]||`` et faites-le glisser dans votre espace de travail.

► Allez dans ``||basic:Base|`` et récupérez le bloc ``||basic:montrer l'icône [ ]||``. Insérez-le dans votre conteneur vide ``||input:sur le logo [appuyé]||``. Réglez l'icône du visage de votre bébite sur heureux :).
``` blocks
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    basic.showIcon(IconNames.Happy)
})
```
## Étape 3 - Son de chatouillement

► Dans la catégorie ``||son:Musique||``, obtenez ``||son:jouer le son [gloussement] jusqu'à la fin||`` et ajoutez-le au bas de votre conteneur ``||input:sur le logo [appuyé]||``.
``` blocks
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    basic.showIcon(IconNames.Happy)
    soundExpression.giggle.playUntilDone()
})
```
## Étape 4 - La bébite est triste

Chaque fois que votre bébite est secoué, elle devient tristes 🙁

► Depuis ``||input:Entrée||``, recherchez ``||input:lorsque [secouer]||`` et faites-le glisser dans votre espace de travail.

► Dans la catégorie ``||basic:Base||``, saisissez ``||basic:montrer l'icône [ ]||`` et insérez-la dans votre nouveau conteneur ``||input:lorsque [secouer]||`` . Réglez l'icône (le visage de votre bébite) sur triste :(
``` blocks
input.onGesture(Gesture.Shake, function () {
    basic.showIcon(IconNames.Sad)
})
```
## Étape 5 - son de tristesse

► Dans la catégorie ``||son:Musique||``, recherchez le bloc ``||son:jouer le son [gloussement] jusqu'à la fin||`` et ajoutez-le au bas de votre conteneur ``||input:lorsque [secouer]||``.

► Cliquez sur la liste déroulante et réglez-la pour que Cyrus joue un son ``||son:triste||``  jusqu'à la fin.
``` blocks
input.onGesture(Gesture.Shake, function () {
    basic.showIcon(IconNames.Sad)
    soundExpression.sad.playUntilDone()
})
```
## Étape 6 - Le visage par défaut de votre bébite. partie 1

Assurons-nous que votre bébite se rendormira toujours après avoir été secoué ou chatouillé.

► Cliquez avec le bouton droit sur le bloc ``||basic:montrer l'icône [-_-]||`` dans votre espace de travail (à l'intérieur du conteneur ``||basic:au démarrage||``) et choisissez Dupliquer.

► Insérez votre bloc copié tout en bas de votre conteneur ``||input:lorsque [secouer]||``.
``` blocks
input.onGesture(Gesture.Shake, function () {
    basic.showIcon(IconNames.Sad)
    soundExpression.sad.playUntilDone()
    basic.showIcon(IconNames.Asleep)
})
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    basic.showIcon(IconNames.Happy)
    soundExpression.giggle.playUntilDone()
})
basic.showIcon(IconNames.Asleep)
```
## Étape 7 - Le visage par défaut de votre bébite. partie 2

► Dupliquez à nouveau le bloc ``||basic:Afficher l'icône [-_-]||`` et cette fois-ci, insérez-le tout en bas de votre conteneur ``||input:sur le logo [appuyé]||``.
``` blocks
input.onGesture(Gesture.Shake, function () {
    basic.showIcon(IconNames.Sad)
    soundExpression.sad.playUntilDone()
    basic.showIcon(IconNames.Asleep)
})
input.onLogoEvent(TouchButtonEvent.Pressed, function () {
    basic.showIcon(IconNames.Happy)
    soundExpression.giggle.playUntilDone()
    basic.showIcon(IconNames.Asleep)
})
basic.showIcon(IconNames.Asleep)
```
## Étape 8 - Test dans le simulateur
assurez-vous que le simulateur est visible et que vos haut-parleurs sont allumés 🔊

Jouez avec votre bébite pour voir comment elle réagit 🐹
Cliquez sur le bouton SHAKE pour secouer votre bébite.
Touchez le logo doré en haut pour chatouiller votre bébite.

Si vous possédez un nouveau micro:bit (celui avec le logo doré brillant en haut), téléchargez ce code et essayez-le !

## Félicitaions
Félicitaions, votre bébite Micro:Bit à des émotions!