# urban_19 Практическая работа по модулю 19 Фреймворк Vue. Js 1.1

Создайте простое одностраничное приложение «Список дел» (ToDo List), которое позволит пользователю добавлять и удалять задачи.

**Требования:**
* Инициализируйте новый Vue-проект с помощью CDN или Vue CLI (по желанию).
* Создайте основной экземпляр Vue и подключите его к элементу в HTML.
* Создайте два компонента:
  + **TodoItem:** представляет отдельную задачу.
  + **TodoList:** отображает список задач и содержит форму для добавления новых задач.
* Компонент **TodoItem** должен принимать через props текст задачи и её уникальный идентификатор.
* Реализуйте двустороннюю привязку для поля ввода новой задачи, чтобы отслеживать текущее значение ввода.
* В компоненте **TodoList** используйте v-for для отображения списка задач, проходя по массиву задач.
* При отправке формы добавляйте новую задачу в список.
* Реализуйте возможность удаления задачи при нажатии на кнопку «Удалить» рядом с каждой задачей.
* Используйте **$emit** для передачи событий от дочерних компонентов к родительским (например, при удалении задачи).
* Добавьте стилизацию с помощью CSS для улучшения внешнего вида приложения.
* Реализуйте возможность помечать задачи как выполненные (например, изменяя стиль текста на зачёркнутый).
**Подсказки:**
1. Используйте массив объектов для хранения задач, где каждый объект имеет свойства id, text и, возможно, completed.
2. Для генерации уникальных идентификаторов можно использовать текущее время или счётчик.
3. Помните о добавлении атрибута :key при использовании v-for.
