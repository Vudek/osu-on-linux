# osu-on-linux
osu! low latency guide 2025 version 

# Язык: [RU](https://github.com/Vudek/osu-on-linux/blob/main/README_RU.md) | [EN](https://github.com/Vudek/osu-on-linux/blob/main/README.md) 

# Поскольку мое предыдущее руководство было кем-то нюкнуто, я решил перенести его на GitHub

Штош, это руководство по osu! с низкой задержкой, со стабильным работающим wine, drag-n-drop и другими вещами.
![Arch Linux](https://vudek.s-ul.eu/3gOtpcXN)

Сначала - [скачайте ISO-файл Arch Linux с официального сайта](https://archlinux.org/download/).

Скачайте [Ventoy](https://sourceforge.net/projects/ventoy/files/v1.1.07/ventoy-1.1.07-windows.zip/download) и распакуйте его в любую директорию, мы создадим USB-мультиинструмент для многих дистрибутивов.

Откройте **Ventoy2Disk**, выберите ваш USB-накопитель, нажмите **Install**, подтвердите стирание USB два раза, и после установки ваш накопитель разделится на **VENTOY** и **VENTOYEFI**, скопируйте ISO Arch Linux на накопитель с именем **VENTOY**.
# Скриншоты:
![](https://vudek.s-ul.eu/DarJQ8Ar)

![](https://vudek.s-ul.eu/re0gc5FJ)

![](https://vudek.s-ul.eu/Lyd0u1tp)

![](https://vudek.s-ul.eu/HCHi80g3)

После этих шагов перезагрузитесь в **BIOS**, выберите ваш накопитель в **Boot**, и вы загрузитесь в графический интерфейс Ventoy.
![](https://vudek.s-ul.eu/Jy9WWfeo)

Важное замечание: после выбора вашего ISO Arch Linux в Ventoy, выберите `Boot in grub2 mode` для успешной установки Arch Linux.
![](https://vudek.s-ul.eu/IkIYfIwM)

Давайте установим Arch на ваш ПК:

1. После загрузки из Ventoy вы увидите один из этих экранов загрузки Arch Linux:
   - если ваш BIOS в legacy-режиме:
     
     ![](https://vudek.s-ul.eu/G5wEsEPG)
     
   - если ваш BIOS в UEFI-режиме:
     
     ![](https://vudek.s-ul.eu/wrPKhSdP)
   Выберите `Arch Linux install medium` и подождите, пока загрузится установочный носитель в терминал.

2. Итак, мы загрузились в терминал:
   
   ![](https://vudek.s-ul.eu/hPtc7p7w)
   
4. Введите `archinstall` и нажмите **Enter**, вы войдете в псевдо-графический интерфейс установки:
   
   ![](https://vudek.s-ul.eu/qaUvSJxD)
   
6. Выберите `Mirrors and repositories`, нажмите **Enter**, и вы войдете в это подменю:
   
   ![](https://vudek.s-ul.eu/502pegGo)

   Нажмите **Enter** снова, и вы войдете в меню, где можете выбрать регион зеркала Arch Linux. Для быстрого поиска нажмите `/` и введите вашу страну, в моем случае это `/Belarus`:
   
   ![](https://vudek.s-ul.eu/dCb5wmmK)

   Нажмите **Enter**, и вы вернетесь в предыдущее меню, выберите `Optional repositories` и нажмите **Enter**:
   
   ![](https://vudek.s-ul.eu/zTT8vJ6c)

   Выберите `multilib`, нажмите **Enter**, и после этих шагов выберите **Back** и нажмите **Enter**, вы вернетесь в главное меню установки:
   
   ![](https://vudek.s-ul.eu/VcqZHE7Q)

7. Выберите `Disk configuration` и нажмите **Enter**:
   
   ![](https://vudek.s-ul.eu/KoClO7ji)

   Нажмите **Enter**:
   
   ![](https://vudek.s-ul.eu/bINWpLyf)

   ### ПРЕДУПРЕЖДЕНИЕ, МОЕ РУКОВОДСТВО ДЛЯ УСТАНОВКИ НА ОТДЕЛЬНЫЙ ДИСК, НЕ ИСПОЛЬЗУЙТЕ УСТАНОВКУ НА ТОМ ЖЕ ДИСКЕ, ГДЕ У ВАС УСТАНОВЛЕНА WINDOWS

   Выберите `Use a best-effort default partition layout` и выберите ваш диск:

   ![](https://vudek.s-ul.eu/edO7zAd8)

   Выберите `ext4`:
   
   ![](https://vudek.s-ul.eu/5e2BMYQQ)

   Диск был автоматически разбит:
   
   ![](https://vudek.s-ul.eu/UcU4i24T)

   Если ваш диск от 64 ГБ до 256 ГБ, вы можете пропустить следующие шаги и перейти к пункту 6.

   # Если вы хотите вручную изменить размер разделов, выполните следующие шаги:
   
   Выберите `Partitioning` снова и перейдите к `Manual Partitioning`:
   
   ![](https://vudek.s-ul.eu/ISVikhfK)

   Выберите ваш диск снова:

   ![](https://vudek.s-ul.eu/F1rbo5Yd)

   И вы увидите это меню:

   ![](https://vudek.s-ul.eu/SZE5KvwD)

   Выберите второй раздел с меткой `/`, нажмите Enter, и вы войдете в это меню:

   ![](https://vudek.s-ul.eu/LX0CkWMy)

   Выберите `Delete partition` и нажмите **Enter**, теперь у вас есть `free` раздел:

   ![](https://vudek.s-ul.eu/4pO26fPB)

   Выберите ваш `free` раздел, нажмите **Enter**, и вы войдете в меню, где можете выбрать размер вашего нового раздела:

   ![](https://vudek.s-ul.eu/egJ2A592)

   В моем случае я сделаю корневой раздел `/` размером 20 GiB.

   После ввода размера нажмите Enter и выберите файловую систему `ext4`:

   ![](https://vudek.s-ul.eu/CPcmG1Ey)

   Нажмите **Enter**, вы войдете в меню `Mountpoint` и введите `/` для вашего первого раздела:

   ![](https://vudek.s-ul.eu/jnimdjZ9)

   Нажмите **Enter**, и вы вернетесь в предыдущее меню с разметкой диска. Запомните `Size` вашего свободного раздела:

   ![](https://vudek.s-ul.eu/KZq0WUIJ)

   Выберите ваш `free` раздел и нажмите **Enter**:

   ![](https://vudek.s-ul.eu/De8PQchb)

   В этом случае размер моего свободного раздела 19 GiB, в вашем случае - введите размер вашего свободного раздела из предыдущего шага:

   ![](https://vudek.s-ul.eu/De8PQchb)

   Выберите файловую систему `ext4`:

   ![](https://vudek.s-ul.eu/iOLjBdDt)

   Выберите точку монтирования `/home`:

   ![](https://vudek.s-ul.eu/Toa1c977)

   И нажмите **Enter**, и вы вернетесь в `Disk configuration`:

   ![](https://vudek.s-ul.eu/PYNgs9dT)

   Итак, после выполнения этих шагов, как вы видите, у вас есть разделы `/boot`, `/` и `/home`!
   Выберите `Confirm and exit` и нажмите **Enter**:

   ![](https://vudek.s-ul.eu/oT6qh4qY)

   Выберите `Back`, и вы вернетесь в главное меню установки:

   ![](https://vudek.s-ul.eu/8yea7R8Y)

8. Перейдите к `Bootloader`:

   ![](https://vudek.s-ul.eu/9FfnyLbi)

   В моем случае там `grub` как загрузчик по умолчанию (из-за legacy BIOS в VM)
   В вашем случае там будет `systemd-boot` по умолчанию (для UEFI BIOS) или тот же `grub` по умолчанию (для legacy BIOS).

9. Перейдите к `hostname`:

   ![](https://vudek.s-ul.eu/e9Le37VX)

   Нажмите Enter, и там вы можете ввести что угодно (ограничение 1-63 буквы):

   ![](https://vudek.s-ul.eu/zGqqRMo2)

   После этого ваш `hostname` появится в главном меню установки вот так:

   ![](https://vudek.s-ul.eu/GtFqHl2V)

10. Перейдите к `Authentification` и нажмите **Enter**:

   ![](https://vudek.s-ul.eu/UZ5r8NNW)

   Здесь выберите `Root password`, нажмите **Enter**, и вы войдете в меню, где можете ввести пароль root:

   ![](https://vudek.s-ul.eu/jlRAam5b)

   После ввода пароля для root нажмите **Enter** и введите пароль снова для подтверждения:

   ![](https://vudek.s-ul.eu/BSz6wHci)

   Нажмите Enter, вы вернетесь в меню `Authentification`, выберите `User account`:
   
   ![](https://vudek.s-ul.eu/esdajcmh)

   Нажмите **Enter**, и вы войдете в это меню:

   ![](https://vudek.s-ul.eu/vEtZmWaS)

   Выберите `Add a user` и нажмите **Enter**:

   ![](https://vudek.s-ul.eu/XviyuFGw)

   Введите предпочитаемое имя пользователя (вы не можете просто ввести **admin**, это запрещено):

   ![](https://vudek.s-ul.eu/XviyuFGw)

   ![](https://vudek.s-ul.eu/V5QPJBVP)

   На следующем шаге вы увидите то же меню, что и в предыдущем шаге, просто введите пароль для учетной записи пользователя дважды:

   ![](https://vudek.s-ul.eu/eKws0Kgp)

   ![](https://vudek.s-ul.eu/nwEFZaQE)

   После этого вам будет задан вопрос "Should %user% be a superuser (sudo)". Выберите yes и нажмите **Enter**:

   ![](https://vudek.s-ul.eu/46Ih9Dbr)

   ![](https://vudek.s-ul.eu/7EKkIGKa)

   Подтвердите изменения. Выберите `Confirm and exit` и нажмите **Enter**:

   ![](https://vudek.s-ul.eu/psXqAifU)

   Выберите `Back`, и вы вернетесь в главное меню установки:

   ![](https://vudek.s-ul.eu/t7cRFoH3)

   Если все правильно, и ваш root имеет пароль, и у вас есть учетная запись пользователя с паролем и sudo, перейдите к следующему шагу.

11. Перейдите к разделу `Profile` и нажмите **Enter**:

   ![](https://vudek.s-ul.eu/X0pBjlEI)

   Выберите `Type` и нажмите **Enter**:

   ![](https://vudek.s-ul.eu/V5uU47cK)

   Выберите `Desktop` и нажмите **Enter**:

   ![](https://vudek.s-ul.eu/jDT7Ei0e)

   Вы войдете в меню, где можете выбрать среду рабочего стола. Для лучшей задержки выберите i3-wm и нажмите **Enter**:

   ![](https://vudek.s-ul.eu/zeyPgvdf)

   Вы вернетесь в меню `Profile`, выберите `Graphics driver` и нажмите **Enter**:

   ![](https://vudek.s-ul.eu/xlDKHUXe)

   Здесь вы можете выбрать предпочитаемый драйвер графики в зависимости от вашего GPU.

   Шпаргалка:

   - **AMD / ATI (open-source)** — Для любого AMD GPU
   - **All open-source** — Этот выбор установит все open-source из этого списка.
   - **Intel (open-source)** — Для любого Intel GPU (встроенного или Arc).
   - **Nvidia (open kernel module for newer GPU's, Turing+)** — Выберите, если у вас современный Nvidia GPU, начиная с серии 20xx.
   - **Nvidia (open-source nouveau driver)** — НИКОГДА НЕ ВЫБИРАЙТЕ ЭТО LMAO.
   - **Nvidia (proprietary)** — Выберите, если у вас несовременный Nvidia GPU (до серии RTX).
   - **VirtualBox (open-source)** — Выберите для установки VirtualBox.

   После выбора предпочитаемого драйвера GPU нажмите **Enter** и вернитесь в главное меню:

   ![](https://vudek.s-ul.eu/SWZowNH7)

12. Перейдите к `Applications` и нажмите **Enter**:
   
   ![](https://vudek.s-ul.eu/qC7P5QmP)

   Выберите `Audio` и нажмите **Enter**:

   ![](https://vudek.s-ul.eu/DbCDZSd9)

   В этом меню выберите `pipewire` и нажмите **Enter**:

   ![](https://vudek.s-ul.eu/8jlmHzI7)

   Выберите `Back` и вернитесь в главное меню, нажав **Enter**:

   ![](https://vudek.s-ul.eu/rr2ogUHt)

13. Перейдите к `Kernels` и нажмите **Enter**:
    
    ![](https://vudek.s-ul.eu/85zkonsN)

    Нажав пробел, удалите `x` у `linux`, выберите `linux-zen`, нажмите пробел снова и нажмите **Enter**:

    ![](https://vudek.s-ul.eu/8cAKQxVy)

    ![](https://vudek.s-ul.eu/bm0l2CBH)

14. Перейдите к `Network configuration` и нажмите **Enter**:

    ![](https://vudek.s-ul.eu/NeLf6hxX)

    Выберите `Copy ISO network configuration to installation` и нажмите **Enter**:

    ![](https://vudek.s-ul.eu/AwFoPNb4)

15. Перейдите к `Additional packages` и нажмите **Enter**:

    ![](https://vudek.s-ul.eu/ctZvGaJE)

    Для легкого выбора пакетов выполните эти шаги:
    - нажмите `/`;
    - введите имя пакета;
    - с помощью стрелок на клавиатуре выберите пакет;
    - нажмите **Esc**;
    - нажмите **Spacebar**.

    Демонстрация этого алгоритма:

    ![](https://vudek.s-ul.eu/yTbTuWQ4)

    Итак, вы должны выбрать эти пакеты:

    `git chromium winetricks lib32-gnutls lib32-libxcomposite kitty rofi nemo flameshot`

    Если у вас Nvidia GPU, дополнительно выберите этот пакет: `lib32-nvidia-utils`.

    ![](https://vudek.s-ul.eu/dUgvjOxj)

    После выбора всех нужных пакетов нажмите **Enter**, все должно быть как это:

    ![](https://vudek.s-ul.eu/TPDK3UYi)

16. Перейдите к `Timezone` и нажмите **Enter**:

    ![](https://vudek.s-ul.eu/SKVECPHx)

    Здесь выберите ваш часовой пояс, поискав через нажатие `/` (в моем случае это `/Minsk`:

    ![](https://vudek.s-ul.eu/p5NyW2Zb)

    Нажмите **Enter** и вернитесь в главное меню:

    ![](https://vudek.s-ul.eu/XTJw85OJ)

17. Перейдите к `Install` и нажмите **Enter**:

    ![](https://vudek.s-ul.eu/PcK0t7fP)

    ![](https://vudek.s-ul.eu/dPeZLvk3)

    Вам будет задан вопрос "The specified configuration will be applied. Would you like to continue?". Выберите `Yes` и нажмите **Enter**:

    ![](https://vudek.s-ul.eu/4drvTzi9)

    ![](https://vudek.s-ul.eu/2rzHyRgC)

    Наконец, начнется ваша установка. На этом этапе вы можете расслабиться или пойти заварить чай, поскольку процесс зависит от скорости вашего интернет-соединения. Пока вы ждете, подпишитесь на мои соцсети🥺:
      - [Telegram](https://t.me/vudekosu)
      - [X (Twitter)](https://twitter.com/vudek_)
      - [YouTube](https://youtube.com/c/vudek)
      - [Twitch](https://twitch.tv/vudek_)
    
    После завершения установки вы увидите это меню:

    ![](https://vudek.s-ul.eu/WBCh8eL7)

    Выберите `Reboot system` и нажмите **Enter**. Во время перезагрузки извлеките USB-накопитель и перейдите в BIOS, чтобы выбрать загрузку в Arch Linux.

# НАКОНЕЦ - ARCH LINUX ЗАГРУЖЕН
  После загрузки Arch вы увидите этот экран входа:

  ![](https://vudek.s-ul.eu/DFy8EJau)

  Введите ваш пароль и нажмите enter, вы войдете в среду рабочего стола i3-wm.

  При первом входе i3-wm спросит о генерации базовой конфигурации, нажмите Enter дважды.

  ![](https://vudek.s-ul.eu/9fE7eW7j)

  ![](https://vudek.s-ul.eu/4fPehK4T)

  После этого базовая конфигурация i3-wm будет записана в `~/.config/i3/config`. Теперь вы можете использовать привязки.

  Нажмите **Win+D**, введите `kitty` и нажмите **Enter**. 
  Нажмите **Win+2**, чтобы перейти на рабочий стол 2.
  Нажмите **Win+D** снова, введите `chromium` и нажмите **Enter**:

  ![](https://vudek.s-ul.eu/rJW33xBm)

  Откройте [эту веб-страницу](https://github.com/Vudek/osu-on-linux) в браузере и скопируйте это:

  ```
  wget http://puu.sh/KClvp/49aa8dee55 -O ~/.config/i3/config
  ```

  Вернитесь на 1-й рабочий стол, нажав Win+1, и вставьте скопированную строку в терминал kitty, нажав **Shift+Insert** или щелкнув средней кнопкой мыши, и нажмите **Enter**.
  Введите:

  ```
  i3 reload
  ```

  и нажмите **Enter**, теперь у вас есть моя расширенная конфигурация i3-wm с этими привязками:
  - Открыть меню запуска по **Win+R**
  - Открыть legacy-меню запуска по **Win+Enter**
  - Переключать рабочие столы по **Win+1**, **Win+2**, ... **Win+0**
  - Переключать активные рабочие столы по **Ctrl+Win+⬅** или **Ctrl+Win+⮕**
  - Переместить активное окно на другой рабочий стол по **Win+Shift+1**, **Win+Shift+2**, ... **Win+Shift+0**
  - Закрыть активное окно по **Win+Shift+Q**
  - 🩼 Переключать рабочие столы в стиле alt-tab по **Win+Tab**
  - Открыть терминал по **Win+Enter**

  Теперь перейдите в терминал и введите:

  ```
  sudo pacman -S pipewire-media-session
  ```

  После этого нажмите **Enter**, и вам будет предложено ввести пароль.

  ПРЕДУПРЕЖДЕНИЕ, ПАРОЛЬ НЕ ОТОБРАЖАЕТСЯ В ТЕРМИНАЛЕ!

  Введите Y и нажмите Enter для `removing wireplumber`. 
  Введите Y и нажмите Enter снова, чтобы установить `pipewire-media-session`.

  ![](https://vudek.s-ul.eu/DfPgb6tR)

  После этого шага нам нужно понизить wine-1x до wine-9.22-1, так что скопируйте это в терминал:

  ```
  mkdir -p ~/Downloads && cd ~/Downloads && wget https://github.com/Vudek/wine-9.22-1-x86_64/releases/download/wine-9.22-1-x86_64.pkg.tar.zst/wine-9.22-1-x86_64.pkg.tar.zst && sudo pacman -U wine-9.22-1-x86_64.pkg.tar.zst && cd
  ```

  И нажмите **Enter**. Вам будет предложено понизить пакет. Введите Y и нажмите Enter.

  ![](https://vudek.s-ul.eu/Rl5xVht4)

  Wine полностью понижен до 9.22-1. Теперь мы можем создать wineprefix и установить osu!

# Установка osu!

  Перед началом скопируйте это в терминал и нажмите **Enter**, чтобы убедиться, что все пакеты установлены:

  ```
  sudo pacman -S giflib lib32-giflib libpng lib32-libpng libldap lib32-libldap gnutls lib32-gnutls \
mpg123 lib32-mpg123 openal lib32-openal v4l-utils lib32-v4l-utils libpulse lib32-libpulse libgpg-error \
lib32-libgpg-error alsa-plugins lib32-alsa-plugins alsa-lib lib32-alsa-lib libjpeg-turbo lib32-libjpeg-turbo \
sqlite lib32-sqlite libxcomposite lib32-libxcomposite libxinerama lib32-libgcrypt libgcrypt lib32-libxinerama \
ncurses lib32-ncurses opencl-icd-loader lib32-opencl-icd-loader libxslt lib32-libxslt libva lib32-libva gtk3 \
lib32-gtk3 gst-plugins-base-libs lib32-gst-plugins-base-libs vulkan-icd-loader lib32-vulkan-icd-loader
  ```

  После этого шага давайте создадим wineprefix для osu!. Скопируйте это в терминал:

  ```
  WINEARCH=win32 WINEPREFIX=~/.wineosu winetricks dotnet45 cjkfonts gdiplus
  ```

  Нажмите Enter. Когда появится окно с установкой **Mono**, нажмите **Cancel**.

  Следующая установка будет в стиле Windows для этого шага. Согласитесь с установкой галочкой, нажмите next, подождите, и после установки dotnet нажмите **Restart Later**.

  Итак, после завершения всего давайте создадим папку osu!, скопируйте это в терминал и нажмите **Enter**:

  ```
  mkdir ~/osu/
  ```

  Скачайте osu!:

  ```
  wget --output-document ~/osu/osu\!.exe https://m1.ppy.sh/r/osu\!install.exe
  ```

  Создайте папку bin:

  ```
  mkdir -p ~/.local/bin
  ```

  Создайте скрипт запуска:

  ```
  nano ~/.local/bin/osu
  ```

  Скопируйте-вставьте это в ваш скрипт запуска:

  ```
  #!/usr/bin/env bash
  #export PATH="/opt/wine-osu/bin:$PATH" #custom WINE ArchLinux
  export PATH="$HOME/wine-osu/bin:$PATH" #custom WINE new

  export WINEARCH=win32
  export WINEPREFIX="$HOME/.wineosu"
  export WINEFSYNC=1
  export WINE_DISABLE_VK_CHILD_WINDOW_RENDERING_HACK=1

  export STAGING_AUDIO_DURATION=13333
  export STAGING_AUDIO_PERIOD=13333

  export vblank_mode=0 #For AMD, Intel and others

  #export __GL_SYNC_TO_VBLANK=0 #For NVIDIA 
  export __GL_MaxFramesAllowed=0
  export __GL_THREADED_OPTIMIZATIONS=1 


  cd ~/osu
  #wine --version
  wine "osu!.exe"
  ```

  Сохраните, нажав Ctrl+O, закройте Ctrl+X.

  Создайте скрипт убийства:

  ```
  nano ~/.local/bin/osukill
  ```

  Скопируйте-вставьте это в ваш скрипт убийства:

  ```
  #!/usr/bin/env bash
  #export PATH="/opt/wine-osu/bin:$PATH" #custom WINE ArchLinux
  export PATH="$HOME/wine-osu/bin:$PATH" #custom WINE new

  export WINEARCH=win32
  export WINEPREFIX="$HOME/.wineosu"

  wineserver -k
  ```

  Сохраните, нажав Ctrl+O, закройте Ctrl+X.

  Скопируйте-вставьте в терминал:

  ```
  chmod +x ~/.local/bin/osu && chmod +x ~/.local/bin/osukill
  ```

  Теперь ваш скрипт и скрипт убийства исполняемы!

  > Для пользователей Nvidia - раскомментируйте\
  > ```export __GL_SYNC_TO_VBLANK=0 #For NVIDIA``` \
  > и закомментируйте \
  > ```export vblank_mode=0 #For AMD, Intel and others``` \
  > с # в начале строки.

  Давайте создадим файл .desktop, чтобы osu! появился в разделе приложений:

  ```
  nano ~/.local/share/applications/osu.desktop
  ```

  Скопируйте-вставьте это:

  ```
  [Desktop Entry]
  Type=Application
  Comment=osu!
  Exec=.local/bin/osu
  GenericName=osu!
  Name=osu!
  StartupNotify=true
  ```
  Сохраните файл **Ctrl+O**, и закройте nano **Ctrl+X**.

  Чтобы сделать этот файл исполняемым, скопируйте это в терминал и нажмите **Enter**:

  ```chmod +x ~/.local/share/applications/osu.desktop```

  Теперь ваше приложение osu.desktop исполняемо!

  После этого скопируйте-вставьте это в терминал

  ```
  cd ~/Downloads && wget http://puu.sh/KAnxf/6e2425cc8f.xz -O wine-osu-7.15.2-x86_64.tar.xz && tar -xvf wine-osu-7.15.2-x86_64.tar.xz && cp -r wine-osu ~/wine-osu && rm -rf wine-osu && cd
  ```

  Давайте настроим pipewire. Скопируйте-вставьте это в терминал и нажмите **Enter**:

  ```
  cd && mkdir -p ~/.config/pipewire && cp -r /usr/share/pipewire/* ~/.config/pipewire/ && wget http://puu.sh/KBIwU/04254728f0.conf -O ~/.config/pipewire/pipewire.conf && wget http://puu.sh/KBIx1/120c9f7b39.conf -O ~/.config/pipewire/pipewire-pulse.conf && wget http://puu.sh/KBIx9/f8b9cdc5ce.conf -O ~/.config/pipewire/media-session.d/alsa-monitor.conf
  ```

  и после этого давайте перезапустим наш аудиосервер, чтобы применить изменения, скопируйте это в терминал и нажмите **Enter**:

  ```
  systemctl --user restart pipewire.service pipewire.socket pipewire-media-session.service pipewire-pulse.service pipewire-pulse.socket
  ```

  Аудиосервер Pipewire успешно настроен!

  Теперь вы можете закрыть терминал, нажав **Win+Shift+Q**.

  > Если ваш ПК достаточно мощный, загляните [в мой Telegram, чтобы изучить гайд по pipewire с минимально возможной задержкой аудио](https://t.me/vudekosu/596).

# Теперь вы можете запустить osu!

  Нажав Win+R, вы можете открыть список приложений, введите osu! и нажмите **Enter**:

  ![](https://vudek.s-ul.eu/v742bcLJ)

  Убедитесь, что галочка `Audio compatibility mode` включена.

# Как изменить герцовку монитора?

  ![Прочитайте это](https://github.com/Vudek/osu-on-linux/blob/main/refresh_rate.md)

# Как установить OTD? 

  Откройте терминал, нажав Win+Enter.
  Скопируйте это в терминал:

  ```
  sudo pacman -S --needed git base-devel && git clone https://aur.archlinux.org/yay-bin.git && cd yay-bin && makepkg -si && yay -S opentabletdriver osu-handler osu-mime
  ```

  > Когда вам будет предложено "Packages to CleanBuild", просто введите `N` в терминал и нажмите **Enter**.

  > Когда вам будет предложено "Diffs to show", просто введите `N` в терминал и нажмите **Enter**.
  
  Эта команда установит `yay`, `opentabletdriver`, `osu-handler` и `osu-mime`

  После установки OTD скопируйте-вставьте эти команды в терминал:

  ```
  echo "blacklist wacom" | sudo tee -a /etc/modprobe.d/blacklist.conf
  ```

  ```
  sudo rmmod wacom
  ```

  ```
  echo "blacklist hid_uclogic" | sudo tee -a /etc/modprobe.d/blacklist.conf
  ```

  ```
  sudo rmmod hid_uclogic
  ```

  ```
  systemctl --user daemon-reload
  ```

  ```
  systemctl --user enable opentabletdriver --now
  ```

  ```
  sudo udevadm control --reload-rules && sudo udevadm trigger
  ```
  
  ```
  systemctl --user start opentabletdriver --now
  ```

  Если появятся ошибки вроде "MODULE ISN'T LOADED", просто игнорируйте их.

  Давайте откроем OTD:

  - Переключите рабочий стол, нажав Win+3
  - Откройте список приложений, нажав Win+R
  - Поищите OpenTabletDriver
  - Нажмите **Enter**

  и OTD теперь откроется!

  Настройте вашу область, фильтры, сохраните/примените. Закройте GUI **Ctrl+Q** или Win+Shift+Q.

  Переключите на 1-й рабочий стол, нажав **Win+1**. Теперь вы можете играть в osu!, поздравляю!

  > Убедитесь, что `Raw input` отключен

  > Убедитесь, что `Map absolute raw input to the osu! window` включен.

# Как изменить раскладки клавиатуры?

  Зависит от того, какие языки вы хотите.

  Сначала откройте терминал и введите это:

  ```
  nano ~/.config/i3/config
  ```

  и перейдите к последней строке:
  
  ```
  exec --no-startup-id "setxkbmap -layout us -option grp:alt_shift_toggle"
  ```

  и добавьте предпочитаемый язык после `us`. Например:

  ```
  exec --no-startup-id "setxkbmap -layout us,ru -option grp:alt_shift_toggle"
  ```

  Сохраните файл, нажав **Ctrl+O** и Enter, **Ctrl+X** для закрытия.

  > Вы также можете изменить привязку для смены раскладки на `grp:ctrl_shift_toggle` или `grp:caps_toggle` (последняя моя любимая).

  и введите в терминал и нажмите **Enter**:

  ```
  setxkbmap -layout us,ru -option grp:alt_shift_toggle
  ```
  
  чтобы принудительно применить изменения прямо сейчас!

#  Руководство написано [Vudek](https://osu.ppy.sh/users/8816345). 

  [Тиньк](https://pay.cloudtips.ru/p/1c9fd916) 
  
  BTC - `bc1q29v9rcdzhs8ds35wmlr8a58u0qk3cvaj2wnpvr`
  
  ETH - `0x7BA5a25A669Fb3570EC7C047b978066D309753A2`
  
  USDT (TRC20) - `TTgd8EejwyxzTNbzLpGK7L5gzfRAdXaxjH`
  
  USDT (ERC20) - `0x7BA5a25A669Fb3570EC7C047b978066D309753A2`

Мяу :3
