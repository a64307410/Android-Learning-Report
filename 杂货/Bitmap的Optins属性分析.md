##Bitmap加载图片的options
###options的值:
	1. 1,2,4....这样的整数(默认是1,以后是2的倍数)
	2. options的值是接近2的整数倍
####看下面整理的log:
	(注:最后的数字代表内存占用.)
	02-26 15:27:21.329: D/test(28162): 14745600-->没有opts==>14.0625
	02-26 15:28:24.389: D/test(28296): 3686400-->2===>3.5156
	02-26 15:29:08.019: D/test(28381): 3686400-->3
	02-26 15:29:33.089: D/test(28541): 921600--->4===>0.8789

####也即是:
- opts=1,内存14.0625MB
- opts=2,内存3.5156MB
- opts=4,内存为0.8789MB
- opts=3,不存在,如果接近2就是2的值,如果接近4,就是4的值

####总结:
	内存的占用比例是区别很大的
	可以在默认的时候加载小图,然后用户点击的时候加载大图.