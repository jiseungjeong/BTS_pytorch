# Sparse samples guided approches 논문 리뷰

<aside>
💡 출처: 
[https://arxiv.org/abs/2011.04123](https://arxiv.org/abs/2011.04123) (arXiv computer science / computer vision and pattern recognition / Deep Learning based Monocular Depth Prediction: Datasets, Methods and Applications 2020 )
   
</aside>

# Depth Completion 이란?

> LiDAR와 같은 **sparse depth 측정에서 dense depth image를 추정**하는 것, 주로 컬러 이미지로 표현됨 (출처: [https://arxiv.org/abs/1903.05421](https://arxiv.org/abs/1903.05421) → Depth Coefficients for Depth Completion, CVPR 2019 논문)
> 

# Lagrange Multiplier Method에 관하여

> 수학적 최적화에서, 라그랑주 승수법(Lagrange Multiplier Method)이란, **제한조건 방정식에 대하여 극대값 극소값을 찾는 방법이다.** (출처: [https://en.wikipedia.org/wiki/Lagrange_multiplier](https://en.wikipedia.org/wiki/Lagrange_multiplier) → Lagrange multiplier 위키피디아)
> 

![Untitled](/BTS_daeri_breaker/Sparse%20samples%20guided%20approches%20%EB%85%BC%EB%AC%B8%20%EB%A6%AC%EB%B7%B0/Untitled.png)

- max: f(x), subject to: g(x)=0

g(x)=0이라는 제한조건에서, f(x)의 극대값/극소값 을 찾기 위해 위의 **Lagrangian function**을 사용한다.

![Untitled](/BTS_daeri_breaker/Sparse%20samples%20guided%20approches%20%EB%85%BC%EB%AC%B8%20%EB%A6%AC%EB%B7%B0/Untitled%201.png)

위 에서 이미지 I와 sparse depth map S를 인자로 하며 세타로 파라미터화된 CNN 모델 함수 f가 depth estimation function 역할을 한다. 즉 이 식은 세타의 값에 대해  함수 f의 극소값을 찾기 위해 Lagrangian function을 활용하는 것이다.

# L1 Loss 에 관하여

![Untitled](/BTS_daeri_breaker/Sparse%20samples%20guided%20approches%20%EB%85%BC%EB%AC%B8%20%EB%A6%AC%EB%B7%B0/Untitled%202.png)

Loss function은 L1 loss를 활용하는데, 위 식에서 ~D는 f(I,S;theta)를 의미하고, D는 real depth map을 의미한다.

- **L1 Loss**

![Untitled](/BTS_daeri_breaker/Sparse%20samples%20guided%20approches%20%EB%85%BC%EB%AC%B8%20%EB%A6%AC%EB%B7%B0/Untitled%203.png)

- **L2 Loss**

![Untitled](/BTS_daeri_breaker/Sparse%20samples%20guided%20approches%20%EB%85%BC%EB%AC%B8%20%EB%A6%AC%EB%B7%B0/Untitled%204.png)

# Early Fusion/Late fusion에 관하여

[https://www.youtube.com/watch?v=J50zmyHT3Ms](https://www.youtube.com/watch?v=J50zmyHT3Ms)

→ 간단히 early fusion과 late fusion에 관해 설명함.

![Untitled](/BTS_daeri_breaker/Sparse%20samples%20guided%20approches%20%EB%85%BC%EB%AC%B8%20%EB%A6%AC%EB%B7%B0/Untitled%205.png)

![Untitled](/BTS_daeri_breaker/Sparse%20samples%20guided%20approches%20%EB%85%BC%EB%AC%B8%20%EB%A6%AC%EB%B7%B0/Untitled%206.png)

# 참고할 자료

- [https://paperswithcode.com/task/depth-completion](https://paperswithcode.com/task/depth-completion) → papers with code depth completion
- [https://github.com/alexklwong/awesome-state-of-depth-completion#unsupervised-void-benchmark](https://github.com/alexklwong/awesome-state-of-depth-completion#unsupervised-void-benchmark) → github awesome-state-of-depth-completion
- [https://www.kaggle.com/code/shuzhizhi/sparse-depth-completion-validation/data](https://www.kaggle.com/code/shuzhizhi/sparse-depth-completion-validation/data) → depth completion data
