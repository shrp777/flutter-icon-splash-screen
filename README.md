# Icon & Splash Screen

## Postionnement de l'icône sur le splash screen

Pour modifier le positionnement de l'image de splashscreen (par défaut "bottom".

- adapter la valeur de android:gravity ("center" à place de "bottom"):

`./android/app/main/res/drawable/lauch_background.xml`

`./android/app/main/res/drawable-21/lauch_background.xml`

```
    <item>
        <bitmap android:gravity="center" android:src="@drawable/branding"/>
    </item>
```

`flutter pub run flutter_native_splash:create`