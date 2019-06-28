### python获取大文件

```python
# 使用wget

```

#### requests下载大文件

```python
# 使用requests stream流迭代下载文件
response = request.get(url, stream=True)
f = open('file_path', 'wb')
for chunk in response.iter_content(chunck_size=512):
    if chunck:
        f.write(chunk)
```

#### 批量下载大文件

```python
from gevent import monkey
from gevent import Pool
monkey.path.patch_all()  # 打猴子补丁，所有io变非阻塞
import requests
from pathlib import Path
url_list = ['url1','url2']

def download(url):
    file_name = Path('D:\\') / url.split('/')
    if file_name.exists():
        return
    
    print(f'下载:{url}')
    response = requests.get(url, stream=True)
    with open(file_name, 'wb') as f:
        for data in response.iter_content(chunck=512):
            f.write(data)
            
def run(url_list):
    pool = Pool(size=100)
    pool.map(download, url_list)
if __name__ == '__main__':
    run(url_list)
    print('Downloaded!!')
```

### requets断点下载

```python

```

