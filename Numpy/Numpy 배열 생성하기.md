## Numpy 배열 생성하기

넘파이(Numpy)는 파이썬 기반의 고성능의 수치 계산을 위한 라이브러리이다.

넘파이는 계산의 기반이 되는 배열(array)을 간편하게 생성할 수 있는 여러 가지 함수들을 제공하고 있다.

<hr>

**넘파이 배열을 생성하는 함수들**

- **np.array(list):** list를 넘파이 배열로 생성
- **np.zeros(shape):** 0 이 들어있는 배열 생성
- **np.ones(shape):** 1 이 들어있는 배열 생성
- **np.empty(shape):** 초기화가 없는 값으로 배열을 반환
- **np.arange(n ,m):** arange 함수를 이용하여 배열을 생성
- **np.linspace(start ,end, num-points):**linspace 함수를 이용하여 시작점과 끝 사이에 균일한 값을 주는 배열을 생성
- **np.random.randint(start end, array-size):** radom.randit함수를 이용하여 랜덤값으로 배열을 생성

```python
from elice_utils import EliceUtils
import numpy as np

elice_utils = EliceUtils()


def main():
	
    print("Array1: 파이썬 리스트로 만들어진 정수형 array")
    array1 = np.array([1,2,3,4,5])
    print("데이터:", array1)
    print("array의 자료형:", type(array1))
    print("dtype:", array1.dtype, "\n")

    print("Array2: 파이썬 리스트로 만들어진 실수형 array")
    array2 = np.array([0.1,0.2,0.3])
    print("데이터:", array2)
    print("dtype:", array2.dtype, "\n")

    print("Array3: 0으로 10개 채워진 정수형 array")
    array3 = np.zeros((1,10))
    print("데이터:", array3)
    print("dtype:", array3.dtype, "\n")

    print("Array4: 1으로 채워진 3x5형태 실수형 array")
    array4 = np.ones((3,5))
    print("데이터:", array4)
    print("dtype:", array4.dtype, "\n")

    print("Array5: 0부터 9까지 담긴 정수형 array")
    array5 = np.arange(0,10)
    print("데이터:", array5, "\n")

    print("Array6: 0부터 1사이에 균등하게 나눠진 5개의 값이 담긴 array")
    array6 = np.linspace(0,1,5)
    print("데이터:", array6, "\n")

    print("Array7: 0부터 10사이 랜덤한 값이 담긴 2x2 array")
    array7 = np.random.randint(0,10,(2,2))
    print("데이터:", array7, "\n")
    
    
if __name__ == "__main__":
    main()
```

```py
# 결과값
Array1: 파이썬 리스트로 만들어진 정수형 array
데이터: [1 2 3 4 5]
array의 자료형: <class 'numpy.ndarray'>
dtype: int64 

Array2: 파이썬 리스트로 만들어진 실수형 array
데이터: [0.1 0.2 0.3]
dtype: float64 

Array3: 0으로 10개 채워진 정수형 array
데이터: [[0. 0. 0. 0. 0. 0. 0. 0. 0. 0.]]
dtype: float64 

Array4: 1으로 채워진 3x5형태 실수형 array
데이터: [[1. 1. 1. 1. 1.]
 [1. 1. 1. 1. 1.]
 [1. 1. 1. 1. 1.]]
dtype: float64 

Array5: 0부터 9까지 담긴 정수형 array
데이터: [0 1 2 3 4 5 6 7 8 9] 

Array6: 0부터 1사이에 균등하게 나눠진 5개의 값이 담긴 array
데이터: [0.   0.25 0.5  0.75 1.  ] 

Array7: 0부터 10사이 랜덤한 값이 담긴 2x2 array
데이터: [[8 4]
 [2 9]] 
```

<hr>

## Numpy 배열의 특정요소 추출하기

넘파이 배열을 사용할 때, 행렬 전체가 아닌 특정 성분 또는 구간 만을 사용할 때가 있다.

이에 대하여 넘파이는 특정 성분 또는 구간을 추출하는 편리한 기능을 제공하고 있다.

이러한 배열의 특정 성분들을 출력하는 것을 실습을 통해서 익혀보자.

<hr>

**배열을 인덱싱/슬라이싱 하는 함수들**

- **ndarray[n, m]:** n 행 m 열의 원소를 추출.
- **ndarray[n, :]:** n 행을 추출.
- **ndarray[:, m]:** m 열을 추출.

```python
import numpy as np

array_1 = np.array([[4,2,5],[5,3,2],[9,1,2]])

#1. 배열 array_1에 대하여 2행 3열의 원소를 추출하세요. 
element_1 = array_1[1,2]
print("2행 3열의 원소는 ", element_1, " 입니다.")

#2. 배열 array_1에 대하여 3행을 추출하세요. 
row_1 = array_1[2,:]
print("3행은 배열 ", row_1, " 입니다.")

#3. 배열 array_1에 대하여 2열을 추출하세요. 
col_1 = array_1[:,1]
print("2열은 배열 ", col_1, " 입니다.")

#4. x의 1행과 3행을 바꾼 행렬을 만들어보세요. 
row_1 = array_1[2,:]
row_2 = array_1[1,:]
row_3 = array_1[0,:]
y = np.vstack([row_1,row_2,row_3])
print(y)
```

```py
# 결과값
2행 3열의 원소는  2  입니다.
3행은 배열  [9 1 2]  입니다.
2열은 배열  [2 3 1]  입니다.
[[9 1 2]
 [5 3 2]
 [4 2 5]]
```

