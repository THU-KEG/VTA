README

# Dataset files

To facilitate the development and evaluation for future VTA systems, we present the **VTA** dataset, which consists of 3 kinds of data: 

- general dialogue quality

  - Each csv file contains:

    `category, course, query, answer, coherence, informativeness, hallucination, humanness, helpfulness, instructiveness`

  - where `category, course` is the background course that the user is learning
  - `query, answer` is a round interaction between user and bot.
  - `coherence, informativeness, hallucination, humanness, helpfulness, instructiveness` are six evaluation scores labeled by annotators

- intention classification

  - Each xlsx file contains:

    `id, question, session_id, category`

  - where `question` is the real user query after anonymization

  - each turn of query has a specific `id`, multiple turns of the same session shares a `session_id`

  - `category` is the fine-grained intention labeled by annotators

- question answering

  - Each xlsx file contains:

    `id, question, session_id, category, answer`

  - where `id, question, session_id, category` are derived from the intention classification dataset

  - we label reference answer for those `简单问题(simple question) ` and `复杂问题(complex question) ` category

```bash
.
└── final_dataset
    ├── general_dialogue_quality
    │   ├── labeled
    │   │   ├── CDial-GPT
    │   │   │   ├── general
    │   │   │   │   ├── CDial-GPT_general_1.csv
    │   │   │   │   └── CDial-GPT_general_2.csv
    │   │   │   └── specific
    │   │   │       ├── CDial-GPT_specific_1.csv
    │   │   │       └── CDial-GPT_specific_2.csv
    │   │   ├── CoT-10b
    │   │   │   ├── general
    │   │   │   │   ├── CoT-10b_general_1.csv
    │   │   │   │   └── CoT-10b_general_2.csv
    │   │   │   └── specific
    │   │   │       ├── CoT-10b_specific_1.csv
    │   │   │       └── CoT-10b_specific_2.csv
    │   │   ├── CoT-130b
    │   │   │   ├── CoT-130b_general_1.csv
    │   │   │   └── CoT-130b_general_2.csv
    │   │   ├── CPM2
    │   │   │   ├── CPM2_1.csv
    │   │   │   └── CPM2_2.csv
    │   │   ├── EVA
    │   │   │   ├── general
    │   │   │   │   ├── EVA_general_1.csv
    │   │   │   │   └── EVA_general_2.csv
    │   │   │   └── specific
    │   │   │       ├── EVA_specific_1.csv
    │   │   │       └── EVA_specific_2.csv
    │   │   ├── GLM
    │   │   │   ├── GLM_1.csv
    │   │   │   └── GLM_2.csv
    │   │   ├── GLM-130b
    │   │   │   ├── general
    │   │   │   │   ├── GLM-130b_general_1.csv
    │   │   │   │   └── GLM-130b_general_2.csv
    │   │   │   └── specific
    │   │   │       ├── GLM-130b_specific_1.csv
    │   │   │       └── GLM-130b_specific_2.csv
    │   │   ├── GPT-3
    │   │   │   ├── general
    │   │   │   │   ├── GPT-3_general_1.csv
    │   │   │   │   └── GPT-3_general_2.csv
    │   │   │   └── specific
    │   │   │       ├── GPT-3_specific_1.csv
    │   │   │       └── GPT-3_specific_2.csv
    │   │   ├── PLATO-XL
    │   │   │   ├── general
    │   │   │   │   ├── PLATO-XL_general_1.csv
    │   │   │   │   └── PLATO-XL_general_2.csv
    │   │   │   └── specific
    │   │   │       ├── PLATO-XL_specific_1.csv
    │   │   │       └── PLATO-XL_specific_2.csv
    │   │   └── Xiaomu
    │   │       └── Xiaomu.csv
    │   └── unlabeled
    │       ├── CDial-GPT
    │       │   ├── general.csv
    │       │   └── specific.csv
    │       ├── CoT-10b
    │       │   ├── general.csv
    │       │   └── specific.csv
    │       ├── CoT-130b
    │       │   └── general.csv
    │       ├── CPM2
    │       │   └── CPM2.csv
    │       ├── EVA
    │       │   ├── general.csv
    │       │   └── specific.csv
    │       ├── GLM
    │       │   └── GLM.csv
    │       ├── GLM-130b
    │       │   ├── general.csv
    │       │   └── specific.csv
    │       ├── GPT-3
    │       │   ├── general.csv
    │       │   └── specific.csv
    │       ├── PLATO-XL
    │       │   ├── general.csv
    │       │   └── specific.csv
    │       └── Xiaomu
    │           └── Xiaomu.csv
    ├── intention_classification
    │   └── intention_classification.xlsx
    └── question_answering
        └── question_answering.xlsx

38 directories, 49 files
```

# General dialogue quality statistic

We conducted general dialogue test on 10 models, most of the tests include:

- **general test** with 420 fixed questions on 20 courses where there is a course called "英语听说读写 (English listening, speaking, reading and writing)" has an alias course, so it has 40 questions while other courses have 20 question each.
- **specific test** is conducted by free, unconstrained interaction between the bot and the annotator, each  course has at least 30 turns of interaction dialogue.
- Each turn of dialogue is **labeled twice** by annotators.

Due to the development history conflicts, time cost and resource limit, some models have only one part of dialogue test or labeled once.

| models    | general_test (420) | specific_test | labeled_twice | question_numbers |
| --------- | ------------------ | ------------- | ------------- | ---------------- |
| Xiaomu    | ❌                  | ⭕️             | ❌             | 2298             |
| GLM       | ❌                  | ⭕️             | ⭕️             | 1289             |
| CPM2      | ❌                  | ⭕️             | ⭕️             | 2576             |
| CDial-GPT | ⭕️                  | ⭕️             | ⭕️             | 420+660          |
| EVA       | ⭕️                  | ⭕️             | ⭕️             | 420+604          |
| GLM-130b  | ⭕️                  | ⭕️             | ⭕️             | 420+749          |
| PLATO-XL  | ⭕️                  | ⭕️             | ⭕️             | 420+800          |
| GPT-3     | ⭕️                  | ⭕️             | ⭕️             | 420+736          |
| CoT-10b   | ⭕️                  | ⭕️             | ⭕️             | 420+905          |
| CoT-130b  | ⭕️                  | ❌             | ⭕️             | 420              |

