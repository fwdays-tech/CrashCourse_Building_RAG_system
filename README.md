# RAG Workshop

Практичний вступ до Retrieval-Augmented Generation (пошук із підсиленням генерації, RAG):
- embeddings (ембеддінги)
- chunking (чанкінг)
- retrieval (пошук) із vector store (векторного сховища, ChromaDB)
- augmentation (аугментація)
- generation (генерація)

---

## Необхідні credentials (облікові дані)

Для цього воркшопу потрібні такі credentials:

1. **OpenAI API key** (`OPENAI_API_KEY`)
  - Отримати тут: [https://platform.openai.com/](https://platform.openai.com/)
  - Sign up -> API keys -> Create new secret key
  - Важливо: одного ключа недостатньо. На акаунті має бути активний billing (білінг) / кредит (баланс), щоб були доступні токени для запуску моделей.
  - Для воркшопу використовуємо найдешевші моделі (цього достатньо), але токени все одно мають оплачуватися з доступного кредиту.

2. **Додатково для Day 3 (створення локального пайплайну)**
  - Встановити Ollama.
  - Для Python налаштувати зв'язку Python + VS Code за коротким туторіалом.

> Не хардкодьте secrets (секрети) в комірках notebook (ноутбука).

---

## Відкрити в Colab

Day 1:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fwdays-tech/CrashCourse_Building_RAG_system/blob/main/Day_1/rag_workshop_00_intro_v2.ipynb)

Пряме посилання:
https://colab.research.google.com/github/fwdays-tech/CrashCourse_Building_RAG_system/blob/main/Day_1/rag_workshop_00_intro_v2.ipynb

Day 2:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/fwdays-tech/CrashCourse_Building_RAG_system/blob/main/Day_2/rag_workshop_02_realtor_assistant.ipynb)

Пряме посилання:
https://colab.research.google.com/github/fwdays-tech/CrashCourse_Building_RAG_system/blob/main/Day_2/rag_workshop_02_realtor_assistant.ipynb

---

## Troubleshooting (усунення проблем)

- **`OPENAI_API_KEY is missing`**
  - Додайте ключ у Colab Secrets або задайте його в комірці до створення клієнта `OpenAI()`.



