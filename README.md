# HTML5 Drag and Drop

```
  drop: function(event) {
    event.preventDefault();
    var files = event.dataTransfer.files;
    var formData = new FormData();
    for (var i = 0; i < files.length; i++) {
      formData.append('file', files[i]);
    }
    xhr = new XMLHttpRequest();
    xhr.open('POST', '/upload');
    xhr.upload.onprogress = function (event) {
      if (event.lengthComputable) {
        var complete = (event.loaded / event.total * 100 | 0);
        this.$('progress').value = complete;
      }
    }
    xhr.onload = function() {
      App.File.store.push('file', {
        id: 1,
        name: 'Name'
      });
    }
    xhr.send(formData);
  }
```

## Progress Bar
+ https://fellowtuts.com/php/drag-n-drop-multiple-ajax-images-upload-with-progress-bar/
+ https://danielmg.org/demo/java-script/uploader/
+ https://github.com/zacfukuda/react-drop-upload-app/

### xhrFields
+ https://gist.github.com/gtechsltn/3cd830c6698e788c3c0e2a31ab4e6bf2
+ https://github.com/zacfukuda/react-drop-upload-app/blob/master/step2-ajax/dropUploadFile.js

# Backend on ASP.NET MVC
[Flowjs ASP.NET MVC](https://github.com/DmitryEfimenko/FlowJs-MVC)  

[FlowJS .Net Core API](https://github.com/ruisilva450/FlowJs-NetCore)
  
[Handled as a MVC 5 pre-action filter](https://github.com/Grummle/FlowUploadFilter)

# .NET Core
+ https://jason-ge.medium.com/aajx-file-upload-with-drag-and-drop-4a27a8232c06
+ https://github.com/jason-ge/AjaxFileUpload
