os.path.split(os.path.realpath(__file__))[0]　　获取执行py文件自身的所在目录
-------------------------------------------------------------------------------------------------------------------------
os.path.dirname(os.getcwd())　　上一级目录名
os.chdir(os.path.dirname(os.getcwd()))   返回上一级目录

os.listdir(‘dirname’)     列出指定目录下的所有文件和子目录，lis包括隐藏文件，并以列表方式打印
os.linesep    字符串给出当前平台使用的行终止符
os.getcwd()     获取当前工作目录，即当前python脚本工作的目录路径
os.chdir(“dirname”)     改变当前脚本工作目录；相当于shell下cd
os.makedirs(‘dirname1/dirname2’)     可生成多层递归目录
os.removedirs(‘dirname1’)     若目录为空，则删除，并递归到上一级目录，如若也为空，则删除，依此类推
os.mkdir(‘dirname’)     生成单级目录；相当于shell中mkdir dirname
os.rmdir(‘dirname’)     删除单级空目录，若目录不为空则无法删除，报错；相当于shell中rmdir dirname

os.remove()     删除一个文件
os.rename(“oldname”,”newname”)     重命名文件/目录

os.curdir     返回当前目录: (‘.’)
os.pardir     获取当前目录的父目录字符串名：(‘..’)
os.chmod(‘pathfile’,os.W_OK)     改变文件权限模式

os.path.realpath(path)      #返回path的真实路径

os.path.relpath(path[, start])      #从start开始计算相对路径

os.path.getsize(path)      #返回文件大小，如果文件不存在就返回错误

os.path.split(path)     将path分割成目录和文件名二元组返回
os.path.splitext(path)     分离文件名与扩展名；默认返回(fname,fextension)元组，可做分片操作 ，以“.”为分隔符


os.path.samefile(path1, path2)      #判断目录或文件是否相同
os.path.isfile(path)     如果path是一个存在的文件，返回True。否则返回False
os.path.isdir(path)     如果path是一个存在的目录，则返回True。否则返回False
os.path.exists(path)     如果path存在，返回True；如果path不存在，返回False


os.path.abspath(path)     返回path规范化的绝对路径
os.path.dirname(path)     返回path的目录。其实就是os.path.split(path)的第一个元素
os.path.basename(path)     返回path最后的文件名。如何path以／或\结尾，那么就会返回空值。即os.path.split(path)的第二个元素
os.path.join(path1[, path2[, ...]])      #把目录和文件名合成一个路径

-------------------------------------------------------------------------------------------------------------------------
os.name    判断现在正在实用的平台，Windows 返回 ‘nt’; Linux 返回’posix’
os.walk方法 
    walk(top, topdown=True, onerror=None, followlinks=False) 
    top – 根目录下的每一个文件夹(包含它自己), 产生3-元组 (dirpath, dirnames, filenames)【文件夹路径, 文件夹名字, 文件名】。 
    topdown –可选，为True或者没有指定, 一个目录的的3-元组将比它的任何子文件夹的3-元组先产生 (目录自上而下)。如果topdown为 False, 一个目录的3-元组将比它的任何子文件夹的3-元组后产生 (目录自下而上)。 
    onerror – 可选，是一个函数; 它调用时有一个参数, 一个OSError实例。报告这错误后，继续walk,或者抛出exception终止walk。 
    followlinks – 设置为 true，则通过软链接访问目录。 
    方法：os.walk(path),遍历path，返回一个对象，他的每个部分都是一个三元组,(‘目录x’，[目录x下的目录list]，目录x下面的文件)

os.stat(‘path/filename’)     获取文件/目录信息
os.symlink(src, dst)     创建符号链接，源需绝对路径—在数据预处理时可节省空间 
    src - 这是来源路径。 
    dest - 这是原来不存在的目标路径。
os.utime()     修改时间属性
os.system()     运行shell命令。
os.environ     获取系统环境变量
os.access(‘pathfile’,os.W_OK)     检验文件权限模式，输出True，False

os.path常用模块详解
os.path.join(path1[, path2[, …]])     将多个路径组合后返回，第一个绝对路径之前的参数将被忽略
os.path.getsize(name)    获得文件大小，如果name是目录返回0L
os.path.isabs(path)     如果path是绝对路径，返回True
os.path.normcase(path)     在Linux下，该函数会原样返回path，在windows平台上会将路径中所有字符转换为小写，并将所有斜杠转换为反斜杠
os.path.splitdrive(path)     拆分驱动器名和路径，主要对win，对linux元组第一个总是空的
os.path.getatime(path)     返回path所指向的文件或者目录的最后存取时间
os.path.getmtime(path)     返回path所指向的文件或者目录的最后修改时间
os.path.walk(top,func,arg) 
    top表示需要遍历的目录树的路径 
    func表示回调函数，对遍历路径进行处理.所谓回调函数，是作为某个函数的参数使用，当某个时间触发时，程序将调用定义好的回调函数处理某个任务.回调函数必须提供3个参数：第1个参数为walk()的参数tag，第2个参数表示    目录列表，第3个参数表示文件列表 
    arg是传递给回调参数func的元组.回调函数的一个参数必须是arg，为回调函数提供处理参数.参数arg可以为空
os.path.walk()与os.walk()产生的文件名列表并不相同。os.path.walk()产生目录树下的目录路径和文件路径，而os.walk()只产生文件路径
os.path.getatime(path)      #返回最后一次进入此path的时间。
os.path.getmtime(path)      #返回在此path下最后一次修改的时间。
os.path.getctime(path)      #返回path的大小
os.path.islink(path)      #判断路径是否为链接
os.path.ismount(path)      #判断路径是否为挂载点（）
os.path.normcase(path)      #转换path的大小写和斜杠
os.path.normpath(path)      #规范path字符串形式
os.path.sameopenfile(fp1, fp2)      #判断fp1和fp2是否指向同一文件
