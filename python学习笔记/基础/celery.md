## Celery

### 简介

celery是python上面发布的异步任务框架

### 安装

`pip install celery`

### 使用

```python
# celery_task.py
from celery import Celery

# 创建celery app
app = Celery(
    main = 'tasks', # celery name 可None
    broker = 'redis://localhost:6379/1', # 生产者队列
)

# 当要定义一个任务的时候
@app.task
def add(x, y):
    return x + y
    
if __name__ == '__main__':
    result = add.delay(1,2)
    print(result)
```

### 启动

`celery -A worker_name worker -l info`

### 添加日志文件

#### 日志Config设置

```python
# config.py

import logging.config  # 使用python自带的日志模块
 
LOG_CONFIG = {
    'version': 1,
    'disable_existing_loggers': False,
    'formatters': {
        'simple': {
            # 'datefmt': '%m-%d-%Y %H:%M:%S'
            'format': '%(asctime)s [%(threadName)s:%(thread)d] [%(name)s:%(lineno)d] [%(module)s:%(funcName)s] [%(levelname)s]- %(message)s'
        }
    },
    'handlers': {
        'celery': {
            'level': 'INFO',  # 记录的级别 
            # 'class': 'logging.handlers.RotatingFileHandler',
		   # 'level': 'DEBUG',
            'formatter': 'simple',
            'class': 'logging.handlers.TimedRotatingFileHandler',
            'filename': 'asyn_task.log',
            'when': 'midnight',
            'encoding': 'utf-8',
        },
    },
    'loggers': {
         'asny_task': {
            'handlers': ['celery'],# 选择上面的celery handler作为日志记录对象
            'level': 'INFO',
            'propagate': True,
         }
    }
}
 
logging.config.dictConfig(LOG_CONFIG)
```

#### Celery导入log模块

```python
# celery_task.py
from celery import Celery
from celery.utils.log import get_task_loggr

# 创建celery app
app = Celery(
    main = 'tasks', # celery name 可None
    broker = 'redis://localhost:6379/1', # 生产者队列
)

logger = get_tasK_logger('asny_task') # 为日志任务命名

# 当要定义一个任务的时候
@app.task
def add(x, y):
    logger.info("Calling task add ({x}{y})".format(x=x, y=y))
    return x + y
    
if __name__ == '__main__':
    result = add.delay(1,2)
    print(result)
```