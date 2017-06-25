# Если вы не хотите заморачиваться:

1) https://conda.io/miniconda

Для этого курса я использую 64-битную c python2.7. Там же есть ссылка на то, как это устанавливать ("See the Quick install page for installation instructions.")

2) В командной строке:
> conda install jupyter matplotlib seaborn pandas numpy scikit-learn

3)
> conda install -c conda-forge xgboost

4) ...

5) Время от времени стоит запускать
> conda update --all

### Запуск Jupyter

В директории, где вы хотите чтобы был корень, нужно запустить команду

>`jupyter notebook`<br>

Удобно запускать ноутбук под nohup

>`nohup jupyter notebook &`<br>

это специальная команда, которая перехватывает сигнал потери связи SIGHUP. Теперь вы можете закрыть консоль и не беспокоиться, что ноутбук упадет. Правда, убивать ноутбук придется через kill или менеджер задач

# Если вы хотите заморачиваться:

## Использование virtualenv


Virtualenv позволяет заключить в отдельный каталог необходимые версии python-пакетов и использовать только их. Используя virtualenv, Вы можете устанавливать свежие версии пакетов из Python Package Index, при этом не огребать проблем с несовместимостью версий пакетов с установленными в системе. Нормальным решением также является установка python-пакетов через pip в системные каталоги. Для этого не нужно ничего мутить с virtualenv, но запускать pip при этом следует от рута:

> `$ sudo pip install juptyter numpy scipy pandas matplotlib scikit-learn`

Но напоминаем, пакеты могут конфликтовать с системными, может фейлиться сборка, могут импортироваться старые версии и возникать другие проблемы...

Для создания виртуального окружения необходимо сказать

> `$ virtualenv yourenv`

при этом будет создан каталог `yourenv` с чистым окружением без каких либо пакетов. Для использования виртуального окружения можно использовать команды из соответствующего каталога:

> `$ yourenv/bin/python script.py`<br>
> `$ yourenv/bin/pip install ... # установка пакетов в виртуальное окружение`<br>
> `$ yourenv/bin/ipython`

Для того чтобы не говорить префикс `yourenv/bin` удобно в текущей сесии командной строки выставить необходимые переменные окружения (активировать виртуальное окружение):

> `$ source yourenv/bin/activate`<br>
> `(yourenv)$ pip install ... # установка пакетов в виртуальное окружение`<br>
> `(yourenv)$ jupiter notebook`

После активации, у приглашения командной строки появится префикс `(yourenv)`.

Для того, чтобы деактивировать виртуальное окружение, необходимо сказать

> `(yourenv)$ deactivate`<br>
> `$ python   # префикс пропал, python будет выполняться в системном окружении`

## Ubuntu:

Для сохранения психического здоровья, используйте Ubuntu 12.04 LTS или выше.

Устанавливаем необходимые тулзы для Python:
>`$ sudo apt-get update`<br>
>`$ sudo apt-get install python-pip python-dev python-virtualenv build-essential`

Устанавливаем пакеты, необходимые для сборки NumPy, SciPy и Matplotlib:

>`$ sudo apt-get install libatlas-base-dev gfortran`<br>
>`$ sudo apt-get build-dep python-matplotlib`<br>

Создаем виртуальное окружение питона (virtualenv):
>`$ virtualenv ml`

Активируем его:
>`$ source ml/bin/activate`

(в консоли должен появиться соотв. префикс)

>`(ml)$ pip install --upgrade pip`<br>
>`(ml)$ pip install jupyter`<br>
>`(ml)$ pip install numpy scipy pandas matplotlib scikit-learn seaborn`<br>


## MacOS:

Придется поставить <a href="http://brew.sh/" target="_blank">Homebrew</a> с вытекающей от туда установкой <a href="https://developer.apple.com/downloads/" target="_blank">Command Line Tools</a> или <a href="https://developer.apple.com/xcode/" target="_blank">XCode</a>. Следуйте указаниям с сайта Homebrew и у вас все получится.

Далее устанавливаем свежую версию Python и virtualenv:

>`$ brew install python --with-brewed-openssl`<br>

Устанавливаем фортран (нужен для сборки NumPy и SciPy):

>`$ brew install gcc pkg-config freetype`

Создаем виртуальное окружение:

>`$ pip install virtualenv`<br>
>`$ virtualenv shad-env`<br>

Активируем его:
>`$ source ml/bin/activate`<br>

Устанавливаем необходимые пакеты питона:

>`(ml)$ pip install jupyter numpy scipy pandas scikit-learn matplotlib seaborn`

## Windows:

<a href="http://python-xy.github.io" target="_blank">Python(x,y)</a>

Говорят, что иногда бывают проблемы. Чтобы проверить, что все выполнилось хорошо, в питоне запускаем юнит-тесты:
>`import numpy`<br>
>`numpy.test()`<br>

Аналогично с pandas, pylab, sklearn.

Если вдруг вываливается ошибка, то можно попробовать установить Python и библиотеки другим способом.

Минимальный набор для работы:

- Python 2.7
- Jupiter Notebook
- NumPy
- Matplotlib
- Pandas
- SciKit-Learn

Лучше ставить 32-битные версии, поскольку 64-битные не всегда работают корректно под Windows. Обратите внимание, что некоторые библиотеки будут иметь дополнительные зависимости в виде других библиотек, их тоже придется поставить.

## XGBoost:
http://xgboost.readthedocs.io/en/latest/build.html

<img src="http://www.linusakesson.net/programming/kernighans-lever/cat.png">
