# OpenCV로 Depth_map 추출하기

# Depth Maps in OpenCV Python (StereoVision)

<aside>
💡 출처: [https://www.youtube.com/watch?v=jhOTm3MZDaY](https://www.youtube.com/watch?v=jhOTm3MZDaY)

</aside>

![Untitled](/BTS_daeri_breaker/OpenCV%EB%A1%9C%20Depth_map%20%EC%B6%94%EC%B6%9C%ED%95%98%EA%B8%B0/Untitled.png)

Disparity는 위와 같이 계산된다.

위쪽 사진 (left camera) 아래쪽 사진(right camera)

![Untitled](/BTS_daeri_breaker/OpenCV%EB%A1%9C%20Depth_map%20%EC%B6%94%EC%B6%9C%ED%95%98%EA%B8%B0/Untitled%201.png)

![Untitled](/BTS_daeri_breaker/OpenCV%EB%A1%9C%20Depth_map%20%EC%B6%94%EC%B6%9C%ED%95%98%EA%B8%B0/Untitled%202.png)

![Untitled](/BTS_daeri_breaker/OpenCV%EB%A1%9C%20Depth_map%20%EC%B6%94%EC%B6%9C%ED%95%98%EA%B8%B0/Untitled%203.png)

```python
import numpy as numpy
import cv2 as cv
from matplotlib import pyplot as plt 

left_image=cv.imread('test_l.png', cv.IMREAD_GRAYSCALE)
right_image=cv.imread('test_r.png', cv.IMREAD_GRAYSCALE)

# left_image=cv.imread('item1_l.png', cv.IMREAD_GRAYSCALE)
# right_image=cv.imread('item2_r.png', cv.IMREAD_GRAYSCALE) ...

stereo=cv.StereoBM_create(numDisparities=0, blockSize=17)
# For each pixel algorithm will find the best disparity from 0
# Larger block size implies smoother, though less accurate disparity map
depth=stereo.compute(left_image, right_image)

cv.imshow("Left", left_image)
cv.imshow("right", right_image)

plt.imshow(depth)
plt.axis('off')
plt.show()
```

blockSize=21 (아래 사진)

![Untitled](/BTS_daeri_breaker/OpenCV%EB%A1%9C%20Depth_map%20%EC%B6%94%EC%B6%9C%ED%95%98%EA%B8%B0/Untitled%204.png)