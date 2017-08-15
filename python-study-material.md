### python document writing

http://iapyeh.readthedocs.io/en/latest/blogs/technical/how2pydocs.html


### bug python 

```
 记一次PIP执行出错--UnicodeDecodeError: 'ascii' codec can't decode byte 0xb1 in position 9: ordinal
标签： python
2016-12-14 17:03 412人阅读 评论(0) 收藏 举报
 分类： python配置（3）  
版权声明：本文为博主原创文章，未经博主允许不得转载。
运行pip时，出错
 UnicodeEncodeError: 'ascii' codec can't encode character u'\u258e' in position 8 : ordinal not in range(128)
原因是pip安装Python包会加载我的用户目录，我的用户目录恰好是中文的，ascii不能编码。解决办法是： 
python目录 Python27\Lib\site-packages 建一个文件sitecustomize.py 
内容写： 
[plain] view plain copy
import sys   
#sys.setdefaultencoding('gb2312')   
sys.setdefaultencoding('big5')   

python会自动运行这个文件。
```