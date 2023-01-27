## Создали, удалили ветку в удалённом репозитории - что делать дальше? ##

А дальше необходимо синхронизировать состояние **удалённого** репозитория с **локальным**!

Для этого используем команду 
                                          **git fetch**

Из [документации Git](https://git-scm.com/docs/git-fetch):
> **git-fetch** - загрузка объектов и ссылок из другого репозитория

:white_check_mark: При выполнении **git fetch** с удалённого репозитория в ваш локальный реп
выкачиваются все имеющиеся в удалённом репозитории коммиты, которых у вас пока нет,
а также все ветки.

:white_check_mark: Локально создаются специальные ветки, которые ***повторяют содержание***
удалённых веток. Эти ветки имеют формат имени <имя удалённого репозитория>/<имя ветки>, например origin/master.

**Как понять:** произошло ли что-то хорошее и что делать дальше?
Ведь новые ветки **по-прежнему не отображаются** :interrobang:

**Ответ:** если Git никак не возмутился и не написал сообщение типа "что-то пошло не так",
а вы просто перешли в другую строку - значит всё случилось! 🌟 стыковка прошла успешно 🚀

Дело в том, что в локальном репозитории немного по-другому всё это отображается.

Если просмотреть ветки, как обычно, с помощью команды **git branch** или её синонима **git branch --list**,
отобразятся только те, которые были созданы в данном, т.е. *локальном*  репозитории.
А нам нужно посмотреть **все**, для этого используем команду 
                                    **git branch -a**.

Будет отображено как на скрине
[![image.png](https://i.postimg.cc/BvGSMD6j/image.png)](https://postimg.cc/75mrL5S4)

:white_check_mark: При этом можно уже переключиться на новую ветку обычной командой **git checkout название-ветки** 👏
