University: [ITMO University](https://itmo.ru/ru/)  
Faculty: [FICT](https://fict.itmo.ru)  
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)  
Year: 2022/2023  
Group: K4110c  
Author: Orudzhev Eldar Eldarovich  
Lab: Lab1  
Date of create: 03.11.2022  
Date of finished: 10.11.2022  

# Ход работы
1) Установка  

Сперва мы скачали minikube с официального сайта, установили и запустили. При первом запуске была странная ошибка, что 
время подключения истекло и просили проверить фаервол, но после перезагрузки компьютера всё заработало.  
 ![scr1.png](Screenshots/scr1.png)

2) Манифест

Далее мы создали манифест для пода и заэплаили его в kubernetes. 
```yaml
apiVersion: v1
kind: Pod
metadata:
  name: vault-pod
  labels:
    app: vault-pod
spec:
  containers:
    - name: vault
      image: vault:latest
      ports:
        - containerPort: 8200
```
Также командой мы проверили, что под был создан.  
![scr2.png](Screenshots/scr2.png)

3) Сервис и запуск

Теперь мы создадим сервис.    
![scr3.png](Screenshots/scr3.png)  

Получим доступ к Vault.    
![scr4.png](Screenshots/scr4.png)  

На данный момент имеет текущую картину.  
![scr5.png](Screenshots/scr5.png)  

4) Нахождение токена

Чтобы найти токен откроем второй терминал и там введем команду для логов.    
![scr6.png](Screenshots/scr6.png)  

Введем появившийся токен.    
![scr7.png](Screenshots/scr7.png)  

Как мы видим, мы смогли успешно зайти. Лабораторная работа выполнена.  

5) Схема  

![scheme.png](Screenshots/scheme.png)  
