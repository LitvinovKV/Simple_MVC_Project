# Simple_MVC_Project
My attempt to create simple MVC project on PHP without any frameworks.  

core/route.php - класс, который запускает методы контроллеров. Изначально будет вызываться controller = Main, action = inex  
Если в строке URL был введен какой-то маршрут, то он разбивается при помощи метода explode(), и уже вызывается контроллер и экшн исходя из URL. Например : localhost/Article/Show. Будет создан экземпляр контроллер = Article и вызван метод Show.  

core/controller.php - базовый класс для контроллеров. (состоит из атрибутов: model, view - экземпляр класса View для представления шаблона)
core/view.php - базовый класс для представлений. (состоит из метода generate() - подключает определенный шаблон и общий шаблон проекта)  
core/model.php - базовый класс для моделей. (состоит из метода getdata() - метод для выборки данных)  
  
controller_main.php - дочерний класс класса Controller. Содержит переопределенный метод action_index(), который подключает шаблон начального представления.  

controller_404.php - дочерний класс класса Controller.

controller_contacts.php, controller_portfolio.php  - дочерние классы класса Controller. Содержит метод action_index(), который подключает шаблон представления и преедает определенные параметры в качестве аргумента функции $data.

model_contacts.php, model_portfolio.php - дочерние классы класса Model. Переопределяют метод getData(), которые возвращает массив с данными для определенного представления.

404_view.php, contacts_view.php, portfolio_view.php - представление в которых используются переданный параметр $data из функций контроллеров.