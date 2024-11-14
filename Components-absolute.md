# Problème rencontré dans le projet Scooter

## Partie du design à reproduire

![design](<assets/design à reproduire.png>)

## 1. Structure HTML

```html
<div class="infos-info-image"> <!--contient toutes les images-->
    <img src="./assets/index/woman-using-smartphone.jpg" alt="woman-using-smartphone" srcset="" />
    <img src="./assets/index/grey-circle-right.svg" alt="grey-circle-right">
    <img class="infos-info-image-arrow" id="arrow-smartphone"
        src="./assets/index/woman-using-smartphone-arrow.svg" alt="arrow-smartphone">
</div>
```

## 2. Etapes

### 2.1. Afficher les images en colonnes

```scss
&-image {
    display: flex;
    gap: 64px;
    ...
}
````
![alt text](<assets/design en flex.PNG>)

### 2.2. Mettre la flèche en position absolue

```scss
&-image {
    display: flex;
    gap: 64px;
    position: relative;
    &-arrow {
        position: absolute;  
    }
}
````
![fleche-absolute](<assets/design fleche absolue.PNG>)

### 2.3. Controler la position de la flèche

| Propriété | Description                                                                                     |
|-----------|-------------------------------------------------------------------------------------------------|
| top       | Définit la distance entre le bord supérieur de l'élément et le bord supérieur de son conteneur positionné. |
| right     | Définit la distance entre le bord droit de l'élément et le bord droit de son conteneur positionné.        |
| bottom    | Définit la distance entre le bord inférieur de l'élément et le bord inférieur de son conteneur positionné. |
| left      | Définit la distance entre le bord gauche de l'élément et le bord gauche de son conteneur positionné.       |


```scss
&-image {
    display: flex;
    gap: 64px;
    position: relative;

    &-arrow {
        position: absolute;  
    }
    #arrow-smartphone {
        bottom: 0px;
    }
    ...
}
````
![design final](<assets/design controle.png>)