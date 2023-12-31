# Агент интерпретации неатомарных действий

Данный агент генерирует спецификацию неатомарного действия в базе знаний на основе полученного шаблона. Если передано множество аргументов, то они подставляются как аргументы неатомарного действия под соответствующими ролями.

**Класс действий:**

`action_interpret_non_atomic_action`

**Параметры:**

1. `nonAtomicActionTemplateAddr` -- шаблон, содержащий описание неатомарного действия;
2. **(необязательно)** `argumentsSet` -- множество аргументов действия.

**Комментарий:**

* Если нет необходимости в `set of arguments`, то допускается пустой `set of arguments` или отсутствие такового набора;
* Переход к следующему действию зависит от результата предыдущего.

**Ход работы агента:**

* Первый аргумент неатомарного действия заменяется узлом, который принадлежит набору аргументов в качестве первого, второй аргумент неатомного действия заменяется узлом, принадлежащим набору в качестве второго;
* В ходе работы агента генерируется шаблон программы описание неатомарного действия. Составляющие его атомарные действия также добавляются к классу выполненных (успешно или неуспешно) агентами, которые их выполнили. Пример интерпретируемой программы агентом приведен ниже:

<img src="../images/nonAtomicActionInterpretationAgentExample.png"></img>

### Пример

Пример входной структуры:

<img src="../images/nonAtomicActionInterpretationAgentInput.png"></img>

Пример выходной структуры:

<img src="../images/nonAtomicActionInterpretationAgentOutput.png"></img>

### Результат

Возможные результаты:
 
* `SC_RESULT_OK` - ответное сообщение сгенерировано;
* `SC_RESULT_ERROR`- внутренняя ошибка.
