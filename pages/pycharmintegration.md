---
layout: page
title: Интеграция правил flake8 в PyCharm
permalink: /pages/pycharmintegration.html
---

#### Для интеграции описаний правил flake8 и примеров для них в JetBrains PyCharm необходимо выполнить следующее:

1. Установить flake8
```python
pipenv install flake8 --dev
```
2. Зарегестрировать flake8 в качестве внешнего инструмента
```python
PyCharm -> Preferences -> Tools -> External Tools -> "+"
Name:               flake8
Description:        Flake8 Runner
Program:            $PyInterpreterDirectory$/flake8
Arguments:          $FilePath$ --format %(path)s:%(row)d,%(col)d:%(code)s:%(text)s:https://flake8.rsln.dev/rules/%(code)s.html
Workign directory:  $ContentRoot$
```
3. Установить в PyCharm плагин [Awesome Console](https://github.com/anthraxx/intellij-awesome-console)  
Данный плагин позволяет вводить кликабельные элементы в консоль PyCharm
```python
PyCharm -> Preferences -> Plugins
```

В результате запуска flake8 для проверяемого файла, в консоли PyCharm мы видим кликабельные ссылки на каждое правило
```python
PyCharm -> Tools -> Plugins -> External Tools -> flake8
```
![PyCharm falke8 integration example](demo.png "flake8 PyCharm Demo")