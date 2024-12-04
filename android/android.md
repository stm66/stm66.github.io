
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

1. Build-tools sdkmanager build-tools 30
2. Platform-tools sdkmanager platform 30
3. System image sdkmanager "system-images;android-30;google_apis;x86"
4. System image sdkmanager "system-images;android-30;google_apis;x86_64"

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


[Главная страница](https://stm66.github.io/)