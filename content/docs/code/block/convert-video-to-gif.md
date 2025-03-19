---
title: "利用Python将视频转化为gif"
weight: 7
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

```python
from moviepy import VideoFileClip


def video_to_gif(video_path, output_path, start_time, end_time, fps=10, resize_ratio=1.0):
    """
    将视频片段转换为 GIF
    参数：
    video_path: 输入视频文件路径
    output_path: 输出 GIF 路径
    start_time: 开始时间（秒）
    end_time: 结束时间（秒）
    fps: 输出帧率（默认10）
    resize_ratio: 缩放比例（默认1.0）
    """
    try:
        # 加载视频并截取指定片段
        with VideoFileClip(video_path) as clip:
            subclip = clip.subclipped(start_time, end_time)

            # 调整尺寸（可选）
            if resize_ratio != 1.0:
                subclip = subclip.resized(resize_ratio)
            #
            # # 导出 GIF
            subclip.write_gif(output_path, fps=fps)

        print(f"GIF 已成功保存至：{output_path}")

    except Exception as e:
        print(f"处理过程中发生错误：{str(e)}")


# 使用示例
if __name__ == "__main__":
    video_to_gif(
        video_path=r'E:\youtube\test.mp4',
        output_path=r'E:\youtube\test.gif',
        start_time=200,  
        end_time=210,  
        fps=15,  
        resize_ratio=0.5 
    )
```

