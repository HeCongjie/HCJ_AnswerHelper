# 常见问题

## Q:提示No module named aip

A：由于未安装百度ocr依赖导致找不到aip，通过pip install baidu-aip安装即可解决

## Q:提示No module named PIL

A：使用PIL库进行图像处理，尝试安装PIL或pillow即可

## 已经将手机投影至电脑中，如何切换OCR模式？

A：需要修改一下几个文件
- 修改config.py中GET_TYPE的值为TYPE_IMG
- 在img_utils的spot方法中用get_ios_img()方法代替crop()方法
- 调整get_ios_img()方法中box的值，确定截图位置

## Q:提示cannot write mode RGBA as JPEG

A: 修改config.py中的图片路径，把jpg改为png即可

## Q:提示NO such file or directory :'img.jpg '

A：图片路径指向错误，请讲config.py中的图片路径指向截图，或者排查是否截图没有生成

## Q:提示No JSON Object could be decode

A：出现这个说明已经成功运行，但是对于接口的异常没有进行处理，最新的代码已经修复这个缺陷，可以更新最新代码进行
 
