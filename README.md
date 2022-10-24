# MediaBench

<!-- vim-markdown-toc GFM -->

* [參數](#參數)
    - [系統](#系統)
    - [目標](#目標)
* [環境](#環境)
    - [cross compiler](#cross-compiler)
* [MediaBench](#mediabench)
    - [H.264](#h264)
        + [下載](#下載)
        + [構建](#構建)
        + [執行](#執行)
    - [JPEG-2000](#jpeg-2000)
        + [下載](#下載-1)
        + [構建](#構建-1)
        + [執行](#執行-1)

<!-- vim-markdown-toc -->

---

## 參數

### 系統

-   Ubuntu 18.04（WSL）

### 目標

-   arm64

## 環境

### cross compiler

```zsh
sudo apt install -y gcc-aarch64-linux-gnu
```

## MediaBench

### H.264

#### 下載

```zsh
wget https://cs.slu.edu/~fritts/mediabench/mb2/mb2_vid_h264.tgz --no-check-certificate

mkdir mb2_vid_h264

tar xvfz mb2_vid_h264.tgz -C mb2_vid_h264
```

#### 構建

```zsh
cd mb2_vid_h264
```

-   Makefile

```make
all:
	aarch64-linux-gnu-gcc -static -o get_report.b2b get_report.b2b.c -lm
	aarch64-linux-gnu-gcc -static -o get_report.rr get_report.rr.c -lm

clean:
	rm -f get_report.b2b get_report.rr
```

#### 執行

```zsh
./get_report.b2b
./get_report.rr
```

### JPEG-2000

#### 下載

```zsh
wget https://cs.slu.edu/~fritts/mediabench/mb2/mb2_vid_jpg2000.tgz --no-check-certificate

mkdir mb2_vid_jpg2000

tar xvfz mb2_vid_jpg2000.tgz -C mb2_vid_jpg2000
```

#### 構建

```zsh
cd mb2_vid_jpg2000
```

-   Makefile

```make
all:
	aarch64-linux-gnu-gcc -static -o get_report.b2b get_report.b2b.c -lm
	aarch64-linux-gnu-gcc -static -o get_report.rr get_report.rr.c -lm

clean:
	rm -f get_report.b2b get_report.rr
```

#### 執行

```zsh
./get_report.b2b
./get_report.rr
```
