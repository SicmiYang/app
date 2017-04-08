### 算法
假定有两个互不相关的过程:
1. 加载 
2. 滚动替换 

#### 加载
1. 有一个单独的方法Append([])导入数据
2. 将滚动替换过程锁定 (因为部分卡片高度未知)
3. 将新卡片append在底部
4. 新卡片都渲染完成后解锁滚动替换方法,并执行一次

#### 滚动替换

已知所有卡片的高度(假设卡片高度不一致),求解哪些卡片应该隐藏,哪些卡片应该显示
根据所有卡片的高度数组itemHeights[],屏幕高H,默认加载卡片数S,滚动距离y计算(p, q, H1, H3)

p: 开始的卡片  第一个top大于(y - H)的卡片
q: 结束的卡片  (q = p + S)
H1: 顶部替换盒子的高度 top(p) 
H3: 底部替换盒子的高度   sum( q + 1, N )