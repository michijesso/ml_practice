
## Сборка рабочего "окружения" для Fedora Workstation 31

1. Добавить репозитории RPM Fusion и обновить все пакеты программного обеспечения

```
sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm

dnf update

```

2. Скачать установщик **[Anaconda](https://www.anaconda.com/distribution/#download-section)** (пакетный менеджер, нужен для простой загрузки нужных библиотек со всеми зависимостями)

3. Установить в `/opt/Anaconda3`

```
sudo chmod 777 ./Anaconda3-2019.10-Linux-x86_64.sh
./Anaconda3-2019.10-Linux-x86_64.sh
```

4. Добавить путь к установленным исходникам в ~/.bashrc

```
PATH=$PATH:/opt/Anaconda3
```

5. Установить Jupyter lab

```
conda install -c conda-forge jupyterlab
```

6. Установить пакеты Julia с помощью пакетного менеджера dnf:

```
dnf install julia
```

7. Скачать .rpm пакет редактора **[Atom](https://atom.io/)** и установить его

Upd: как раз к моменту наших с Вами практических занятий вышла новая версия (0.12.) пакета для Atom'a, которая ломает REPL в IDE, поэтому нужно будет часть пакетов поставить руками

1. Открыть менеджер пакетов Julia (прописать в консоли `julia` и нажать `]`)
2. Установить стабильный пакет для Atom'a:
```
add Atom@0.11.3
```
Закрыть терминал.

3. Открыть терминал и установить стабильные пакеты для поддержки Julia в Atom'e:
```
apm install julia-client@0.11.3
apm install ink@0.11.3

```
Закрыть терминал.

8. Дальнейшие инструкции по установке пакета Juno можно найти **[тут](https://docs.junolab.org/latest/man/installation/)** (начиная с 3 пункта)

Upd: пакеты `julia-client` и `ink` обновлять не нужно.
