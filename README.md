# Лабораторная работа № 2 — Инфраструктура ML-проекта (продолжение)

##  Описание
Проект продолжает реализацию полного жизненного цикла ML-модели, включая подготовку данных, обучение, контейнеризацию, CI/CD, веб-интерфейс и расширенную инфраструктуру.

##  Статус проекта на данный момент
- **Структура**: сохранены папки `app`, `infra/compose`, `data`, `model`, `src`, `tests`, `web`.
- **Инфраструктура контейнеризации**: присутствуют `Dockerfile`, `docker-compose.yml`, `.dockerignore`.
- **Версионирование данных и моделей**: настроен DVC (`.dvc`, `dvc.yaml`, `dvc.lock`, `.dvcignore`).
- **CI/CD**: каталог `.github/workflows/`
- **Конфигурация и зависимости**: файлы `config.ini`, `requirements*.txt`, `pyproject.toml`, `pytest.ini`.

##  Структура проекта

| Папка/файл                     | Назначение                                                                 |
|--------------------------------|----------------------------------------------------------------------------|
| `app/`                         | Основное приложение                     |
| `infra/compose/`               | Файлы инфраструктуры (docker-compose, окружение)                           |
| `data/`                        | Исходные и промежуточные данные (управляются DVC)                          |
| `model/`                       | Сохраненные обученные модели                                               |
| `src/`                         | Код вызова моделей, обучение, предобработка                               |
| `tests/`                       | Модульные/интеграционные тесты                                             |
| `web/`                         | Веб-интерфейс/API (Flask/FastAPI)                                          |
| `.dvc`, `dvc.yaml`, `dvc.lock` | Конфиг DVC, пайплайн, версии данных/моделей                                |
| `.dvcignore`, `.gitignore`     | Правила исключения файлов для DVC и Git                                   |
| `Dockerfile`                   | Создание Docker-образа проекта                                             |
| `docker-compose.yml`           | Описание и запуск контейнеров (инфраструктуры приложения)                  |
| `.github/workflows/`           | CI/CD процессы через GitHub Actions                                        |
| `config.ini`                   | Настройки и гиперпараметры модели                                          |
| `requirements.txt`, `requirements-serve.txt`, `pyproject.toml` | Управление зависимостями |
| `pytest.ini`                   | Конфигурация для тестов (pytest)                                           |
### Клонирование и установка зависимостей:
```bash
git clone https://github.com/Mitlyy/DB_tech_lab_2.git
cd DB_tech_lab_2
pip install -r requirements.txt
```
###  Использование 
```
dvc repro

docker-compose up

curl -X POST "http://localhost:8000/predict" \
     -H "Content-Type: application/json" \
     -d '{"feature1": 0.5, "feature2": 1.2}'
```
