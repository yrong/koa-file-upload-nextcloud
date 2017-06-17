# koa-file-upload-nextcloud

koa2 middle to upload file, 支持本地文件系统、 nextcloud私有云

### Features

- support upload to dir

```javascript
options['upload'] = {
  "url": '/api/upload',
  "storeDir": 'xxx',
  "provider": "local",
  "mimetypes": ['image/png','image/bmp'], // 如果没有配置,将不进行类型检查 http://www.freeformatter.com/mime-types-list.html
  "folder": "public",
  "urlPath": "images"
}
```

- support upload to nextcloud

```javascript
options["upload"] = {
  "url": "/api/upload/nc",
  "provider": "nc",
  "folder": "public/upload",
  "nc_host":"http://localhost:8089/FileStore",
  "nc_admin_user":"admin",
  "nc_admin_password":"admin",
  "nc_public_group":"share"
}
```


### How to use

```javascript
const file_uploader = require('koa-file-upload-fork')
app.use(mount(option.url,file_uploader(option).handler))
```

### Requirements

- Node v6.0+

## Workflow

- `npm install`
