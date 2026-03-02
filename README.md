## Решение 1

### 1. Изучил проект. Заполнил токен, ID облака и ID папки пользователя в personal.auto.tfvars
### 2. Инициализировал проект и выполнил код.

Создалась сеть и подсеть с именем Develop и группа безопасности с именем example_dynamic и правилами трафика:

<img width="535" height="434" alt="image" src="https://github.com/user-attachments/assets/32244fcc-febf-4c61-ae71-b496425250e8" />

## Решение 2

### 1. Создал файл count-vm.tf и описал в нем 2 одинаковые виртуальные машины, которые будут называться web-1 и web-2:

<img width="391" height="175" alt="image" src="https://github.com/user-attachments/assets/fd2df46b-97f8-4fcb-8f19-6baa2b1ef3b9" />

Назначил виртуальной машине созданную в первом задании группу безопасности:

<img width="353" height="128" alt="image" src="https://github.com/user-attachments/assets/5d644ee9-ea7b-4b40-afab-0daa2fd762da" />

### 2. Создал файл for_each-vm.tf. В нем описал создание двух ВМ с именами "main" и "replica" разных по cpu/ram/disk , используя мета-аргумент for_each loop:

<img width="398" height="761" alt="image" src="https://github.com/user-attachments/assets/d5e12527-d4b1-46f1-b3e4-ae53952fa382" />

### 3. ВМ с именами "main" и "replica" создаются после создания ВМ web-1 и web-2:

<img width="373" height="84" alt="image" src="https://github.com/user-attachments/assets/d1f43c63-f0d3-4249-99f8-46429a8b5a78" />

### 4. Для считывания файла ключа использую local-переменную и использую ее в блоке metadata:

<img width="360" height="85" alt="image" src="https://github.com/user-attachments/assets/2de10bcc-11b2-4a35-97c3-d6bf817988ee" />

<img width="360" height="92" alt="image" src="https://github.com/user-attachments/assets/44a9321b-04e8-4215-a179-d9ff2f6d6bb0" />

### 5. Инициализировал проект, выполнил код. Создалось 7 объектов - сеть, подсеть, группа безопасности и 4 виртуальные машины:

<img width="799" height="196" alt="image" src="https://github.com/user-attachments/assets/6dcae664-30a9-476d-854a-03205856f4aa" />

## Решение 3

### 1. Создал 3 одинаковых диска:

<img width="392" height="167" alt="image" src="https://github.com/user-attachments/assets/3206e5eb-b5b2-4f75-a6da-e6e49766e553" />

### 2. Создал виртуальную машину storage и используя мета-аргумент for_each подключил к ней созданные диски:

<img width="565" height="757" alt="image" src="https://github.com/user-attachments/assets/e906f89f-4869-4944-acb3-f4f51f692822" />

## Решение 4

### 1. Создал файл ansible.tf, по примеру из лекции написал код с использованием функции tepmplatefile:

<img width="455" height="179" alt="image" src="https://github.com/user-attachments/assets/72a83a2a-ecc8-4aa6-b618-af67cc481455" />

Шаблон инвентари файла использовал также из лекции.

### 2. Инвентари файл получился с 3 группами.

### 3. Скриншот результата:

<img width="331" height="297" alt="image" src="https://github.com/user-attachments/assets/921da82f-60b7-4271-b26f-3d0151939638" />








