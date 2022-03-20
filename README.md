# NN_methods_project
#### Term Defenition Extraction project for HSE Neural Networks Methods course

Презентация к `29.01.2022` есть в файлах, а вот [ссылка](https://docs.google.com/presentation/d/1jZjVo1a3vtCak-OyGlwKWzhlrksOpSqK_kHQAAJFA5Y/edit?usp=sharing).
Ссылка на [Trello](https://trello.com/b/lrAiG4q9/term-extraction).

Цель: выделение терминов с определениями из предложений.

Тетрадки с кодом:

- get_wikidata.ipynb: тетрадка скачивает статьи из Википедии по теме "Лингвистика" и создаёт таблицу sent_def. Столбцы: текст предложения, наличие определения. У первых предложений из статей has_def = 1, у остальных has_def = 0. sent_def.csv требует ручной проверки.
- baseline_rules_table1.ipynb: тетрадка с помощью правил элементарным образом размечает, есть ли определение в предложении или нет. accuracy = 0.85
- baseline_rules_table2table1.ipynb: Этот код из столбца с текстом предложений создаёт таблицу со столбцами: sent_index	token	tag. Токены каждого передложения с определением размечаются тегами B-TERM, I-TERM, B-DEF, I-DEF O. Если определение не найдено, у всех слов тег O. А has_def для предложения = 0. accuracy(классификации) = 0.86, accuracy(всего) = 0.769 Можно использовать этот код для первоначальной BIO разметки, которую после ручной выверки можно давать нейросети. 

id	| sent_index	|	token	| tag
- | - | - | - 
1	| 1	| слово1	| B-TERM
- | - | - | - 
2	| 1	| слово2	| O
- | - | - | - 
3	| 1	| слово3	| B-DEF
- | - | - | - 
4	| 1	| слово4	| I-DEF
