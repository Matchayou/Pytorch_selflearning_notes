### 官网介绍
[https://docs.pytorch.org/vision/0.9/models.html]()
```python
_class_torch.utils.data.DataLoader(_dataset_, _batch_size=1_, _shuffle=None_, _sampler=None_, _batch_sampler=None_, _num_workers=0_, _collate_fn=None_, _pin_memory=False_, _drop_last=False_, _timeout=0_, _worker_init_fn=None_, _multiprocessing_context=None_, _generator=None_, _*_, _prefetch_factor=None_, _persistent_workers=False_, _pin_memory_device=''_, _in_order=True_)
```

dataset参数为数据集，其他参数多为有默认值的
### 参数介绍
batch_size 每次抓牌时抓几张
shuffle 洗牌时候，排序与上一次是否一样，一般设置为true（随机排序），默认为false（与上一次一样）
num_workers 设置加载进程，大于0时在win系统运行有错误
drop_last ：举例，100张牌除以3，余1张牌，此时决定这张牌是否舍去
eg.
batch_size =4时，就是从dataset中取四个数据
![[Pasted image 20250728204905.png]]
img0，1，2，3打包为imgs,target0,1,2,3打包为targets，然后返回imgs,targets
### 代码笔记
![[dataloader_testnotes.ipynb]]