# Parser
Для работы нужно скачать репо через `git clone`. 
Скачанные отчеты будут появляться в папке **EDGAR**, которая автоматически создавается в директории клонированного репозитория.

Запуск программы происходит через файл **parser.py** *(лично я запускаю его через терминал)*

Структура хранения отчетов: `EDGAR/*ticker*/*тип отчета*/filing-details.html`

Например для тикера AAPL и отчета 10-K путь до документа будет выглядеть следующим образом: `EDGAR/AAPL/10-K/filing-details.html`

При необходимости можно выбирать какие отчеты нужно скачать. Полный список доступных форматов можно посмотреть в `Downloader/_constants.py` в пункте **SUPPORTED_FILINGS**

Для загрузки 10-K отчетов реализовано следующим образом:

```
	dl = Downloader()
	dl.get("10-K", "AAPL", amount=1)
```
- Downloader() - указывается путь для создания папки с отчетами (задается в виде строки "/path/to/your/location", по умолчанию сохраняет в корневую папку с проектом)
- "10-K" - тип отчета, который необходимо скачать, задается в виде строки
- "AAPL" - ticker или CIK компании
- amount - количество отчетов

Тикеты, по которым нет отчетов, сохраняются в корне папки с проектом в файле **empty_tickers.txt**
