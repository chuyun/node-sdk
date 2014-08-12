# node-upyun
official upyun sdk for node.js (with upyun api v2.0)

# Install
__NOT AVAILABLE NOW__
```sh
$ npm install upyun --save
```

# Example 
```js
var UPYUN = require('upyun');

var upyun = new UPYUN('testbucket', 'operatername', 'operaterpwd', 'v0');

upyun.getUsage(function(err, result) {
    //...
})
```

# Docs
## API
* [`getUsage`](#getUsage)
* [`listDir`](#listDir)
* [`createDir`](#createDir)
* [`removeDir`](#removeDir)
* [`uploadFile`](#uploadFile)
* [`existsFile`](#existsFile)
* [`downloadFile`](#downloadFile)
* [`removeFile`](#removeFile)

## Utils

* [`setEndpoint`](#setEndpoint)


# API

<a name="getUsage" />
### getUsage(callback)
To get how many quota has been used.(Unit:`Byte`)

---------------------------------------

<a name="" />
### listDir(remotePath, [limit], [order], [iter], callback)
Get the file list of that dir. The response contains each item's type(file or dir), size(unit: `Byte`), last modify time.

__Arguments__
* `remote_dir_path` The dir path which you want to traverse.
* `limit` Specifies the maximum number of file list output per request.
* `order` Sort the file list by 'last_modified' as `asc` or `desc`.(Default: `asc`)
* `iter` Specifies the start of iteration.

---------------------------------------

<a name="createDir" />
### createDir(remotePath, callback)
Create a new dir in UPYUN bucket.

__Arguments__
* `remotePath` The dir path which you want to create.

---------------------------------------

<a name="removeDir" />
### removeDir(remotePath, callback)
Delete a dir

* `remotePath` The dir path which you want to remove.

---------------------------------------

<a name="uploadFile" />
### uploadFile(remotePath, localFile, type, checksum, [opts], callback)
Upload a file into UPYUN bucket.

__Arguments__
* `remotePath` Where the file will be stored in your UPYUN bucket.
* `localFile` The file you want to upload. It can be a `path` string or the file's raw data.
* `type` Specifies the file's content-type.
* `checksum` Set `true` to force SDK send a md5 of local file to UPYUN. Or set a md5value string by yourself.
* `opts` The additional http request headers(JavaScript Object). More detail in [Official Docs](http://docs.upyun.com/api/http_api/#上传文件)

---------------------------------------

<a name="existsFile" />
### existsFile(remotePath, callback)
`HEAD` a path to detect if there is an file.

__Arguments__
* `remotePath` The file's path in your UPYUN bucket.

---------------------------------------

<a name="downloadFile" />
### downloadFile(remotePath, callback)
Download a file from UPYUN bucket.

__Arguments__
* `remotePath` The file's path in your UPYUN bucket.

---------------------------------------

<a name="removeFile" />
### removeFile(remotePath, callback)
Delete a file from UPYUN bucket.

__Arguments__
* `remotePath` The file's path in your UPYUN bucket.

# Utils

<a name="setEndpoint" />
### setEndpoint(endpoint)
Use this method to set api endpoint manually.

__Arguments__
* `endpoint` The value can be these(leave blank to let sdk auto select the best one):
  * `ctcc` or `v1`: China Telecom
  * `cucc` or `v2`: China Unicom
  * `cmcc` or `v3` China Mobile
  * `v0` or any other string: Will use `v0.api.upyun.com` (auto detect routing)


# Note

The original owner of [`upyun npm package`](https://www.npmjs.org/package/upyun) was [James Chen](http://ashchan.com) 

After consultation with James, this package has been transfered to official upyun dev. team.

Any futher update and maintenance will conducted by upyun dev. team and subsequent versions will not be associated with the original project.

In npm registry, `"upyun": "<=0.0.3"` were published as [node-upyun](https://github.com/ashchan/node-upyun) by [James Chen](http://ashchan.com).

__Thanks to  [James Chen](http://ashchan.com)  for his contribution to upyun.__
