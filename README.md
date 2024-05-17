[![Tests](https://github.com/tokarevsas31/ml_fastapi_tests/actions/workflows/python-app.yml/badge.svg)](https://github.com/tokarevsas31/ml_fastapi_tests/actions/workflows/python-app.yml)

# An example of ML Application with the pretrained model and test.

An example of English text tone detection with [Hugging Face](https://huggingface.co/) library.


# Документация Приложения FastAPI для Анализа Тональности
## Описание
Приложение представляет собой веб-сервис, разработанный с использованием FastAPI, который позволяет анализировать тональность текстовых сообщений. Сервис использует модуль pipeline из библиотеки Hugging Face Transformers для автоматического определения тональности текста.

## Установка
Для работы с этим приложением необходимо установить следующие зависимости:

FastAPI
Uvicorn (для запуска сервера)
Transformers (библиотека Hugging Face для анализа тональности)
Torch (основная библиотека для работы с нейронными сетями)
Httpx (HTTP-клиент)

## Установите их через pip:

pip install fastapi uvicorn transformers torch httpx

## Конфигурация
Сервер должен быть запущен с помощью команды:

uvicorn main:app --reload
где main — это имя файла, содержащего ваше приложение, а app — экземпляр FastAPI внутри этого файла.

## Эндпоинты
GET /
Описание: Возвращает приветственное сообщение.

Ответ:

200 OK: Возвращает JSON-объект с сообщением "Hello World".
POST /predict/
Описание: Анализирует тональность переданного текста.

Запрос:

body (JSON): Объект item, содержащий поле text с текстом для анализа.
Ответ:

200 OK: Возвращает JSON-объект с результатами анализа тональности.

## Примеры
Приветствие
GET запрос к корневому эндпоинту (/) вернет следующий ответ:

{"message": "Hello World"}
Анализ тональности
POST запрос к эндпоинту /predict/ с текстом "I like machine learning!" вернет следующий ответ:

{
"label": "POSITIVE",
"score": 0.9995
}
Аналогично, запрос с текстом "I hate machine learning!" вернет:

{
"label": "NEGATIVE",
"score": 0.9995
}

## Заключение
Приложение предназначено для быстрого и удобного анализа тональности текстовых сообщений. Оно может быть полезным инструментом для обработки больших объемов текстовой информации или для создания систем, требующих оценки эмоциональной реакции пользователей на различные темы.
