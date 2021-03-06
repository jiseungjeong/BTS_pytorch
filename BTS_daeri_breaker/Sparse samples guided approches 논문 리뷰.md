# Sparse samples guided approches ๋ผ๋ฌธ ๋ฆฌ๋ทฐ

<aside>
๐ก ์ถ์ฒ: 
[https://arxiv.org/abs/2011.04123](https://arxiv.org/abs/2011.04123) (arXiv computer science / computer vision and pattern recognition / Deep Learning based Monocular Depth Prediction: Datasets, Methods and Applications 2020 )
   
</aside>

# Depth Completion ์ด๋?

> LiDAR์ ๊ฐ์ **sparse depth ์ธก์ ์์ dense depth image๋ฅผ ์ถ์ **ํ๋ ๊ฒ, ์ฃผ๋ก ์ปฌ๋ฌ ์ด๋ฏธ์ง๋ก ํํ๋จ (์ถ์ฒ: [https://arxiv.org/abs/1903.05421](https://arxiv.org/abs/1903.05421) โ Depth Coefficients for Depth Completion, CVPR 2019 ๋ผ๋ฌธ)
> 

# Lagrange Multiplier Method์ ๊ดํ์ฌ

> ์ํ์  ์ต์ ํ์์, ๋ผ๊ทธ๋์ฃผ ์น์๋ฒ(Lagrange Multiplier Method)์ด๋, **์ ํ์กฐ๊ฑด ๋ฐฉ์ ์์ ๋ํ์ฌ ๊ทน๋๊ฐ ๊ทน์๊ฐ์ ์ฐพ๋ ๋ฐฉ๋ฒ์ด๋ค.** (์ถ์ฒ: [https://en.wikipedia.org/wiki/Lagrange_multiplier](https://en.wikipedia.org/wiki/Lagrange_multiplier) โ Lagrange multiplier ์ํคํผ๋์)
> 

![Untitled](/BTS_daeri_breaker/Sparse%20samples%20guided%20approches%20%EB%85%BC%EB%AC%B8%20%EB%A6%AC%EB%B7%B0/Untitled.png)

- max: f(x), subject to: g(x)=0

g(x)=0์ด๋ผ๋ ์ ํ์กฐ๊ฑด์์, f(x)์ ๊ทน๋๊ฐ/๊ทน์๊ฐ ์ ์ฐพ๊ธฐ ์ํด ์์ **Lagrangian function**์ ์ฌ์ฉํ๋ค.

![Untitled](/BTS_daeri_breaker/Sparse%20samples%20guided%20approches%20%EB%85%BC%EB%AC%B8%20%EB%A6%AC%EB%B7%B0/Untitled%201.png)

์ ์์ ์ด๋ฏธ์ง I์ sparse depth map S๋ฅผ ์ธ์๋ก ํ๋ฉฐ ์ธํ๋ก ํ๋ผ๋ฏธํฐํ๋ CNN ๋ชจ๋ธ ํจ์ f๊ฐ depth estimation function ์ญํ ์ ํ๋ค. ์ฆ ์ด ์์ ์ธํ์ ๊ฐ์ ๋ํด  ํจ์ f์ ๊ทน์๊ฐ์ ์ฐพ๊ธฐ ์ํด Lagrangian function์ ํ์ฉํ๋ ๊ฒ์ด๋ค.

# L1 Loss ์ ๊ดํ์ฌ

![Untitled](/BTS_daeri_breaker/Sparse%20samples%20guided%20approches%20%EB%85%BC%EB%AC%B8%20%EB%A6%AC%EB%B7%B0/Untitled%202.png)

Loss function์ L1 loss๋ฅผ ํ์ฉํ๋๋ฐ, ์ ์์์ ~D๋ f(I,S;theta)๋ฅผ ์๋ฏธํ๊ณ , D๋ real depth map์ ์๋ฏธํ๋ค.

- **L1 Loss**

![Untitled](/BTS_daeri_breaker/Sparse%20samples%20guided%20approches%20%EB%85%BC%EB%AC%B8%20%EB%A6%AC%EB%B7%B0/Untitled%203.png)

- **L2 Loss**

![Untitled](/BTS_daeri_breaker/Sparse%20samples%20guided%20approches%20%EB%85%BC%EB%AC%B8%20%EB%A6%AC%EB%B7%B0/Untitled%204.png)

# Early Fusion/Late fusion์ ๊ดํ์ฌ

[https://www.youtube.com/watch?v=J50zmyHT3Ms](https://www.youtube.com/watch?v=J50zmyHT3Ms)

โ ๊ฐ๋จํ early fusion๊ณผ late fusion์ ๊ดํด ์ค๋ชํจ.

![Untitled](/BTS_daeri_breaker/Sparse%20samples%20guided%20approches%20%EB%85%BC%EB%AC%B8%20%EB%A6%AC%EB%B7%B0/Untitled%205.png)

![Untitled](/BTS_daeri_breaker/Sparse%20samples%20guided%20approches%20%EB%85%BC%EB%AC%B8%20%EB%A6%AC%EB%B7%B0/Untitled%206.png)

# ์ฐธ๊ณ ํ  ์๋ฃ

- [https://paperswithcode.com/task/depth-completion](https://paperswithcode.com/task/depth-completion) โ papers with code depth completion
- [https://github.com/alexklwong/awesome-state-of-depth-completion#unsupervised-void-benchmark](https://github.com/alexklwong/awesome-state-of-depth-completion#unsupervised-void-benchmark) โ github awesome-state-of-depth-completion
- [https://www.kaggle.com/code/shuzhizhi/sparse-depth-completion-validation/data](https://www.kaggle.com/code/shuzhizhi/sparse-depth-completion-validation/data) โ depth completion data
