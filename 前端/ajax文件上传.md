## Ajax文件上传

### html部分代码

```html
// form表单上传

```

### js代码

```javascript
// 文件上传Ajax
$.ajax（{
    url：'target_url',
    type: 'POST',
    cache: false,
    data: new FormData($('#uploadForm')[0]),
    processData: false,
        contentType: false,}).done(function (res){
            
        }).fail(function (res){
            
        })
```

