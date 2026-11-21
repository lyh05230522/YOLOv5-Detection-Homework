\# YOLOv5 目标检测作业



\## 环境与复现命令

\- \*\*环境\*\*：Anaconda (Python 3.9)，YOLOv5

\- \*\*训练命令\*\*：`python train.py --img 640 --batch 4 --epochs 50 --data D:/Doll\_Homework/data.yaml --weights yolov5s.pt --device cpu`

\- \*\*推理命令\*\*：`python detect.py --weights runs/train/exp2/weights/best.pt --source test.mp4 --conf-thres 0.3 --augment`



\## 数据规范说明

\- \*\*视频来源\*\*：自己录制

\- \*\*类别名称\*\*：xxy（共 1 类）

\- \*\*数据划分\*\*：截取 50 张图像，按 8:2 划分。训练集 40 张，验证集 10 张，验证集未混入训练集。

\- \*\*标注规范\*\*：使用 X-AnyLabeling 标注，YOLO HBB 格式，框紧贴目标。



\## 指标与问题

\- \*\*验证集指标\*\*：mAP@0.5 = 0.995（极佳）

\- \*\*遇到的问题\*\*：环境限制使用 CPU 训练。为防止内存溢出将 batch size 设为 4。推理时加入 `--augment` 提升视频检测框的平滑度。



\## 仓库文件说明

\- `result.mp4`：推理检测视频

\- `frame\_01/02/03.png`：视频截取帧

\- `best.pt`：训练产出的权重文件

