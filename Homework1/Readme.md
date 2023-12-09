# Homework1

> ### Убедительная просьба писать домашние задания на странице с домашним заданием! 

# я сумел сделать публичный проект в gitlab ссылка ниже.
# https://gitlab.com/test4555548/Test


> # Я обучаюсь на курсе Python разработчик, активно использую django.
> # Мне как python разработчику не понятно зачем нам нужен курс CI/CD?
> # Лекций у нас нет! Спросить интересующие нас вопросы не у кого! Семинаров у нас нет! 
> # Мы ранее никогда не сталкивались с devops, и непонятно как будут оцениваться домашние задания?
> # 21 декабря в нашей группе состоится защита диплома по программе python-разработчик, моя тема диплома "CRM Автомойка" в место того что бы готовится к диплому я изучаю актуальнось которого вызывает вопросы!
> # Прошу ответить на мои вопросы. 
> # Прошу принять эту информацию к сведенью! 
> Далее о проблемах ниже. 
> 
## Задание
1. Зарегистрироваться в gitlab
2. создать pipeline n runner
3. сохранить артефакт одной из стадий + исключить из папки с артефактами любой файл 
4. сделать любую gitlab pages

# Решение
## 1. Зарегистрироваться в gitlab
Очень интересное задание, особенно когда это задание как квест с самолетиком в gta. 
### Проблема №1
Gitlab официально не работает в России. Зарегистрироваться в нем официально нельзя!

### Проблема №2
Не возможно зарегистрироваться в gitlab. 
Зарегистрироваться получилось только на 30 дневную версию. 

### Проблема №3
Проблема актуальности полученных знаний.
Я очень сомневаюсь что крупные аккредитованные компании использую запрещенные сервисы по типу gitlab и тд.. 

### Решение
К сожалению я не смогу скинуть ссылку с выполненным домашним заданием потому что зарегистрироваться получилось только как компания и то на 30 дней. и все репозитории приватны, поэтому я пишу это все на github.

## 2. создать pipeline n runner
![Снимок экрана 2023-12-04 в 22.35.22.png](%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202023-12-04%20%D0%B2%2022.35.22.png)

![Снимок экрана 2023-12-04 в 22.35.44.png](%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202023-12-04%20%D0%B2%2022.35.44.png)

## Вопрос касательно runne, акой смысл его запускать локально ? когда можно это сделать в docker или в вебе? 
![Снимок экрана 2023-12-05 в 23.45.06.png](%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%202023-12-05%20%D0%B2%2023.45.06.png)
### Пример сразу с артефактами
```yaml
stages:
  - build
  - test
  - deploy
  - pages

image: alpine


build_job:
  stage: build
  script:
    - echo "Building the project..."
  artifacts:
    paths:
      - path/to/artifact
    exclude:
      - path/to/artifact/excluded_file.txt


test_job:
  stage: test
  script:
    - echo "Running tests..."

deploy_job:
  stage: deploy
  script:
    - echo "Deploying the project..."

pages_job:
  stage: deploy
  script:
    - echo "Deploying static websites..."
  artifacts:
    paths:
      - public/
  only:
    - main

create_file_job:
  stage: build
  script:
    - echo "Creating the file..."
  artifacts:
    paths:
      - path/to/file.txt

test_file_job:
  stage: test
  script:
    - echo "Testing the file..."

delete_file_job:
  stage: deploy
  script:
    - echo "Deleting the file..."

pages:
  stage: deploy
  script:
    - echo 'Publishing website to GitLab Pages'

  artifacts:
    paths:
      - public/
    exclude:
      - public/example.txt

```


## 3. сохранить артефакт одной из стадий + исключить из папки с артефактами любой файл 

```yaml
stages:
  - build
  - test
  - deploy
  - pages

image: alpine


build_job:
  stage: build
  script:
    - echo "Building the project..."
  artifacts:
    paths:
      - path/to/artifact
    exclude:
      - path/to/artifact/excluded_file.txt


test_job:
  stage: test
  script:
    - echo "Running tests..."

deploy_job:
  stage: deploy
  script:
    - echo "Deploying the project..."

pages_job:
  stage: deploy
  script:
    - echo "Deploying static websites..."
  artifacts:
    paths:
      - public/
  only:
    - main

create_file_job:
  stage: build
  script:
    - echo "Creating the file..."
  artifacts:
    paths:
      - path/to/file.txt

test_file_job:
  stage: test
  script:
    - echo "Testing the file..."

delete_file_job:
  stage: deploy
  script:
    - echo "Deleting the file..."

pages:
  stage: deploy
  script:
    - echo 'Publishing website to GitLab Pages'

  artifacts:
    paths:
      - public/
    exclude:
      - public/example.txt

```

4. сделать любую gitlab pages

```yaml
stages:
  - build
  - test
  - deploy
  - pages

image: alpine


build_job:
  stage: build
  script:
    - echo "Building the project..."
  artifacts:
    paths:
      - path/to/artifact
    exclude:
      - path/to/artifact/excluded_file.txt

test_job:
  stage: test
  script:
    - echo "Running tests..."

deploy_job:
  stage: deploy
  script:
    - echo "Deploying the project..."

pages_job:
  stage: deploy
  script:
    - echo "Deploying static websites..."
  artifacts:
    paths:
      - public/
  only:
    - master

create_file_job:
  stage: build
  script:
    - echo "Creating the file..."
  artifacts:
    paths:
      - path/to/file.txt

test_file_job:
  stage: test
  script:
    - echo "Testing the file..."

delete_file_job:
  stage: deploy
  script:
    - echo "Deleting the file..."

pages:
  stage: deploy
  script:
    - echo 'Publishing website to GitLab Pages'
    # Add commands to build your website here
  artifacts:
    paths:
      - public/
    exclude:
      - public/example.txt

```
