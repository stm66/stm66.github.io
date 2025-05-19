
[Главная страница](https://stm66.github.io/)

## Разработка Android приложения на QT
### Установка Android SDK и Android NDK
Вопрос:
I have installed the command line tools of android, correctly configured all environment variables.

avdmanager create avd -n test -k "system-images;android-23;google_apis;x86"

It gives the following error:

error: package path is not valid. valid system image paths are:ository... null
I have already installed the SDK tool : sdkmanager "system-images;android-23;google_apis;x86"

And accepted the licenses sdkmanager --licenses

But still it's showing the same error.

By the way, I am using it for react-native

Ответ:

When I am creating a virtual device with this command:
In order to resolve your issue, you need to first run the cmd sdkmanager --list. A list will be populated with installed & available modules make sure: you have installed


1. Build-tools    - sdkmanager --install "build-tools;30.0.0"
2. Platform-tools - sdkmanager --install "platforms;android-30"
3. System image   - sdkmanager --install "system-images;android-30;google_apis;x86"
4. System image   - sdkmanager --install "system-images;android-30;google_apis;x86_64"
5. system image specific to Google Play Services  - sdkmanager --install "system-images;android-30;google_apis_playstore;x86_64"
6. NDK - sdkmanager --install "ndk;"

After installing or making sure the above are installed you can go ahead on creating avd.

5. Create an avd - avdmanager create avd -n TestAVD -k "system-images;android-30;google_apis;x86" --device "Pixel_4"
6. List created avds emulator -list -avds
7. Start Emulator or AVD emulator @TestAVD

2 ответ

I've resolved the issue by installing image first like

sdkmanager --install "system-images;android-23;google_apis;x86"

and then it is possible to create a emulator

3 ответ

It seem that avdmanager can not find the local image. Please try:

cd YOUR_SDK_ROOT_DIRECTORY

avdmanager create avd -n test -k "system-images;android-23;google_apis;x86"



[Сборка из командной строки](https://developer.android.com/build/building-cmdline?hl=ru)
[](https://developer.android.com/tools/sdkmanager?hl=ru)

## Установка gradle
скачиваем архив с сайта https://gradle.org/
https://docs.vultr.com/how-to-install-gradle-on-ubuntu-24-04
//sudo apt  install gradle неудачное решение очень старая версия

## Устанавливаем sdkmanager
в UBUNTU можно командой "sudo apt install google-android-cmdline-tools-1.0-installer"
либо скачать с сайта android сайта
https://developer.android.com/studio?hl=ru#command-tools
внизу страницы 

## Скачиваем java с сайта oracle Java 24
https://www.oracle.com/java/technologies/downloads/?er=221886

## установка Android-tools
>
>sdkmanager --install "platform-tools" 
// устанавливает в ту директорию где откуда запускается sdkmanager точнее в директорию где папка cmdline-tools

## скачиваем NDK
https://developer.android.com/ndk/downloads?hl=ru

## Документация по Android
[Документация по Android  на русском](http://easyandroid.ru/)
[Develop for Android](https://developer.android.com/develop)
[Официальная документация по Android](https://developer.android.com/)
[Начальная страница официальной документации](https://developer.android.com/get-started/overview?hl=ru)
[Обзор манифеста приложения](https://developer.android.com/guide/topics/manifest/manifest-intro?hl=ru#groovy)
[Настройте свою сборку](https://developer.android.com/build?hl=ru)
[Command-line tools ](https://developer.android.com/tools)
[Build your app from the command line](https://developer.android.com/build/building-cmdline)
[Управление файлами манифеста](https://developer.android.com/build/manage-manifests?hl=ru)
[Android ABIs](https://developer.android.com/ndk/guides/abis)
[Create WebP images](https://developer.android.com/studio/write/convert-webp)
[Building an Android App from the Command Line](https://www.hanshq.net/command-line-android.html)

## Gradle
[Kotlin DSL Reference for Gradle](https://docs.gradle.org/current/kotlin-dsl/index.html)
[Gradle User Manual](https://docs.gradle.org/current/userguide/userguide.html)
[]()
[]()

## Полезные ссылки
[Как компилировать apk без android studio](https://megavtogal.com/android/kak-kompilirovat-apk-bez-android-studio.html?ysclid=mal53bjd8o662507263&utm_referrer=https%3A%2F%2Fya.ru%2F)
[Running On Device android app](https://reactnative.dev/docs/running-on-device?package-manager=npm)
[Пишем и собираем приложения для Android в linux консоли](https://habr.com/ru/articles/335074/)
[Играем в APK-гольф. Уменьшение размера файлов Android APK на 99,9%](https://habr.com/ru/articles/339938/)
[Пишем, собираем и запускаем HelloWorld для Android в блокноте](https://habr.com/ru/articles/210584/)
[Пишем, собираем и запускаем HelloWorld для Android в блокноте. Java 8 и Android N](https://habr.com/ru/articles/309504/)
[Сборка Android приложения без Studio](https://habr.com/ru/articles/671086/)

[Главная страница](https://stm66.github.io/)
