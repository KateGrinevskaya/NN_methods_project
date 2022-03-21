# NN_methods_project
#### Term Defenition Extraction project for HSE Neural Networks Methods course

Презентация к `29.01.2022` есть в файлах, а вот [ссылка](https://docs.google.com/presentation/d/1jZjVo1a3vtCak-OyGlwKWzhlrksOpSqK_kHQAAJFA5Y/edit?usp=sharing).
Ссылка на [Trello](https://trello.com/b/lrAiG4q9/term-extraction).

## Цель: выделение терминов с определениями из предложений.

## Данные:

Предложения из 300 статей из Википедии по теме "Лингвистика". Сохранены в таблицах:

sents_Wiki_tagged.csv (table1)

tokens_Wiki_tagged.csv (table2)

## Тетрадки с кодом:

- **get_wikidata.ipynb**

Тетрадка скачивает статьи из Википедии по теме "Лингвистика" и создаёт таблицу sent_def. Столбцы: sent_index, текст предложения, наличие определения. У первых предложений из статей has_def = 1, у остальных has_def = 0. sent_def.csv требует ручной проверки.

- **baseline_rules_table1.ipynb**

Тетрадка с помощью правил элементарным образом размечает, есть ли определение в предложении или нет. accuracy = 0.85

- **baseline_rules_table2table1.ipynb**

Этот код из столбца с текстом предложений создаёт таблицу со столбцами: sent_index,	token,	tag. Токены каждого передложения с определением размечаются тегами B-TERM, I-TERM, B-DEF, I-DEF O. Если определение не найдено, у всех слов тег O. А has_def для предложения = 0. accuracy(классификации) = 0.86, accuracy(всего) = 0.769 Можно использовать этот код для первоначальной BIO разметки, которую после ручной выверки можно давать нейросети.

- **bert(+fine_tuned)_crf_wo_embed.ipynb**

Недообученный BERT с CRF по признакам, дообученный BERT с CRF по признакам

- **fine_tuned_bert_crf_w_emb.ipynb**

Дообученный BERT с лучшей опробованной моделью с CRF по признакам и с весами от BERT

table1 (sent_def.csv)
| sent_index	| text_sent |	has_def
| - | - | - 
| 1	| текст предложения без определения	| 0
| 2	| текст предложения с определением	| 1


table2
| id	| sent_index	|	token	| tag
| - | - | - | -
| 1	| 1	| слово1	| B-TERM
| 2	| 1	| слово2	| O
| 3	| 1	| слово3	| B-DEF
| 4	| 1	| слово4	| I-DEF
