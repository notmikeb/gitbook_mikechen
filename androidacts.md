# run android ACTS 20170401

## Python2/3 在Windows 下的共存
http://zengrong.net/post/2350.htm
python2 python3 都不要加到 system path
使用  py2.bat & py3.bat 去加入 python2 path

## Has utf8 decode error
因為android acts 主要是在linux 下執行, 他需要使用which 發現 adb的路徑
沒有which , 所以寫了一個which.c , 編譯成which.exe放在path
```
#include <stdio.h>

int main(){
printf("j:\\utils\\adb.exe");
return 0;
}
```

## error message cannot be decode
http://blog.darkthread.net/post-2011-08-11-command-prompt-codepage.aspx
因為windows console 使用codepage big5, 所以要先使用chcp 轉成utf8(65001)
```
dos>chcp 65001
```
http://blog.sina.com.cn/s/blog_940224600101499e.html
1。如果python中所要处理的字符串中包含中文，那么最好要搞懂所用字符的编码，是gbk/gb2312/gb18030，还是utf-8，否则容易出现乱码，以及此处的语法错误。
而为了保险起见，最好用unicode("中文字符")的方式，来使用，操作这些中文字符。
当然，如果你自己需要，自己也知道，那最好unicode("中文字符").encode("utf-8")的方法，把其转为utf-8的格式，这个编码最通用。
2.notepad++新建的文件，也最好使用比较通用的utf-8的格式来存储文件，而不要用默认的ANSI，否则其中的中文，会由于ANSI不支持，而默认用你本地语言，比如我此处的GBK，去编码，这样容易出现一些编码类的错误。


## missing fastboot
Download adb & fastboot tools

ADB & FASTBOOT 常用指令
https://htcfz.wordpress.com/2016/07/05/adb-fastboot-%E5%B8%B8%E7%94%A8%E6%8C%87%E4%BB%A4/
Download adb & fastboot
https://androidmtk.com/download-minimal-adb-and-fastboot-tool

### missing permission to create symbol links
使用 Win+X, A 執行adminstration console
http://stackoverflow.com/questions/32877260/privlege-error-trying-to-create-symlink-using-python-on-windows-10
```
J:\git_home\acts\framework>cop acts\bin\act.py .
J:\git_home\acts\framework>python act.py -c sample_config.json -tb SampleTestBed -tc SampleTest

```

### Fix android_devices not found

Since the SampleTest does not require any device, it should check self.android_devices first
`python act.py -c sample_config.json -tb SampleTestBed -tc SampleTest`

`if hasattr(self, 'android_devices'):`

```
    """Tests"""
    def test_make_toast(self):
        if hasattr(self, 'android_devices'):
            for ad in self.android_devices:
                ad.droid.makeToast("Hello World.")
        return True
```


![](/assets/20170401_android_acts.png)