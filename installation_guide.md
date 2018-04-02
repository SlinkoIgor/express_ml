Нам нужно установить необходимые python-пакеты:
jupyter matplotlib seaborn pandas numpy scikit-learn plotly graphviz pydotplus ipywidgets

Кроме того понадобятся xgboost и catboost

# Если у вас Windows:
Достаточно зайти на https://www.anaconda.com/download/ и скачать клиент Анаконды. Там будет предустановлено большинство пакетов и Jupyter. Недостающие можно будет установить из Navigator (ставится вместе с Анакондой).

# Установка через conda (проще всего):

1) https://conda.io/miniconda

Для этого курса я использую 64-битную c python3.6. Там же есть ссылка на то, как это устанавливать ("See the Quick install page for installation instructions."). Можно использовать 3-ий питон.

2) В командной строке:
> conda install jupyter matplotlib seaborn pandas numpy scikit-learn plotly graphviz pydotplus ipywidgets

> jupyter nbextension enable --py widgetsnbextension

2.1) для визуализации дерева нужна библиотека graphviz (мы ее установили выше), но иногда это не работает. В таком случае, можно установить ее отдельно. В Linux это делается через
> apt-get install graphviz

3) Установка xgboost:
> conda install -c conda-forge xgboost

Либо устанавливать из исходников по инструкции: http://xgboost.readthedocs.io/en/latest/build.html

4) Устанока catboost:
> pip install catboost

...почему-то ставит для 3-го питона. Если у вас второй, надо собирать из исходников: https://tech.yandex.com/catboost/doc/dg/concepts/python-installation-docpage/

Если ругается, что нет pip - устанавливаем его: https://pip.pypa.io/en/stable/installing/

5) Для обновления анакондовских пакетов, можно запускать
> conda update --all

### Запуск Jupyter

В директории, где вы хотите чтобы был корень, нужно запустить команду

>`jupyter notebook`<br>

Удобно запускать ноутбук под nohup

>`nohup jupyter notebook &`<br>

это специальная команда, которая перехватывает сигнал потери связи SIGHUP. Теперь вы можете закрыть консоль и не беспокоиться, что ноутбук упадет. Правда, убивать ноутбук придется через kill или менеджер задач

# Установка через pip:

## Использование virtualenv

Virtualenv позволяет заключить в отдельный каталог необходимые версии python-пакетов и использовать только их. Используя virtualenv, Вы можете устанавливать свежие версии пакетов из Python Package Index, при этом не огребать проблем с несовместимостью версий пакетов с установленными в системе. Нормальным решением также является установка python-пакетов через pip в системные каталоги. Для этого не нужно ничего мутить с virtualenv, но запускать pip при этом следует от рута:

> `$ sudo pip install "необходимые пакеты" `

Но напоминаем, пакеты могут конфликтовать с системными, может фейлиться сборка, могут импортироваться старые версии и возникать другие проблемы...

Ок, определились на счет virtualenv. Теперь нужно установить некоторые пакеты в систему:

### Ubuntu:

Для сохранения психического здоровья, используйте Ubuntu 12.04 LTS или выше.

Устанавливаем необходимые тулзы для Python:
>`$ sudo apt-get update`<br>
>`$ sudo apt-get install python-pip python-dev python-virtualenv build-essential`

Устанавливаем пакеты, необходимые для сборки NumPy, SciPy и Matplotlib:

>`$ sudo apt-get install libatlas-base-dev gfortran`<br>
>`$ sudo apt-get build-dep python-matplotlib`<br>


### MacOS:

Придется поставить <a href="http://brew.sh/" target="_blank">Homebrew</a> с вытекающей оттуда установкой <a href="https://developer.apple.com/downloads/" target="_blank">Command Line Tools</a> или <a href="https://developer.apple.com/xcode/" target="_blank">XCode</a>. Следуйте указаниям с сайта Homebrew и у вас все получится.

Далее устанавливаем свежую версию Python и virtualenv:

>`$ brew install python --with-brewed-openssl`<br>

Устанавливаем фортран (нужен для сборки NumPy и SciPy):

>`$ brew install gcc pkg-config freetype`


### Далее - для обеих платформ:

Создаем виртуальное окружение питона (virtualenv):
>`$ virtualenv ml`

Активируем его:
>`$ source ml/bin/activate`

(в консоли должен появиться соотв. префикс)

>`(ml)$ pip install --upgrade pip`<br>
>`(ml)$ pip install jupyter matplotlib seaborn pandas numpy scikit-learn plotly graphviz pydotplus ipywidgets`<br>

Установку xgboost и catboost можно произвести по инструкциям на соотв. сайтах:
http://xgboost.readthedocs.io/en/latest/build.html <br>
https://tech.yandex.com/catboost/doc/dg/concepts/python-installation-docpage (для 2-го питона pip install сейчас не работает, собирайте из исходников)

Для того, чтобы деактивировать виртуальное окружение, необходимо сказать

> `(ml)$ deactivate`<br>
> `$ python   # префикс пропал, python будет выполняться в системном окружении`

<img src="http://www.linusakesson.net/programming/kernighans-lever/cat.png">
