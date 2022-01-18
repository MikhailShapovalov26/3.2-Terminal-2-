Домашняя работа к занятию "3.2. Работа в терминале, лекция 2"
============================
1.
        type cd
        cd — это встроенная команда bash
При использовании ОС Linux нужно использовать оболочку-интерфейс, который даёт нам доступ к службам операционной системы. И команда cd является связывающей командой, которая помогает перемещаться пользователю по рабочим каталогом и напрямую работать с системой. 

2. 
         wc -l #Вывести кол-во строк в объекте

К примеру, команда ниже выведет список файлов, которые не содержат текста. 

         $ grep -IRiL "somestring" 
        .git/info/exclude
        .git/HEAD
        .git/index
        .git/config
        .git/hooks/pre-applypatch.sample
        .git/hooks/pre-commit.sample


3. 

        $ ps aux

Первый в списке был процесс


    root 1  0.0  0.0 164156 10580 ?        Ss   19:59   0:01 /sbin/init

4. 
        ls >/dev/pts/2

5. 
         ls >/dev/pts/2 2>&1
6. 
        ls /dev |grep tt
Выбираем необходимый из списка

        $ echo "tty" >/dev/tty10

7.
        bash 5>&1
Привело к тому, что я потерял историю всех командых вводимых в данном терминале, теперь мне доступны команды из стории только из другого терминала. 
        
        echo netology > /proc/$$/fd/5 
        netology

8.  
               ls 5>&2 2>&1 1>&5
Что-то вроде такого? Я честно не особо понял задание. Можно скинуть материал по данному моменту. 
9. 
Вывод:
                SHELL=/bin/bashSESSION_MANAGER=.....

Для вывода аналогичной информации попдойдет команда env (вывод значительно удобнее для чтения)

10. 
        /proc/[pid]/cmdline
              This read-only file holds the complete command line for the process, unless the
              process is a zombie.  In the latter case, there is nothing in this  file:  that
              is,  a  read on this file will return 0 characters.  The command-line arguments
              appear in this file as a set of strings separated by null bytes ('\0'), with  a
              further null byte after the last string.

PID это индефикатор процесса, соответвественно файл содержит полную командную строку запуска процесса, если только процесс не зомби и не ушёл в своппинг. В этом случае в файле ничего нет, то есть при чтение данного файла будет 0
                
        /proc/[pid]/exe

              Under Linux 2.2 and later, this file is a symbolic link containing  the  actual
              pathname  of the executed command. 
exe является символьной ссылкой, содержащей фактическое полное имя выполняемого файла.

11. sse4_2

12. 
Для запуска можно использовать аргумент -t, и команда будет запущена принудительно.

13.

                reptyr -L 4549 
                Opened a new pty: /dev/pts/4

14. Команда tee в Linux нужна для записи вывода любой команды в один или несколько файлов. Используя команду tee с разными опциями, можно сохранить вывод команды в нескольких файлах.
                echo string | sudo tee /root/new_file
                string
                cat /root/new_file 
                string

Из листинга понятно, что даннная команда сделала вывод в консоль и сделала вывод в файл new_file. 

