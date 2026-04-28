<h1>Массовое добавление сотрудников в домен Active Directory.</h1>


Чтобы воспользоваться программой достаточно перейти на [сайт](https://denis-linux.github.io/ADD-Users-ActiveDirectory/) - https://denis-linux.github.io/ADD-Users-ActiveDirectory/

Инструкция:
1. Вносим данные вашего домена Aсtive Directory "A3f.local", "BB.ru" и т.п.
   
![image](https://github.com/tkachukds/AD-User-Importer/assets/103854079/7bb8846d-ed2c-4443-9816-72da9c665969)

![image](https://github.com/tkachukds/AD-User-Importer/assets/103854079/e39d6f10-4845-43b5-bdc9-c24e56c1c3c7)



2. Можно изменить стандартный пароль от всех пользователей.

 ВНИМАНИЕ: Как только пользователь войдет, он будет обязан сменить пароль. Поэтому ставить сложный пароль не имеет смысла.

![image](https://github.com/tkachukds/AD-User-Importer/assets/103854079/c11198d6-5516-4fad-9507-75fb57bd0175)


 3. Вносим путь до папки куда создать пользователей.

ВНИМАНИЕ:Автоматически будет создан путь OU.
Менять ничего не нужно.    
![image](https://github.com/tkachukds/AD-User-Importer/assets/103854079/910578f0-0e9b-4407-9abb-aa1344c9684c)

office-users/IT в AD выглядить так - 

![image](https://github.com/tkachukds/AD-User-Importer/assets/103854079/eb9b38f4-d3c7-464f-ad91-ba354dfc3aaf)


но если хотите вручную внести:
OU - это путь до папки куда нужно сохранить пользователей. Нужно вносить в обратном порядке. Например:
Путь до папки у меня такой: A3F.local/office-users/IT, значит нужно указать : OU=IT,OU=office-users,DC=A3F,DC=local. 

4. Вносим список пользователей, которых нужно добавить и нажимаем СОЗДАТЬ
   
![image](https://github.com/tkachukds/AD-User-Importer/assets/103854079/56baa55c-b1a2-41af-beae-ed1ac1a80133)


Новый пользователь - новая строка. 
Отчество указывать не обязательно. Если хотите добавить должность, после ФИО добавьте тере (-) и должность. [ФИО - должность]

Появится код (можно проверить все ли правильно) а также создается файл  addusers.ps1
![image](https://github.com/tkachukds/AD-User-Importer/assets/103854079/0f05bd5f-a317-4e2f-ac63-8c0a8f7cdc9b)
![image](https://github.com/tkachukds/AD-User-Importer/assets/103854079/999e1c4d-528d-478d-995c-1ea956aa6bb0)


Запускаем файл addusers.ps1 на Windows Server и пользователи будут автоматически созданы.


![image](https://github.com/tkachukds/AD-User-Importer/assets/103854079/b38b27f2-8594-4967-84c8-1ca137adf84e)

Если что-то пойдет не так, PowerShell об этом вам сообщит. (например: если такой пользователь уже есть)



Преимущества:
1. Программа полностью бесплатная (все аналоги платные, либо не работают)
2. Программа сама за вас сгенерирует логин пользователя по алгоритму - ТРАНСЛИТ"первая буква имени.фамилия полностью". (в аналогичных программах вы сами вносите логин в таблицу)

   
С уважением, Коновалов Денис Александрович kino-denis@mail.ru

