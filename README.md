# Домашнее задание к занятию "`Работа с Playbook`" - `Бакулев Евгений`

### Install and Configure Vector

Этот playbook предназначен для автоматической установки и конфигурации Vector

Playbook выполняет следующие задачи:
1. Создаёт директории для установки и конфигурации Vector.
2. Загружает и распаковывает бинарник Vector.
3. Копирует бинарник Vector в системный путь.
4. Разворачивает конфигурацию Vector с использованием шаблона.
5. Запускает Vector с заданной конфигурацией.
   
Параметры:
1. install_dir: Директория для установки Vector. По умолчанию — /opt/vector.
2. config_dir: Директория для хранения конфигурационных файлов. По умолчанию — /etc/vector.
3. config_file: Путь к конфигурационному файлу Vector. По умолчанию — {{ config_dir }}/vector.toml.
   
Задачи:
1. Ensure installation directory exists: Создаёт директорию для установки, если она не существует.
2. Ensure configuration directory exists: Создаёт директорию для конфигурации, если она не существует.
3. Download Vector binary: Скачивает архив с бинарником Vector с официального сайта.
4. Extract Vector binary: Распаковывает архив с бинарником в директорию для установки.
5. Copy Vector binary to system path: Копирует бинарник Vector в системный путь (/usr/local/bin).
6. Deploy Vector configuration: Применяет конфигурацию, используя шаблон vector.yaml.j2.
7. Run Vector: Запускает Vector с заданной конфигурацией.

Запустите ansible-lint site.yml и исправьте ошибки, если они есть
![Скриншот](https://github.com/garrkiss/ansible-02/blob/main/img/lint.png)
Попробуйте запустить playbook на этом окружении с флагом --check
![Скриншот](https://github.com/garrkiss/ansible-02/blob/main/img/check.png)
Запустите playbook на prod.yml окружении с флагом --diff. Убедитесь, что изменения на системе произведены.
![Скриншот](https://github.com/garrkiss/ansible-02/blob/main/img/diff1.png)
Повторно запустите playbook с флагом --diff и убедитесь, что playbook идемпотентен.
![Скриншот](https://github.com/garrkiss/ansible-02/blob/main/img/diff2.png)