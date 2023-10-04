# Контекст решения
<!-- Окружение системы (роли, участники, внешние системы) и связи системы с ним. Диаграмма контекста C4 и текстовое описание. 
-->
```plantuml
@startuml
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml

AddElementTag("microService", $shape=EightSidedShape(), $bgColor="CornflowerBlue", $fontColor="white", $legendText="microservice")
AddElementTag("storage", $shape=RoundedBoxShape(), $bgColor="lightSkyBlue", $fontColor="white")

Person(admin, "Администратор")
Person(user, "Пользователь")

System(conference_site, "Магазин", "Сайт для поиска и добавления товаров в корзину")



Rel(admin, conference_site, "Создание нового пользователя, поиск пользователя по логину, поиск пользователя по маске имя и фамилии, Создание товара")
Rel(user, conference_site, "Получение списка товаров, добавление товара в корзину, получение корзины для пользователя")



@enduml
```
## Назначение систем
|Система| Описание|
|-------|---------|
| Магазин | Веб-интерфейс, обеспечивающий доступ к просмотру и добавлению в корзину товаров. Бэкенд сервиса реализован в виде микросервисной архитектуры |

