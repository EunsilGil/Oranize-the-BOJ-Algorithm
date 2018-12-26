# Algorithm 분석

* 문제에 주어진 요건을 만족하는가?
* 정확하게 동작하는가?
* 사용법과 동작에 대한 documention
* function을 효과적으로 사용하였는가?
  * 기능적 module화

* readability
* storage 사용의 효율성
  * **Space complexity**로 분석
* 실행시간의 효율성
  * **Time complexity**로 분석



## Time complexity

#### Algorithm이 완료되는데 소요되는 시간의 양(수행 시간)

* Algorithm의 time efficiency를 분석

* 주어진 data의 규모(n)에 대하여 어떤 함수의 형대로 실행시간 복잡도가 증가하는가?

![시간복잡도 Big-O](https://t1.daumcdn.net/cfile/tistory/9941F43B5ABDBF4E1F)

​						[time complexity의 graph](https://www.google.com/imgres?imgurl=https://t1.daumcdn.net/cfile/tistory/9941F43B5ABDBF4E1F&imgrefurl=http://heekim0719.tistory.com/266&h=319&w=550&tbnid=Dcoko2K6HfNXIM:&q=%EC%8B%9C%EA%B0%84+%EB%B3%B5%EC%9E%A1%EB%8F%84&tbnh=116&tbnw=199&usg=AI4_-kSSQ2AjC91loMj0rFOUAgrzRVAukQ&vet=12ahUKEwiYrvPy1bzfAhUsSN8KHchgBf8Q_B0wFXoECAUQBg..i&docid=H7kYohV0S9xYsM&itg=1&sa=X&ved=2ahUKEwiYrvPy1bzfAhUsSN8KHchgBf8Q_B0wFXoECAUQBg)는 링크 인용

### 평가방법

-------

#### 점근적 표기법

* **Big O notation**

  * 주어진 알고리즘이 아무리 나빠도 비교하는 함수와 같거나 좋다.
    * 최악의 경우(Worst case)에도 이보다는 빠르다는 뜻

  ​	`ex) O(n^2)  > order of n^2`

* **Ω** **notation**

  * 주어진 알고리즘이 아무리 좋아도 비교하는 함수와 같거나 나쁘다.
* **Θ** **Notation**

  * 주어진 알고리즘이 아무리 좋아지거나 나빠지더라도 비교하는 함수의 범위 안에 있다.



Average case가 가장 이상적으로 보이지만, Algorithm이 복잡해 질수록 평균적인 경우를 구하는 것이 어려워지므로, **최악의 경우**로 알고리즘의 성능을 평가하는 것이 일반적이다. 

최악의 경우라는 것은 모든 경우라고 할 수도 있으므로, 신뢰도가 높아 **Big O notation**을 가장 일반적으로 사용한다.



### Big O natation

---

#### O(1) < O(logn) < O(n) < O(nlogn) < O(n^2) < O(n^3) < O(2^n) < O(n!)

|   n    |  O(n)  | O(logn) |
| :----: | :----: | :-----: |
|  500   |  500   |    9    |
| 5,000  | 5,000  |   13    |
| 50,000 | 50,000 |   16    |

* O(1)	    : 입력자료의 수에 관계없이 일정한 실행 시간을 갖는다.
* O(n)     : 입력자료의 수에 따라 선형적인 실행 시간이 걸린다.
* O(n^2) : 이중 loop내에서 입력자료를 처리한다.

### 표기방법

```markdown
ex)
	T(n) = n^2 + 2n + 9		=> O(n^2)
	T(n) = 5n^3 + 3n + 1 	=> O(n^3)
	T(n) = 6n + 4			=> O(n)
```

##### 최고차항의 차수가 Big O가 된다.

* 최고차항만 고려
* 계수는 무시

### 계산법

```C++
int main(){
	
	int T, n, arr[ARRAY_SIZE];
	
	cin >> T;
	
	/*A*/
	arr[0] = 0;
	arr[1] = 1;
	arr[2] = 2;
	arr[3] = 4;
	
	/*B*/
	for(int i = 4; i < ARRAY_SIZE; i++)
		arr[i] = arr[i-1] + arr[i-2] + arr[i-3];
	
    /*C*/
	while(T--){
		cin >> n;
		cout << arr[n];
	}
}
```

위 algorithm의 T(n) = 2n + 1 이므로,  (1중 loop문 2개 사용) 	**O(n)**이 된다.

