# Домашнее задание к занятию "`Кластеризация и балансировка нагрузки`" - `Кудряшов Андрей`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

Конфиг-файл Haproxy:
[haproxy.cfg](https://drive.google.com/file/d/109R_8VDtnbaGJosVZrST9aC9OkovyRD3/view?usp=sharing)

http-get
<img width="948" height="356" alt="1" src="https://github.com/user-attachments/assets/0528cf75-c170-4231-9adc-68438648ca0f" />

tcp-get
<img width="953" height="332" alt="2" src="https://github.com/user-attachments/assets/21965181-49d1-4615-94bf-9fa1004c0169" />



---

### Задание 2

[haproxy2.cfg](https://drive.google.com/file/d/1V_fjtdAQNPKt5nSnuldj91RzuKFIItY2/view?usp=sharing)

Скрипт проверки для example-http.com:
```
#!/bin/bash

declare -A count
count["Server 1 :8888"]=0
count["Server 2 :9999"]=0
count["Server 3 :7777"]=0

for i in $(seq 1 100); do
    output=$(curl -s -H 'Host: example-http.com' http://localhost:8088)
    if [[ "$output" == "Server 1 :8888" ]]; then
        count["Server 1 :8888"]=$(( ${count["Server 1 :8888"]} + 1 ))
    elif [[ "$output" == "Server 2 :9999" ]]; then
        count["Server 2 :9999"]=$(( ${count["Server 2 :9999"]} + 1 ))
    elif [[ "$output" == "Server 3 :7777" ]]; then
        count["Server 3 :7777"]=$(( ${count["Server 3 :7777"]} + 1 ))
    fi
done

echo "Results:"
for server in "${!count[@]}"; do
    echo "$server: ${count[$server]} times"
done
```

<img width="949" height="369" alt="3" src="https://github.com/user-attachments/assets/1474013a-6f80-4a10-bb52-42471dc78223" />


Скрипт проверки для http://localhost:8088
```
#!/bin/bash

declare -A count
count["Server 1 :8888"]=0
count["Server 2 :9999"]=0
count["Server 3 :7777"]=0

for i in $(seq 1 100); do
    output=$(curl -s http://localhost:8088)
    if [[ "$output" == "Server 1 :8888" ]]; then
        count["Server 1 :8888"]=$(( ${count["Server 1 :8888"]} + 1 ))
    elif [[ "$output" == "Server 2 :9999" ]]; then
        count["Server 2 :9999"]=$(( ${count["Server 2 :9999"]} + 1 ))
    elif [[ "$output" == "Server 3 :7777" ]]; then
        count["Server 3 :7777"]=$(( ${count["Server 3 :7777"]} + 1 ))
    fi
done

echo "Results:"
for server in "${!count[@]}"; do
    echo "$server: ${count[$server]} times"
done

```

<img width="954" height="518" alt="4" src="https://github.com/user-attachments/assets/9c7ffa1b-0c56-4530-87d7-3ed490b5aad9" />



---

### Задание 3

`Приведите ответ в свободной форме........`

1. `Заполните здесь этапы выполнения, если требуется ....`
2. `Заполните здесь этапы выполнения, если требуется ....`
3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`

### Задание 4

`Приведите ответ в свободной форме........`

1. `Заполните здесь этапы выполнения, если требуется ....`
2. `Заполните здесь этапы выполнения, если требуется ....`
3. `Заполните здесь этапы выполнения, если требуется ....`
4. `Заполните здесь этапы выполнения, если требуется ....`
5. `Заполните здесь этапы выполнения, если требуется ....`
6. 

```
Поле для вставки кода...
....
....
....
....
```

`При необходимости прикрепитe сюда скриншоты
![Название скриншота](ссылка на скриншот)`
