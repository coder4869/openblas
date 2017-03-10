# openblas
This is an repository for openblas learning.
Openblas Download URL: https://sourceforge.net/projects/openblas/files/

Compile For Andorid(mac):
```
1.Prepare:
	Android SDK and NDK:
	studio and sdk tools : https://developer.android.google.cn/studio/index.html
    ndk : https://developer.android.google.cn/ndk/downloads/index.html
	openblas src : https://sourceforge.net/projects/openblas/files/ 
2.Build Android Dev Environment
3.Config Path:
	export NDK=/usr/local/Android/android_sdk_mac/ndk-bundle
	export PATH=$NDK/toolchains/arm-linux-androideabi-4.9/prebuilt/darwin-x86_64/bin:$PATH
	export SYSROOT=$NDK/platforms/android-19/arch-arm
	export CC="$NDK/toolchains/arm-linux-androideabi-4.9/prebuilt/darwin-x86_64/bin/arm-linnux-androideabi-gcc --sysroot=$SYSROOT"
4.Run cmd in dir of openblas src
	make TARGET=ARMV7 HOSTCC=gcc CC=arm-linux-androideabi-gcc NOFORTRAN=1
Note:
 if errors occured like "fatal error: stdio.h: No such file or directory", use following cmd:
    make TARGET=ARMV7 HOSTCC=gcc CC=arm-linux-androideabi-gcc NOFORTRAN=1 CFLAGS+=-I$SYSROOT/usr/include -I.
5.compile finish and the following will appear:

    OpenBLAS build complete. (BLAS CBLAS)

    OS               ... Android             
    Architecture     ... arm               
    BINARY           ... 32bit                 
    C compiler       ... GCC  (command line : arm-linux-androideabi-gcc)
-n   Library Name     ... libopenblas_armv7p-r0.2.19.a
(Multi threaded; Max num-threads is 4)

To install the library, you can run "make PREFIX=/path/to/your/installation install".
    
```
