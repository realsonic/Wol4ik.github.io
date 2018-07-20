# Пазделы и параграфы

Вы можете форматировать текст с помощью Markdown, а также использовать HTML.

Чтобы создать интерактивные истории, вам нужно добавить некоторые ссылки. Есть два типа текстовых блоков, которые вы можете использовать в Squiffy:

(**Sections**) Разделы являются основными единицами текста.
(**Passages**) Проходы - это меньшие единицы, которые существуют внутри секций.

Взятие игрока в новый раздел приведет к **деактивации всех предыдущих ссылок**, поэтому используйте новый раздел, когда игрок предпринял некоторые действия, чтобы переместить историю вперед.

## Разделы (**Sections**)

Названия разделов должны быть уникальными в истории. Настройте раздел, используя двойные квадратные скобки, а затем двоеточие. Для ссылки на раздел используйте двойные квадратные скобки.
```
Do you want to have the [[roast chicken]] or skip straight to [[dessert]]?
    
[[roast chicken]]:
This plate of roast chicken looks delicious.

[[dessert]]:
Three different flavours of ice cream - yum!
```

## Проходы (**Passages**)

Настройте проход, используя одиночные квадратные скобки, а затем двоеточие. Проходы могут соединяться с дальнейшими проходами. После того, как игрок нажимает ссылку на проход, эта ссылка отключается, поэтому игрок может только щелкнуть ее один раз. Для ссылки на проход используйте одиночные квадратные скобки.
```
Looking around the room, you can see a [TV], a [book] and a piece of [paper] with some handwriting scribbled on it.

[TV]:
Covered in dust and the plug is missing.

[book]:
It's a book of magic tricks. Maybe you should [open] it?

[open]:
The cover opens up to reveal the pages all glued together, with an empty key-shaped hole cut out.

[paper]:
"Gone out for a walk. May be a while."
```
# Очистка экрана

Перед появлением любого раздела или прохода можно очистить экран, используя _@clear_ **на отдельной строке**:
```
[[Chapter 2]]:
@clear
My first reaction to the explosion was...
```

# Поверните счетчик

Вы можете вызвать проход после того, как игрок совершил определенное количество кликов в секции. Например, вы можете отобразить дополнительный текст, чтобы указать время прохождения. Или в проходе может быть запущен некоторый JavaScript для автоматического перемещения игрока в другой раздел.

В приведенном ниже примере текст «Мы почти здесь. Поезд тянет в платформу ». Всегда записывается после первого щелчка. После второго прохода нажмите, мы переместимся в следующий раздел.
```
On the train you can see a [girl singing], a [man reading a book] and an [old woman].

[girl singing]:
She is nodding her head to the music in her enormous earphones, and singing badly out of tune.

[man reading a book]:
He's been reading the same page of *War and Peace* for a while now.

[old woman]:
She eyes you suspiciously, as if she has seen your type before.

[@1]:
We're nearly here. The train is pulling into the platform.

[@2]:

    squiffy.story.go("station");

[[station]]:
We have now arrived at the station.
```