Этот документ описывает установку Python и Jupyter использованием docker.

# Установка Docker

Скачать и установить docker в соответствии с инструкциями на https://www.docker.com/community-edition

# Запуск Jupyter

- Открыть консоль зайти в каталог express_ml
- Запустить `docker-compose up`
- В консоли появится выдача вида:

```
jupyter_1  | [I 17:51:18.034 NotebookApp] Writing notebook server cookie secret to /home/jovyan/.local/share/jupyter/runtime/notebook_cookie_secret
jupyter_1  | [W 17:51:18.174 NotebookApp] WARNING: The notebook server is listening on all IP addresses and not using encryption. This is not recommended.
jupyter_1  | [I 17:51:18.227 NotebookApp] JupyterLab alpha preview extension loaded from /opt/conda/lib/python3.5/site-packages/jupyterlab
jupyter_1  | [I 17:51:18.244 NotebookApp] Serving notebooks from local directory: /home/jovyan/work
jupyter_1  | [I 17:51:18.244 NotebookApp] 0 active kernels
jupyter_1  | [I 17:51:18.245 NotebookApp] The Jupyter Notebook is running at: http://[all ip addresses on your system]:8888/?token=d2ae14bcc24a55b66571fc2f43374b0ff86cc92f726ac734
jupyter_1  | [I 17:51:18.245 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
jupyter_1  | [C 17:51:18.246 NotebookApp]
jupyter_1  |     
jupyter_1  |     Copy/paste this URL into your browser when you connect for the first time,
jupyter_1  |     to login with a token:
jupyter_1  |         http://localhost:8888/?token=d2ae14bcc24a55b66571fc2f43374b0ff86cc92f726ac734
```

- Открыть ссылку в браузере

# Остановка Jupyter

- Нажать `Control-C` в консоли из которой был произведен запуск.
