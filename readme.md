# Instalacja i konfiguracja środowiska React Native i Android

## Wymagania przed instalacją środowiska

1. Zainstalowany **Node** przynajmniej w wersji **LTS**. Można go pobrać ze strony: https://nodejs.org/en/download/
2. Zainstalowany i skonfigurowany **Git**. Można go pobrać ze strony: https://git-scm.com/
3. Zainstalowany dowolny edytor kodu np. **_Visual Studio Code_**
4. Zainstalowane **JDK** (_Java Developer Kit_) w wersji **11**
5. Dodana zmienna środowiskowa systemowa: **JAVA_HOME** (ścieżka do folderu z java 11.0.15)
6. Zainstalowane Expo CLI: [instrukcja](https://docs.expo.dev/get-started/installation/)

## Instalacja środowiska React Native

### 1. Instalacja i konfiguracja **Android Studio**

Zainstaluj **Android Developer Studio**. Można je pobrać ze strony: https://developer.android.com/studio . Podczas instalacj upewnij się, że masz zaznaczone checkboxy:

- Android SDK
- Android SDK Platform
- Android Virtual Device
- If you are not already using Hyper-V: Performance (Intel ® HAXM)

Następnie zainstaluj **Android SDK**. Domyślnie zainstalowana jest najnowsza wersja SDK, natomiast powinineś mieć zainstalową również **_SDK 12_**. Możesz je zainstalować z poziomu **SDK Manager** w Android Developer Studio.

Kliknij "More Actions" a następnie **SDK Manager**
![SDK Manager](https://reactnative.dev/assets/images/GettingStartedAndroidStudioWelcomeWindows-ce20d1230828a1a26e143e3a4145f1df.png)

Następnie wybierz zakładkę "SDK Platforms" z menedżera SDK, a następnie zaznacz pole obok "Show Package Details" w prawym dolnym rogu. Poszukaj i rozwiń wpis Android 12 (S), a następnie upewnij się, że następujące elementy są zaznaczone:

- Android SDK Platform 31
- Intel x86 Atom_64 System Image or Google APIs Intel x86 Atom System Image

Następnie wybierz zakładkę "**SDK Tools**" i zaznacz pole obok "Show Package Details" również tutaj. Poszukaj i rozwiń wpis Android SDK Build-Tools, a następnie upewnij się, że wybrano **31.0.0.**

Na koniec kliknij "Apply", aby pobrać i zainstalować Android SDK i powiązane narzędzia do budowania.

### 2. Skonfiguruj zmienną środowiskową **ANDROID_HOME**

Narzędzia React Native wymagają ustawienia pewnych zmiennych środowiskowych, aby móc budować aplikacje z natywnym kodem.

1. Wyszukaj w eksploratorze **_Edytuj zmienne środowiskowe dla konta_**
2. Kliknij Nowa... żeby utworzyć ANDROID_HOME, które wskazuje na ścieżkę do Twojego Android SDK

![ANDROID_HOME](data:image/png;base64,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)

Rzeczywistą lokalizację SDK można znaleźć w oknie dialogowym "Settings" pod Appearance & Behavior → System Settings → Android SDK.

Otwórz nowe okno Command, aby upewnić się, że nowa zmienna środowiskowa została załadowana przed przejściem do następnego kroku.

1. Otwórz **_powershell_**
2. Kopiuj i wklej `Get-ChildItem -Path Env:\` do powershell
3. Zweryfikuj czy ANDROID_HOME został dodany

### 3. Dodaj zmienne do **Path**

1. Wyszukaj w eksploratorze **_Edytuj zmienne środowiskowe dla konta_**
2. Wybierz zmienną Path.
3. Kliknij Edytuj.
4. Kliknij Nowy i dodaj do listy ścieżkę do platform-tools: `%LOCALAPPDATA%\Android\Sdk\platform-tools`
5. Dodaj do listy jeszcze 2 ścieżki wg wzoru: `%LOCALAPPDATA%\Android\Sdk\tools\bin`, `C:\users\nazwa_uzytkownika_windows\AppData\Local\Android\Sdk\emulator`,
6. W przypadku gdy chcesz mieć projekt napisany w Typescript po utworzeniu projektu podążaj za tą [instrukcją](https://docs.expo.dev/guides/typescript/)

### 4. Skonfiguruj urządzenie do wyświetlania aplikacji

- Jeżeli używasz emulatora podążaj za tą [instrukcją](https://developer.android.com/studio/run/managing-avds)
- Jeżeli używasz fizycznego urządzenia sprawdź tę [instrukcję](https://reactnative.dev/docs/running-on-device)

### 6. Stworzenie projektu Expo

1. Otwórz **git bash** w folderze, gdzie chcesz utworzyć nowy projekt.
2. Wpisz komendę `npx create-expo-app my-app`, gdzie zamiast my-app podasz swoją nazwę aplikacji
3. Podążaj za komunikatami
4. Gdy projekt poprawnie się utworzy wpisz komendę w tym samym oknie git bash `cd my-app`

[Oficjalna dokumentacja Expo](https://docs.expo.dev/get-started/create-a-new-app/)

### 7. Uruchom projekt

Upewnij się, że masz podłączony telefon lub uruchomiony emulator, a następnie w **git bash** otwartym w lokalizacji projektu wpisz komendę która startuje aplikację w trybie developerskim w Twoim projekcie. Dla projektu Expo będzie to komenda `yarn start` lub `expo start`

### 8. DODATKOWE

1. Diagnostyka

   pozwala sprawdzić które z kroków powyżej nie zostały zrealizowane poprawnie

   Dla vanilla React Native:

   [React Native doctor](https://reactnative.dev/blog/2019/11/18/react-native-doctor)

   Dla Expo React Native:

   [Expo doctor](https://www.npmjs.com/package/expo-doctor)

2. Zmiana portu na urządzeniu fizycznym lub emulatorze

   Czasami problematyczne może okazać się pobieranie danych z api które udostępnione jest na localhost. Wtedy konieczna jest zmiana portu na urządzeniu lub emulatorze.

   W tym celu:

   - Włącz **_powershell_**
   - Wpisz komendę `adb devices`
   - Następnie wpisz komendę `adb -s nazwa-urządzenia reverse tcp:8081 tcp:8081` żeby zmienić port. Oczywiście w przypadku innego portu niż 8081 wpisujemy ten przez nas porządany.

3. Debugger

   Istnieje kilka rozwiązań, ja polecam szczególnie:

   [react-devtools i debugowanie zdalnego kodu](https://reactnative.dev/docs/debugging)

   [Flipper](https://fbflipper.com/docs/features/react-native/)

   [Reactotron](https://github.com/infinitered/reactotron)

W razie problemów cały proces instalacji jest również opisany w [dokumentacji React Native](https://reactnative.dev/docs/environment-setup)
