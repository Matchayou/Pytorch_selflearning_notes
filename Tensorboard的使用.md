---
date: 2025-07-20
tags:
  - 代码
  - pytorch
  - tensorboard
  - 训练记录
---
SummaryWriter 是 torch.utils.tensorboard 模块中的一个类，它提供了一个简单的接口，允许你将训练过程中的各种数据（如损失、精度、图像等）记录下来，并保存到指定的日志文件中。你可以将这些日志文件加载到 TensorBoard 中，实时可视化训练过程。
#### `writer.add_scalar():`
add_scalar() 方法用于记录标量数据（例如训练损失、准确率等），它有以下常用参数：<br>第一个参数是 tag，标签名，通常是你希望显示的变量名称（如 Loss/train 或 Accuracy）。<br>第二个参数是 scalar_value，即你想记录的标量值（如当前epoch的训练损失）。<br>第三个参数是 global_step，通常是当前的训练步数或 epoch 数。这将决定该标量值在 TensorBoard 中出现的位置。<br>目的：通过此方法，你可以将训练过程中逐步变化的标量数据（如损失、精度等）记录到日志中，以便在 TensorBoard 中观察其变化趋势

总结：记录训练过程并可视化



## 使用过程中的注意事项
1. 注意工作目录与logs目录
logs文件夹会与代码文件所在文件夹保存在一起，不一定是在你的终端工作目录下。必须保持一致，才能读取输入
2. 必须有writer.close()
3. writer的参数里，step是步数，同一tag下，不同步数可以展示不一样的内容
当 step 相同的时候，TensorBoard 会认为当前记录是 同一步骤的数据，通常不会覆盖新数据，而是保持在当前步骤的数据不变。
每次 step 值发生变化时，TensorBoard 会记录新的事件数据，并将新的图像数据写入该步骤下。每个步骤都会生成一个事件文件，其中包含该步骤的图像数据。
4. PIL的图片必须转换形式才能被writer.add_image读取，且从PIL到numpy，需要在add_image()中指定shape中每一个数字/维表示的含义。具体见writer.add_image的含义部分
### 代码笔记
![[tensorboard_use_notes 1.ipynb]]
