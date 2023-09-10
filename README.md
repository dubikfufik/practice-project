# Использование Git и GitHub
Мы пропустим список команд терминала, если вы их еще не знаете изучите их, а потом возвращайтесь сюда.

## Git
1. Инициализация git в репозитории. -> git init
2. Проверить статус. -> git status
3. Подготовить файл к сохранениюю -> git add 'имя файла'
  
     + Подготовить все файлы к сохранению -> git add --all
     + Подготовить всю папку к сохранению -> git add . 

4. Сохранить файл. -> git commit 'имя файла' -m 'описание изменения'
5. Просмотреть история комитов. -> git log

## GitHub
**GitHub** - платформа позволяющая работать в команде над одним проектом.
Мы пропустим часть регистрации на GitHub если вы это читаете - значит вы уже зарегестрированы))
Охватим лишь часть, создания репозитория.
1. Зайдете на свой профиль на GitHub
2. Перейдете на страницу **Repositories** и создайте новый репозиторий, настраивать его приватным или публичным это уже ваше дело.
3. Синхронизация удаленного репозитория на GitHub и локального - на вашем компьютере:
  
     + Генерация ssh ключей -> $ ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"  
     + Или $ ssh-keygen -t rsa -b 4096 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"   
     + Далее указываем место хранения ключей, можно просто прожать Enter, тем самым создав домашний каталог  
     + Настройка пароля (по желанию, если хотите добавить второй слой защиты ваших ключей)  
     + Копируем содержимое ключа в буфер обмена в зависимости от пути генериации:
     ###### MacOs
     Для id_rsa: pbcopy < ~/.ssh/id_rsa.pub  
     Для ed25519: pbcopy < ~/.ssh/id_ed25519.pub  
     ###### Windows
     Для id_rsa: clip < ~/.ssh/id_rsa.pub  
     Для ed25519: clip < ~/.ssh/id_ed25519.pub  



     + Перейдите на GitHub и выберите пункт **Settingsв** меню аккаунта  
     + В меню слева нажмите на пункт **SSH and GPG keys**  
     + В открывшейся вкладке выберите **New SSH key**  
     + В поле **Title** напишите название ключа  
     + В поле **Key type** должно быть **Authentication Key**  
     + В поле **Key** скопируйте ваш ключ из буфера обмена  
     + Нажмите на кнопку **Add SSH key**  
     + Проверьте правильность ключа с помощью следующей команды : $ ssh -T git@github.com. Если это первый раз когда вы работаете с Git вы можете проверить ваш ключ по [ссылке](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints). Введите yes, если все получилось  



     + Перейдите на страницу удалённого репозитория, выберите тип SSH и скопируйте URL. Кнопка справа позволит сделать это мгновенно  
     + Вернитесь в терминал, откройте свой репозиторий и введите команду $ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git  
     + Чтобы убедиться что ключи связанны введите команду $ git remote -v. Если вы увидели строки  
         origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (fetch)  
         origin    git@github.com:%ИМЯ_АККАУНТА%/%ИМЯ-ПРОЕКТА%.git (push)  
       Значит все хорошо, и локальный и удаленный репозитории связаны  
     + Чтобы отправить изменения на удаленный репозиторий введите команду $ git push -u origin main. Далее можно не использовать флаг -u. Далее вы можете посмотреть изменения в своем репозитории на GitHub  

---

#Хеширование  
**Хеш** - идентификатор коммита  
**Хеширование** - способ преобразовать набор данных и получить их отпечаток.  
С помощью хеша можно получить всю информацию о коммите - когда был сделан и кем.  
Вся хеш таблица храниться в файле .git. 

---

#Log  
## Элементы описания коммита  

+ строка из цифр и латинских букв после слова commit - хеш коммита.  
+ Author — имя автора и его электронная почта.  
+ Date — дата и время создания коммита.  
+ в конце находится сообщение коммита.  

Получить сокращенный лог можно при помощи команды **git log --oneline**.
























