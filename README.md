**Author:** Зернов В. **Spec ID:** 1  Priority: 1 **Producer:** ? **Developer:** Беликова А.

## OVERVIEW:
Данный тест проверяет модель процесса исходящего документа.

## GLOBAL SETUP and ADDITIONAL INFO:

- SQL Запрос в БД bpm, с помощью которого можно увидеть историю процесса, использовав соответствующий primarykey:
```
select t.primarykey as pk_zadachi,t.workflowinstance,t.createdate, t.name,t.resulttext,t.comment,t.state, a.login ,a.name, a.agentpk from taskexecutor te
     join task t on te.task=t.primarykey
     join actor a on a.primarykey=te.currentactor
     join workflowinstance wi on wi.primarykey=t.workflowinstance
	where t.workflowinstance = '{primarykey}'
                 order by t.createdate desc
```
- Историю процесса можно так же посмотреть здесь, вставив в ссылку primarykey из запроса выше:
```
http://dms.zspk.perm.ru/#/history/{primarykey}
```


## Automated Testing of the Process Model 0001
**IDEA:** Процесс завершается без ошибок с печатью, сканированием, индексом, архивированием 
## SETUP and ADDITIONAL INFO:
**Инициатор:** zspk\testuser24

**Вид документа:**	Письмо

**Группа документа:**	Запрос автора

**Оргструктура:**	Структура Аппарата

**Тематика документа:**	Тематика не определена

**Утверждающий:**	zspk\testuser02

**Разработать самому:**	true

**Исполнители подготовки:** 	(0)

**Способ отправки:**	Электронная почта

**Делопроизводитель:**	zspk\testuser11

**Собственноручная подпись:**	true

**Ответственный за печать:**	ЯTestUser09

**Сканирование:**	true

**Ответственный за сканирование:**	ЯTestUser08

**Индекс дела:**	true

**Архивирование:**	true
## Execution part

1. Рассмотрите проект исходящего документа. 
>**Confirm** 
>>Задача завершена. Назначена следующая задача

2. Отсканируйте документ. 
>**Confirm** 
>>Задача завершена. Назначена следующая задача

>3. Разместите в архив оригинал исходящего документа и отправьте документ получателю. 
>>**Confirm** 
>>Задача завершена. Назначена следующая задача

>4. Утвердите проект исходящего документа. 
>>**Confirm** 
>>>Задача завершена. Назначена следующая задача

>5. Пожалуйста, распечатайте документ и обеспечьте подписание бумажного варианта документа 
>>**Confirm** 
>>>Задача завершена. Назначена следующая задача

>6. Документ отправлен получателю. 
>>**Confirm** 
>>>Задача завершена. Назначена следующая задача






























