# App Icon & Splash Screen

## Splash Screen

### Génération du splash screen

- Ajouter le package `flutter_native_splash` dans les `dev_dependencies` du fichier `./pubspec.yaml`
- Récupérer la dépendance en effectuant la commande `flutter pub get`
- En bas du fichier `./pubspec.yaml` ajouter :

```
flutter_native_splash:
  color: "#42a5f5"
  branding: assets/<nom-fichier-image>.png
  branding_mode: bottom
```

- Créer un dossier `assets` à la racine du projet
- Placer une image png dans le dossier `assets`.


`flutter pub run flutter_native_splash:create`

### Postionnement de l'icône sur le splash screen

En cas de problème de positionnement de l'image de splashscreen (par défaut :"bottom") :

adapter la valeur de android:gravity ("center" à place de "bottom")dans les 2 fichiers suivants :

`./android/app/main/res/drawable/lauch_background.xml`

`./android/app/main/res/drawable-21/lauch_background.xml`

```
    <item>
        <bitmap android:gravity="center" android:src="@drawable/branding"/>
    </item>
```

## App Icon

---

__Alexandre Leroux__

- alex@sherpa.one
- https://sherpa.one
- sherpa#3890
- https://github.com/sherpa1/

_Enseignant vacataire à l'Université de Lorraine_

- IUT Nancy-Charlemagne (LP Ciasie)

- Institut des Sciences du Digital, Management & Cognition (Masters Sciences Cognitives)