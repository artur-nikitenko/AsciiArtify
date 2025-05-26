# MVP: Розгортання go-demo-app з ArgoCD

## Ціль

* Створити ArgoCD Application, що відстслідковує репозиторій:
  [https://github.com/artur-nikitenko/go-demo-app](https://github.com/artur-nikitenko/go-demo-app)
* Налаштувати автосинхронізацію (Auto Sync)
* Показати, що зміни в Git автоматично розгортуються на кластері

## Кроки реалізації

1. Створено fork репозиторію `go-demo-app`
2. Створено ArgoCD Application (через UI):
3. Зроблено мінімальну зміну (збільшено кількість api-pod до 2 в YAML)
4. ArgoCD визначив OutOfSync статус та здійснив автосинхронізацію (видно з логу в відео)

## Демонстрація

[🎥 Переглянути демо Auto Sync](https://asciinema.org/a/fSl1TN87chYkVsus2sjouKzPD)
[🎥 Переглянути демо роботи go-app](https://asciinema.org/a/sVuw3UNEddZXrPY4HZdg30xVk)

> *На першому відео показано, як ArgoCD відслідковує та автоматично застосовує зміну з Git-репозиторію без втручання вручну.*

