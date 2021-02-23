---
layout: page
title: Интеграция правил flake8 в PyCharm
permalink: /pages/pcintegration.html
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