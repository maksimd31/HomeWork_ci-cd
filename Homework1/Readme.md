# Homework1

> # Убедительная просьба писать домашние задания на странице с домашним заданием! 

1. Зарегистрироваться в gitlab
2. создать pipeline n runner
3. сохранить артефакт одной из стадий + исключить из папки с артефактами любой файл 
4. сделать любую gitlab pages

# Решение

1. Зарегистрироваться в gitlab
2. создать pipeline n runner

```yaml
stages:
  - build
  - test
  - deploy

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

```


3. сохранить артефакт одной из стадий + исключить из папки с артефактами любой файл 

```yaml
stages:
  - build
  - test
  - deploy

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

```

4. сделать любую gitlab pages