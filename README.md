# Автоматический подбор коэффициентов самодиффузии для оценки результатов ЯМР


## Описание
Цель проекта – создать программу, автоматизирующую подбор данных, необходимых для проведения гистологического исследования биопсийного материала.
Данная задача курируется Гиматдиновым Рустамом Саясовичем - заведющим кафедры медицинской физики, в Казанском Медицинском Университете.
Не секрет что в борьбе с раком, время играет чуть ли не решающую роль. Автоматизируя процесс, пропускная сбособность исследуемых образцов увеличиться в десятки раз, что сократит время ожидания результата до одного дня. Данный метод более информационно емкий так как образец можно исследовать целиком, а не отдельно взятый маленький срез.
Эксперимент выполнялся на кафедре физики молекулярных систем на спектрометре Брукер. В ходе данного эксперимента было выяснено что ЯМР методом можно исследовать такого типа образцы.

## Входные данные
Входные данные получены для разрешения порядка десятка микрометров, что достаточно для изучения ткани, однако данные ещё собираются поэтому качество модели может впоследствии значительно улучшаться.

## Требования для запуска
- Docker 

## Документация
- [Numpy](https://numpy.org/doc/)
- [Matplotlib](https://matplotlib.org/stable/index.html)
- [Pandas](https://pandas.pydata.org/docs/index.html)
- [PyTorch](https://pytorch.org/docs/stable/index.html)
- [Streamlit](https://docs.streamlit.io/library/get-started/)

### ML модель сохранена в ".pth" расширении

## Инструкции по сборке и запуску

### Клонирование репозитория

```bash
git clone https://github.com/edvltshn/MFDP2-VideoEmotionAnalisys.git
cd mfdp/app
```

### Сборка Docker образа и запуск контейнеров с FastAPI и Streamlit
```bash
# сборка docker image
docker build -t mfdp2:latest .

# запуск контейнера с FastAPI сервером в фоновом режиме:
docker run --gpus all -d --rm -v $PWD:/app -p 8000:8000 mfdp2:latest uvicorn main:app --host 0.0.0.0 --port 8000

# запуск контейнера с фронтендом на Streamlit в фоновом режиме:
docker run -d --rm -v $PWD:/app -p 8501:8501 mfdp2:latest streamlit run app.py
```

После выполнения команд, сервисы будут доступны на следующих портах:  
FastAPI сервер будет доступен на http://localhost:8000  
Streamlit фронтенд будет доступен на http://localhost:8501   

- Где проводился Хакатон?
https://ai-talent-hack.webflow.io/
