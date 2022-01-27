# App Icon & Splash Screen

## Splash Screen

### Génération du splash screen

https://pub.dev/packages/flutter_native_splash

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
- Exécuter la commande suivante :

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


### Génération du App Icon

https://pub.dev/packages/flutter_launcher_icons

- Ajouter le package `flutter_launcher_icons` dans les `dev_dependencies` du fichier `./pubspec.yaml`
- Récupérer la dépendance en effectuant la commande `flutter pub get`
- En bas du fichier `./pubspec.yaml` ajouter :

```
flutter_icons:
  android: "launcher_icon"
  ios: true
  image_path: "assets/<nom-fichier-image>.png"
  adaptive_icon_background: "#42a5f5"
  adaptive_icon_foreground: "assets/<nom-fichier-image>.png"
```

- Exécuter la commande suivante :
`flutter pub run flutter_launcher_icons:main`

- Un problème lors de la génération de l'icône peut se produire. Il est dû à une mauvaise interprétation de la valeur des variables `flutter.minSdkVersion` et `targetSdkVersion` dans le fichier `./android/app/build.gradle`

- Remplacer le code par défaut :

```
defaultConfig {
    // TODO: Specify your own unique Application ID (https://developer.android.com/studio/build/application-id.html).
    applicationId "com.example.icon_and_splash_screen"
    minSdkVersion flutter.minSdkVersion
    targetSdkVersion flutter.targetSdkVersion
    versionCode flutterVersionCode.toInteger()
    versionName flutterVersionName
}
```

- par :

```
defaultConfig {
    // TODO: Specify your own unique Application ID (https://developer.android.com/studio/build/application-id.html).
    applicationId "com.example.icon_and_splash_screen"
    minSdkVersion 21
    targetSdkVersion 29
    versionCode flutterVersionCode.toInteger()
    versionName flutterVersionName
}
```

- une fois l'icône correctement généré, rétablir le fichier dans son état d'origine.

cf. https://stackoverflow.com/questions/70308823/why-am-i-getting-errors-while-adding-launcher-icon-in-flutter-project/70342129


---

__Alexandre Leroux__

- alex@sherpa.one
- https://sherpa.one
- sherpa#3890
- https://github.com/sherpa1/

_Enseignant vacataire à l'Université de Lorraine_

- IUT Nancy-Charlemagne (LP Ciasie)

- Institut des Sciences du Digital, Management & Cognition (Masters Sciences Cognitives)