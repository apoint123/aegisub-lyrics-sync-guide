# Aegisub 打轴指南
[![CC0](https://img.shields.io/badge/License-CC0%201.0-lightgrey.svg)](https://creativecommons.org/publicdomain/zero/1.0/)

[一些有用的小提示](/Useful-tips.md)
## 概述
Aegisub 只能编辑并导出 ASS 字幕格式的文件，你需要一些小小的操作才可以为歌词文件（例如 Lyricify Syllable 和 TTML）打轴

> [!WARNING]
> ASS 只能精确到厘秒（即 10 毫秒），所以你打轴的精度最多只能精确到 10 毫秒级别  
> 但是你无需关注此问题，因为一般人无法察觉出这 10 毫秒的区别。

## 为什么要选择 Aegisub?
Aesigub 与其它打轴工具（例如 AMLL TTML TOOL）有本质区别。Aegisub 通过阅读频谱图并拖动鼠标进行打轴，直观方便，精度非常高  

其他打轴工具受限于你的反应速度，可能会有数十至数百毫秒的偏移，而且长时间的集中注意力倾听还可能会进一步降低精度

## 你需要的文件和工具
为了使用 Aegisub 为歌词打轴，你需要准备下列工具和文件：

- 一台运行着 Windows 10 或更新版本的电脑
- [Aegisub](https://github.com/TypesettingTools/Aegisub) 软件
    - 我推荐使用 arch1t3cht 的 [Fork 版本](https://github.com/arch1t3cht/Aegisub)，因为其包含更多功能。本篇指南也将以该版本为例
- 相应的音频文件
- 文件格式转换器
    - 推荐使用 [LDDC](https://github.com/chenmozhijin/LDDC) 获取 ASS 字幕文件
    - 或者使用我写的 [QQLyricFetcher](https://github.com/apoint123/QQLyricFetcher)
    - 在打轴完成后，你还需要使用我的 [AssandQrcConverter](https://github.com/apoint123/AssandQrcConverter-rust) 工具将 ASS 字幕格式转换为 Lyricify Syllable 文件或 QRC 文件
    - 或者使用由 ranhengzhang 写的[脚本](https://github.com/ranhengzhang/amll-ttml-db-raw-data)和 [TTML TRANSLATER](https://github.com/ranhengzhang/ttml-translater)，该脚本是专门为 TTML 歌词打轴设计的

## 可选工作
这些工作并非必须，但完成它们可以极大地优化你的打轴体验

- 相应的歌词文件
    - 可以是从音乐网站上复制的纯文本
    - 也可以使用上述的 LDDC 或 QQLyricFetcher 下载带时间轴的歌词
- 提取对应歌曲的人声部分
    - 你可以使用搜索引擎寻找此类工具

## Aegisub 软件的设置
建议调整这些设置以便提高打轴体验

1. 点击上方工具栏的 **查看** -> **选项**
2. 将 **高级** -> **音频** 下方的 **质量** 和 **Frequency mapping** 分别更改为 **极高质量** 和 **Extended**
3. 点击上方工具栏的 **视频** -> **使用空白视频**，将 **帧率(fps)** 修改为你屏幕支持的最高帧率
> [!IMPORTANT]
> 低帧率会导致高显示延迟。保持默认的低帧率会导致预览效果看起来比实际上的慢，所以你需要把帧率修改得大一些，通常你屏幕的帧率足矣，但你也可以改为更大的值

## 准备工作
> [!TIP]
> 建议你为每首歌创建一个单独文件夹用于存储文件，否则大量文件可能会弄乱你的桌面

1. 打开 [QQLyricFetcher](https://github.com/apoint123/QQLyricFetcher) 并按照提示下载你喜欢的歌词  

![image](https://github.com/user-attachments/assets/5be3d791-8768-4c61-8feb-08989b5037f2)  

3. 使用 Aegisub 打开软件目录下的字幕文件
4. 删除歌词开头和尾部的元数据  

![image](https://github.com/user-attachments/assets/7b44149e-c955-4e37-a2c6-4fefbdf8f0d1)


## 开始打轴
> [!NOTE]
> 在此处仅介绍打轴时你需要注意的其他情况，请查看 [Aegisub 文档](https://aegisub.org/zh-cn/docs/latest/karaoke_timing_tutorial/)学习完整的打轴流程

1. 将对应的音频文件拖入到 Aegisub 主窗口中
2. 如果没有处于频谱分析模式，点击波形图下方的 **频谱分析模式** 按钮

> [!IMPORTANT]
> 波形图对制作逐字歌词几乎没有帮助，必须切换为频谱图

![image](https://github.com/user-attachments/assets/da06aa97-e26c-4880-aec4-a9b0c0b4b24f)

3. 点击上方工具栏的 **视频** -> **使用空白视频**
> [!TIP]
> 你可以根据你的喜好设置分辨率和颜色

现在，你的 Aegisub 主窗口应如图所示  

![image](https://github.com/user-attachments/assets/e3ee6c51-b3ab-4dda-8b4a-a02fb7aca0e8)

3. 开始打轴

> [!CAUTION]
> 尽管 Aegisub 有自动备份的功能，但还是别忘了定时保存你的文件

4. 打完一行的时间轴后，点击视频下方的 **播放当前行** 按钮，以预览你打的歌词
> [!NOTE]
> 这种预览方式类似于 Lyricify 的 Spotify 样式歌词界面

![image](https://github.com/user-attachments/assets/53d64e09-ac07-4e41-8c71-1dd43beef39e)

5. 若歌词有对唱和背景人声，你可以将说话人设置为“左”、“右”或“背”，AssandQrcConverter 会自动转换为相应属性的 Lyricify Syllable 歌词文件

![image](https://github.com/user-attachments/assets/8c922dab-7284-4ce7-b4fd-6b19a0f90b94)

6. 完成整首歌的打轴后，你可以将视频的进度条拖动到开始并点击播放按钮，这样可以完整地预览所有歌词

![image](https://github.com/user-attachments/assets/b835fd86-e474-4a48-bb61-3b96c6416706)

## 将完成的字幕文件转换为歌词文件
你可以直接将字幕文件拖动到 AssandQrcConverter 程序上以自动转换。若没有设置说话人，则会转换为 QRC 歌词文件，若设置了任意一个说话人，则会转换为 Lyricify Syllable 文件

![image](https://github.com/user-attachments/assets/6be437ae-ca03-43b0-bd1f-9266bd64e714)
