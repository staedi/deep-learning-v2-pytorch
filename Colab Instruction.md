# Making the best use of Google Colab and Google Drive

This file gives tips for collaborating **Google Colab notebook** with **Google Drive** and **Github**

The following two modifications can be made.
* Markdown block
* Codeblock


## Image in Notebook markdown text

**Google Colab Notebook** doesn't allow images files from **Google Drive** or local files as as now. One possible workaround is to use **Github** repository.

```
<img src='https://github.com/staedi/deep-learning-v2-pytorch/raw/master/intro-to-pytorch/assets/mnist.png'>
```

## Import custom source in Notbook codeblock

**Google Colab Notebook** allows mounting **Google Drive** and use files from there. However, the process is not straightforward.

The following procedures are needed.
* Mounting **Google Drive**
* Import custom library from **Google Drive**


### Mounting Google Drive

From `google.colab.drive` module, you can connect to Google Drive using `mount` function 

you can connect to **Google Drive** and *import* files from there.

```
from google.colab import drive
drive.mount("/content/drive")
```

### Import custom library from Google Drive

Now, you can access files in **Google Drive**. Instead of usual `import` actions, you use `new_module` function from `imp` module.

```
import imp 
helper = imp.new_module('helper')
exec(open("./helper.py").read(), helper.__dict__)
```
