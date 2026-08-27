# RAG Workshop — День 2: Асистент ріелтора (Realistic End-to-End)

Реалістичний приклад RAG-системи на синтетичних, але структурованих даних реальної агентури нерухомості.

**Що розбираємо:**
- **Реальні формати даних**: CSV (каталог квартир, клієнти), Markdown (політики, чеклисти), PDF (договори)
- **ChromaDB у режимі персистентності** — індекс зберігається між сеансами
- **Метадані для retrieval**: `source` для фільтрації й цитування
- **Стабільна індексація**: `upsert` зі стійкими ID без дублікатів при повторному запуску
- **Маршрутизація контексту**: LLM-роутер `where` обмежує пошук до потрібних файлів
- **Історія діалогу**: чат у межах сесії з контекстом попередніх репік
- **Промпт-інжиніринг**: цитування джерел, галюцинаціональна стійкість, структурована відповідь
- **Telegram-бот**: інтерфейс для RAG-асистента
- **Evaluation**: золотий набір і метрики якості (coverage джерел, судження LLM)

---

## Необхідні credentials

Для цього воркшопу потрібні:

**1. OpenAI API key** (`OPENAI_API_KEY`)
- Отримати тут: [https://platform.openai.com/](https://platform.openai.com/)
- На Colab додайте через Secrets (🔑 icon)
- Потрібен активний billing на акаунті

**2. Telegram Bot Token** (`TELEGRAM_BOT_TOKEN`) - опційно
- Створіть бота через **@BotFather** у Telegram
- Отримайте токен, додайте до Secrets
- Опційно — бот запускається окремою коміркою

---

## Відкрити у Google Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/NatalyUA/RAG-workshop_Day2/blob/main/rag_workshop_02_realtor_assistant.ipynb)

Пряме посилання:
https://colab.research.google.com/github/NatalyUA/RAG-workshop_Day2/blob/main/rag_workshop_02_realtor_assistant.ipynb

---

## Вміст (День 2)

- `rag_workshop_02_realtor_assistant.ipynb` — основний ноутбук
- `use_case_realtor_assistant.md` — контекст юзкейсу
- `data/` — корпус документів для індексації (CSV, Markdown, PDF)
- `README.md` — цей файл

---

## Швидкий старт (для учасників у Colab)

1. **Відкрийте** notebook у Colab через бейдж вище.
2. **Збережіть копію**: `File → Save a copy in Drive`.
3. **Додайте secrets** (ліва панель → 🔑 key icon):
   - `OPENAI_API_KEY` — ваш OpenAI API ключ
   - `TELEGRAM_BOT_TOKEN` — токен Telegram-бота (опційно)
4. **Запустіть комірки** послідовно (Shift+Enter):
   - Комірка **Setup** встановить бібліотеки
   - Комірка **Індексація** завантажить `data/` і створить вектор-індекс
   - Комірки **Retrieval** й **RAG** покажуть приклади пошуку й відповідей
   - Комірка **Telegram Bot** (опційно) запустить бота
5. **Для локального запуску**: див. розділ **Локальний запуск** нижче

---

## Локальний запуск

1. **Клонуйте repo або завантажте файли** до папки на машині
2. **Створіть virtual environment**:
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # На Windows: .venv\Scripts\activate
   ```
3. **Встановіть залежності**:
   ```bash
   pip install -r requirements.txt
   ```
4. **Додайте credentials** у `.env` файл у корені проєкту:
   ```
   OPENAI_API_KEY=sk-...
   TELEGRAM_BOT_TOKEN=123456:ABC...  # (опційно)
   ```
5. **Запустіть ноутбук**:
   ```bash
   jupyter notebook
   # або
   python -m jupyter lab
   ```

---

## Troubleshooting

- **`OPENAI_API_KEY is missing`**
  - **На Colab**: Додайте до Secrets (🔑 icon, ліва панель)
  - **Локально**: Перевірте `.env` файл або встановіть environment variable: `export OPENAI_API_KEY=sk-...`

- **`ModuleNotFoundError: No module named 'chromadb'`**
  - Запустіть комірку **Setup** (встановлення залежностей)
  - На локалі: `pip install -r requirements.txt`

- **Telegram-бот не запускається**
  - Переконайтеся, що `TELEGRAM_BOT_TOKEN` додано до Secrets (Colab) або `.env` (локально)
  - Токен отримайте від **@BotFather** у Telegram

- **GoogleDrive не монтується на Colab**
  - Дозвольте доступ, коли з'явиться запит
  - Папка `RAG-workshop_Day2` повинна існувати на Drive
  - Альтернатива: завантажте файли прямо на Colab через Upload



