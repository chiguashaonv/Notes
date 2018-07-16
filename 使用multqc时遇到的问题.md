在使用multqc时，`multqc --help`显示了如下的错误：
```
Traceback (most recent call last):
  File "/home/liuke/.local/bin/multiqc", line 767, in <module>
    multiqc()
  File "/share/apps/anaconda3/lib/python3.5/site-packages/click/core.py", line 716, in __call__
    return self.main(*args, **kwargs)
  File "/share/apps/anaconda3/lib/python3.5/site-packages/click/core.py", line 675, in main
    _verify_python3_env()
  File "/share/apps/anaconda3/lib/python3.5/site-packages/click/_unicodefun.py", line 119, in _verify_python3_env
    'mitigation steps.' + extra)
RuntimeError: Click will abort further execution because Python 3 was configured to use ASCII as encoding for the environment.  Either run this under Python 2 or consult http://click.pocoo.org/python3/ for mitigation steps.

Additional information: on this system no suitable UTF-8
locales were discovered.  This most likely requires resolving
by reconfiguring the locale system.
```
根据错误提示，进入网址http://click.pocoo.org/python3/，发现了如下的解决方案，在使用multiqc时先输入：
```powershell
# 如果是德国的linux系统
export LC_ALL=de_DE.utf-8
export LANG=de_DE.utf-8
# 如果是美国的Linux系统
export LC_ALL=C.UTF-8
export LANG=C.UTF-8
```
然后就可以正常使用multiqc
