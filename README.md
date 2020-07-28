# daka_04_string
字符串

1.字符串的定义
    Python 中字符串被定义为引号之间的字符集合

    Python 的常用转义字符
    转义字符	描述
    \\	反斜杠符号
    \'	单引号
    \"	双引号
    \n	换行
    \t	横向制表符(TAB)
    \r	回车

    即如果字符串中需要出现单引号或双引号，可以使用转义符号\对字符串中的符号进行转义
    print('let\'s go')  # let's go
    print("let's go")  # let's go
    print('C:\\now')  # C:\now
    print("C:\\Program Files\\Intel\\Wifi\\Help")
    #C:\Program Files\Intel\Wifi\Help

    三引号允许一个字符串跨多行，字符串中可以包含换行符、制表符以及其他特殊字符
    para_str = '''这是一个多行字符串的实例
    多行字符串可以使用制表符
    TAB ( \t )。
    也可以使用换行符 [ \n ]。
    '''
    print(para_str)
    #这是一个多行字符串的实例
    #多行字符串可以使用制表符
    #TAB ( 	 )。
    #也可以使用换行符 [ 
    # ]。

2.字符串的切片与拼接

    类似于元组具有不可修改性
    从 0 开始 
    切片通常写成 start:end 这种形式，包括「start 索引」对应的元素，不包括「end索引」对应的元素。
    索引值可正可负，正索引从 0 开始，从左往右；负索引从 -1 开始，从右往左。使用负数索引时，会从最后一个元素开始计数。最后一个元素的位置编号是 -1。

    str1 = 'I Love LsgoGroup'
    print(str1[:6])  # I Love
    print(str1[5])  # e
    print(str1[:6] + " 插入的字符串 " + str1[6:])  
    #I Love 插入的字符串  LsgoGroup

    s = 'Python'
    print(s)  # Python
    print(s[2:4])  # th
    print(s[-5:-2])  # yth
    print(s[2])  # t
    print(s[-1])  # n

3.字符串的常用内置方法

    capitalize() 将字符串的第一个字符转换为大写。
    lower() 转换字符串中所有大写字符为小写。
    upper() 转换字符串中的小写字母为大写。
    swapcase() 将字符串中大写转换为小写，小写转换为大写。

    count()
    str2 = "DAXIExiaoxie"
    print(str2.count('xi'))  # 2

    endswith()检查字符串是否以指定子字符串...结束
    startswith()检查字符串是否以指定子字符串...开头
    str2 = "DAXIExiaoxie"
    rint(str2.endswith('ie'))  # True
    print(str2.endswith('xi'))  # False
    print(str2.startswith('Da'))  # False
    print(str2.startswith('DA'))  # True  

    find()检测 str 是否包含在字符串中
    rfind()从右边开始查找
    str2 = "DAXIExiaoxie"
    print(str2.find('xi'))  # 5
    print(str2.find('ix'))  # -1
    print(str2.rfind('xi'))  # 9

    isnumeric() 判断字符串中是否只包含数字字符
    str3 = '12345'
    print(str3.isnumeric())  # True
    str3 += 'a'
    print(str3.isnumeric())  # False

    ljust()返回一个原字符串左对齐，并使用fillchar（默认空格）填充至长度width的新字符串。
    rjust()返回一个原字符串右对齐，并使用fillchar（默认空格）填充至长度width的新字符串。
    str4 = '1101'
    print(str4.ljust(8, '0'))  # 11010000
    print(str4.rjust(8, '0'))  # 00001101

    lstrip([chars]) 截掉字符串左边的空格或指定字符。
    rstrip([chars]) 删除字符串末尾的空格或指定字符。
    strip([chars]) 在字符串上执行lstrip()和rstrip()。

    partition() 找到子字符串，把字符串分为一个三元组(pre_sub,sub,fol_sub)，如果字符串中不包含则返回('原字符串','','')。
    rpartition()类似于partition()方法，不过是从右边开始查找。
    str5 = ' I Love LsgoGroup '
    print(str5.strip().partition('o'))  # ('I L', 'o', 've LsgoGroup')
    print(str5.strip().partition('m'))  # ('I Love LsgoGroup', '', '')
    print(str5.strip().rpartition('o'))  # ('I Love LsgoGr', 'o', 'up')

    replace(old, new [, max]) 把 将字符串中的old替换成new，如果max指定，则替换不超过max次。
    split(str="", num) 不带参数默认是以空格为分隔符切片字符串，如果num参数有设置，则仅分隔num个子字符串，返回切片后的子字符串拼接的列表。
    u= "www.baidu.com.cn"
    #使用默认分隔符
    print(u.split())  # ['www.baidu.com.cn']

    #以"."为分隔符
    print((u.split('.')))  # ['www', 'baidu', 'com', 'cn']

    #分割0次
    print((u.split(".", 0)))  # ['www.baidu.com.cn']

    #分割一次
    print((u.split(".", 1)))  # ['www', 'baidu.com.cn']

    #分割两次
    print(u.split(".", 2))  # ['www', 'baidu', 'com.cn']

    #分割两次，并取序列为1的项
    print((u.split(".", 2)[1]))  # baidu

    #分割两次，并把分割后的三个部分保存到三个变量
    u1, u2, u3 = u.split(".", 2)
    print(u1)  # www
    print(u2)  # baidu
    print(u3)  # com.cn

    splitlines() 按照行('\r', '\r\n', \n')分隔，返回一个包含各行作为元素的列表
    str6 = 'I \n Love \n LsgoGroup'
    print(str6.splitlines())  # ['I ', ' Love ', ' LsgoGroup']
    print(str6.splitlines(True))  # ['I \n', ' Love \n', ' LsgoGroup']

    maketrans() 创建字符映射的转换表，第一个参数是字符串，表示需要转换的字符，第二个参数也是字符串表示转换的目标。
    translate() 根据参数table给出的表，转换字符串的字符，要过滤掉的字符放到参数中
    str7 = 'this is string example....wow!!!'
    intab = 'aeiou'
    outtab = '12345'
    trantab = str7.maketrans(intab, outtab)
    print(trantab)  # {97: 49, 111: 52, 117: 53, 101: 50, 105: 51}
    print(str7.translate(trantab))  # th3s 3s str3ng 2x1mpl2....w4w!!!

4.字符串格式化

    format 格式化函数
    str8 = '{0:.2f}{1}'.format(27.658, 'GB')  # 保留小数点后两位
    print(str8)  # 27.66GB

    Python 字符串格式化符号
    符 号	     描述
    %c	格式化字符及其ASCII码
    %s	格式化字符串，用str()方法处理对象
    %r	格式化字符串，用rper()方法处理对象
    %d	格式化整数
    %o	格式化无符号八进制数
    %x	格式化无符号十六进制数
    %X	格式化无符号十六进制数（大写）
    %f	格式化浮点数字，可指定小数点后的精度
    %e	用科学计数法格式化浮点数
    %E	作用同%e，用科学计数法格式化浮点数
    %g	根据值的大小决定使用%f或%e
    %G	作用同%g，根据值的大小决定使用%f或%E


    格式化操作符辅助指令
    m.n	m 是显示的最小总宽度,n 是小数点后的位数（如果可用的话）
    -	用作左对齐
    +	在正数前面显示加号( + )
    #	在八进制数前面显示零('0')，在十六进制前面显示'0x'或者'0X'(取决于用的是'x'还是'X')
    0	显示的数字前面填充'0'而不是默认的空格
        print('%5.1f' % 27.658)  # ' 27.7'
        print('%.2e' % 27.658)  # 2.77e+01
        print('%10d' % 10)  # '        10'
        print('%-10d' % 10)  # '10        '
        print('%+d' % 10)  # +10
        print('%#o' % 10)  # 0o12
        print('%#x' % 108)  # 0x6c
        print('%010d' % 5)  # 0000000005


5.练习题：

    1)字符串函数回顾
        怎么批量替换字符串中的元素？
            replace()
        怎么把字符串按照空格进⾏拆分？
            string.split()
        怎么去除字符串⾸位的空格
            string.lstrip()

    2) 实现isdigit函数
        题目要求
        实现函数isdigit， 判断字符串里是否只包含数字0~9
        def isdigit(string):
    
        """
        判断字符串只包含数字
        :param string:
        :return:
        """
        # your code here

        tr = True if string.isnumeric() else False
            return tr
            x = input()
            tr = isdigit(x)
            print(tr)

    3)leetcode 5题 最长回文子串

    给定一个字符串 s，找到 s 中最长的回文子串。你可以假设 s 的最大长度为 1000。

    示例:

    输入: "babad"

    输出: "bab"

    输入: "cbbd"

    输出: "bb"

        class Solution:
            def longestPalindrome(self, s: str) -> str:
                    
            # your code here
            n = len(s)

        dp = [[0 for i in range(n)] for i in range(n)]
        left = 0
        right = 0
        for i in range(n-2,-1,-1):
            dp[i][i] = 1
            for j in range(i + 1,n,1):
                dp[i][j] = str[i] == str[j] and ( j-i<3 or dp[i+1][j-1])
                if(dp[i][j] and right-left<j-i):
                    left=i
                    right=j
        return str[left:right+1]


6.总结：

    对字符串的处理函数很多：
    capitalize()
    lower()
    upper()
    swapcase()
    count()
    endswith()
    startswith()
    find()
    rfind()
    isnumeric()
    ljust()
    rjust()
    lstrip([chars])
    rstrip([chars])
    strip([chars])
    partition(sub)
    rpartition(sub)
    replace(old, new [, max])
    split(str="", num) 
    splitlines([keepends])
    maketrans(intab, outtab)
    translate(table, deletechars="")
    format

    可以发现python对字符串的处理能力是很强大的
