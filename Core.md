## Object

1.Почему все наследуется от него? 
Нужно подумать про наследование
Чтобы определенный пул методов стандартных был у всех объектов, объект наследника может быть использован где нужно объект родителя

2.Для чего можно создать экземпляр обжекта? 

Например для монитора многопоточность


3. Методы класса 
hashCode(), equals(), ToString

Wait(), notify(), notifyall() - вызываются только внутри synchronize блока, используются для синхронизации, wait останавливает поток, notify пробуждает один поток notifyall пробуждает все потоки на мониторе.

getClass

Clone(), finalize()

## Сериализация

Сериализация — это процесс, который переводит объект в последовательность байтов, по которой затем его можно полностью восстановить.При сериализации объекта сериализуются все объекты, на которые он ссылается в своих переменных экземпляра. 
Десериализация — это процесс восстановления объекта из этих байт.
Дополнительным бонусом ко всему является сохранение кроссплатформенности. 
Реализовать механизм сериализации довольно просто. Необходимо, чтобы ваш класс реализовывал интерфейс Serializable. Это интерфейс — идентификатор, который не имеет методов, но он указывает jvm, что объекты этого класса могут быть сериализованы. 

Что делать, если вы хотите управлять сериализацией сами? Существует два способа. Первый, использовать ключевое слово transient ( не дает полю сериализоваться). Второй, вместо реализации интереса Serializable использовать его расширение — интерфейс Externalizable.