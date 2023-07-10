Описание:
	Этот проект из себя представляет обертку, написанную на языке С++ вокруг графической библиотеки FreeImage написанной на С.


Почему FreeImage:
	Изначально предлагалось использовать библиотеку ImageMagick, а именно ImageMagick Wand, но в ходе установки выше указанной библиотеки возникла следующие проблемы. Библиотека устанавливала себя не пойми куда, причем при ее установке отсутствовали ее внутренние декодеры и как следствие не удавалась работать с такими распространенными форматами как JPEG, PNG и так далее. Второй проблемой оказалась компиляция. Было совершено множество попыток исправить эту проблему,  но так и не получилось заставить компилятор корректно работать с этой библиотекой.
	FreeImage таких проблем не имеет, при установке появляется один хедер, который прекрасно компилируется и работает.
      

Как скомпилировать проект (вручную):
	g++ -o start.out iApcFreeImageGraphicsHelper.cpp iApcTest.cpp iApcUserCode.cpp -lfreeimage


Структура проекта:
	Исходный проект представляет из себя шесть файлов:
                 iApcFreeImageGraphicsHelper.cpp (реализация функций)
                 iApcFreeImageGraphicsHelper.h (заголовки функций для пользователя)
                 iApcFreeImageGraphicsHelperInternalCode.h (заголовки функций скрытых от пользователя)
                 iApcTest.cpp (реализация тестовых функций)
                 iApcTest.h (заголовки тестовых функций)
                 iApcUserCode.cpp (код "пользователя", который использует нашу обертку)


Дополнительные файлы проекта:
	Дополнительно к проекту прилагаются изображения трех форматов (их название НЕ МЕНЯТЬ!), они нужны для имитации работы с памятью. Чтобы протестировать нашу библиотеку, нужно загрузить все эти изображения в память, это делается автоматически. После загрузки происходит следующие, в функцию передается вектор и обратно пользователь получает тоже вектор ).


Недостатки:
	На данный момент реализованы не все функции и обертка не работает с файлами типа ICO.
