[<- Назад](/README.md)

## 1. Установите tmux

- macOS (Homebrew)

```sh
brew install tmux
tmux -V
```

Если Homebrew ещё не установлен:

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Linux (Debian / Ubuntu)

```sh
sudo apt update
sudo apt install tmux
tmux -V
```

## 2. Подключите конфиг

Создайте символическую ссылку:

```sh
ln -sf ~/Developer/tmux/tmux.conf ~/.tmux.conf
```

После этого изменения в репозитории будут сразу попадать в рабочий конфиг.

## 3. Первый запуск

```sh
tmux
```

Для выхода из сессии без завершения работы нажмите `` ` `` `d`.

Чтобы полностью выйти из `tmux`, выполните:

```sh
exit
```

## 4. Применить изменения

После редактирования `tmux.conf` перезагрузите конфиг прямо из `tmux`:

```text
` =
```
