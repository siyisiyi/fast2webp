# img2webp

一个将 PNG、JPG、JPEG、BMP、GIF 等格式的图像文件批量 (递归) 转换为 webp 格式的 Python 脚本

可以设定压缩级别 (0 ~ 100)，数字越大品质越好。支持无损压缩。支持多线程。

可以在 GNU/Linux 上运行，Mac OS 估计也可以 (没测试过)，Windows 上可能要修改一下才能用 (主要是目录地址中 `/` 与 `\` 的区别)

> 想了想将项目名称改成了 `img2webp`，这样就可以少打两个字了 \_(:з」∠)\_

## 依赖

- Python3

- webp

## 安装

为 GNU/Linux 提供了一个安装脚本。运行并输入密码即可安装

```shell
./install.sh
```

实际上就是将 `img2webp.py` 复制到 `/usr/local/bin` 并重命名为 `img2webp`

## 使用方法

```shell
img2webp [options] [value]
```

## 截图

![example](https://f.cangg.cn:82/data/201812111203537788.gif)

## 参数 (options)

支持以下参数：

|    参数     |    默认值    | 描述                                                         |
| :---------: | :----------: | :----------------------------------------------------------- |
|     -i      | . (当前目录) | 需要转换的文件所在的目录，会递归进行转换。                   |
|     -o      |   ./output   | `*.webp` 文件的输出目录。<br>输出目录结构与输入目录保持一致。<br>如果输出不存则会按照给定的路径新建文件夹。<br>如果缺省，则会在当前目录中新建并输出到目录 `output` |
|     -q      |      80      | 与 `cwebp` 中相同。表示压缩的程度 (0 ~ 100)，数字越大品质越好。 |
|     -t      |      30      | 线程池中线程的个数。数字越大转换速度越快，当然，也更吃资源。 |
|  -lossless  |      -       | 与 `cwebp` 中相同。无损压缩。                                |
| -enable_gif |      -       | 将 gif 转为 webp (默认情况下会跳过 gif 文件)<br>转换 gif 文件比较吃资源，而且可能出现压缩后的 webp 比原 gif 大的情况，慎用。<br>转换 gif 文件不支持无损压缩，如果使用了 `-lossless` 参数会被理解成 `-q 100` |
|   -uncopy   |      -       | 默认情况下会将非图片文件复制到输出目录中<br>使用参数 `-uncopy` 关闭这一特性 (`*.webp` 和 `*.gif` 仍会被复制) |

## TODO

- 支持 Windows
- 支持更多的参数

