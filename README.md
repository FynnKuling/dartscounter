# Dartcounter APK

Een kleine Android-app die `dartcounter.html` (staat in `app/src/main/assets/index.html`) schermvullend in een WebView toont. Werkt volledig offline en heeft geen internetrechten nodig. Het verschijnt in het Android TV-startscherm en op telefoons.

## Optie A: bouwen met GitHub (geen Android Studio nodig)

1. Maak een gratis account op github.com en een nieuwe (privé) repository.
2. Upload alle bestanden uit deze map, inclusief de verborgen map `.github`.
3. Ga in de repository naar het tabblad **Actions**, kies **Build APK** en klik op **Run workflow**.
4. Na ongeveer 3 tot 5 minuten staat onder de run een download `dartcounter-apk`. Pak de zip uit: daarin zit `app-debug.apk`.

## Optie B: bouwen met Android Studio

1. Installeer Android Studio en kies **Open** op deze map.
2. Laat de Gradle-sync afronden (hij haalt zelf de benodigde onderdelen op).
3. Kies **Build > Build App Bundle(s) / APK(s) > Build APK(s)**.
4. De APK staat in `app/build/outputs/apk/debug/app-debug.apk`.

## Installeren op de stick

```
adb connect IP-VAN-DE-STICK:5555
adb install -r app-debug.apk
```

Als `adb devices` je stick al toont, kun je `adb connect` overslaan.

De app staat daarna in het appoverzicht van de stick. De stick moet "Apps uit onbekende bronnen" toestaan als je de APK op een andere manier installeert dan via adb.

## Dartcounter aanpassen

Wijzig `app/src/main/assets/index.html` en bouw opnieuw. Verhoog bij een nieuwe versie `versionCode` in `app/build.gradle`.
