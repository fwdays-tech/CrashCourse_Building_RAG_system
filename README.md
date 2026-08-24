# RAG Workshop (Day 1)

Практичний вступ до Retrieval-Augmented Generation(пошук із підсиленням генерації, RAG):
- embeddings(ембеддінги)
- chunking(чанкінг)
- retrieval(пошук) із vector store(векторного сховища, ChromaDB)
- augmentation(аугментація)
- generation(генерація)

---

## Необхідні credentials(облікові дані)

Для цього воркшопу потрібні такі credentials(облікові дані):

**1. OpenAI API key** (`OPENAI_API_KEY`)
- Отримати тут: [https://platform.openai.com/](https://platform.openai.com/)
- Sign up → API keys → Create new secret key
- Важливо: одного ключа недостатньо — на акаунті має бути активний billing(білінг) / кредит(баланс), щоб були доступні токени для запуску моделей.
- Для воркшопу використовуємо найдешевші моделі (цього достатньо), але токени все одно мають оплачуватися з доступного кредиту.

> Не хардкодьте secrets(секрети) в комірках notebook(ноутбука).

---

## Відкрити в Colab

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/NatalyUA/RAG-workshop/blob/main/rag_workshop_00_intro_v2.ipynb)

Пряме посилання:
https://colab.research.google.com/github/NatalyUA/RAG-workshop/blob/main/rag_workshop_00_intro_v2.ipynb

---

## Вміст (Day 1)

- `rag_workshop_00_intro_v2.ipynb`
- `RAG_intro.png`
- `RAG_mindmap.png`
- `RAG_end-to-end_pipeline.png`

---

## Швидкий старт (для учасників)

1. Відкрийте notebook(ноутбук) у Colab через бейдж вище.
2. Створіть власну editable copy(редаговану копію): `File → Save a copy in Drive`.
   - Важливо: відкриття посилання **не** створює персональну копію автоматично.
   - Спільне GitHub-посилання відкриває source version(вихідну версію) notebook(ноутбука) у Colab.
3. Додайте credentials(облікові дані) у **Colab Secrets** (ліва панель → 🔑 key icon):
   - `OPENAI_API_KEY` — ваш OpenAI ключ
   - Альтернатива: задати як тимчасову environment variable(змінну середовища) в комірці (не рекомендовано для shared notebooks(спільних ноутбуків)).
4. Запускайте комірки зверху вниз.
5. Якщо встановлення пакетів просить runtime restart(перезапуск середовища) — перезапустіть і запустіть усе знову.

---

## Troubleshooting(усунення проблем)

- **`OPENAI_API_KEY is missing`**
  - Додайте ключ у Colab Secrets або задайте його в комірці до створення клієнта `OpenAI()`.



