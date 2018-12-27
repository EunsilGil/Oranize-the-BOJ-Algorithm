# Dynamic Programming

## 설명

####  작은 문제의 답을 조합해서 큰 문제의 답을 푼다.

* Dynamic Program은 최적화 문제를 연구하는 수학이론에서 출발
* recursion 호출 시, 반복적으로 계산되는 것들의 계산 횟수를 줄이기 위해 이전에 계산했던 값을 저장해 두었다가 재사용하는 방법

#### memoization

* program이 동일한 계산을 반복해야 할 때, 이전에 계산한 값을 메모리에 저장함으로써 동일한 계산의 반봅 수행을 제거하여 program의 time complexity를 향상시키는 기술
* DP에서 중복된 계산을 막기 위해 **반복되는 결과 값 배열에 저장**한 뒤, **다음에 계산이 필요할 때**, 저장된 값을 불러와서 **중복을 없애는**데에 사용된다.

#### 구현 방법

* Top-Down (memoization)

  1. 문제를 작은 문제로 나눈다.

  2. 작은 문제들을 푼다.

  3. 작은 문제들의 답으로 전체 문제를 푼다.

     ```c++
     /* 일반적인 recursion */
     int fib(int n){
         if (n < 2)
         	return 1;
         return fib(n-1) + fib(n-2);
     }
     
     /* memoization을 적용한 top-down DP algorithm */
     int fib(int fib){
         if(n < 2)
             return 1;
         if(!memo[n])
             return memo[n];
         memo[n] = fib(n-1) + fib(n-2);
         return memo[n];
     }
     ```

* Bottom-Up

  1. 가작 작은 문제부터 푼다.

  2. 문제의 크기를 점점 크게 만들어서 전체 문제를 푼다.

     ```c++
     int fib(int n){
         memo[0] = 0;
         meme[1] = 1;
         for(int i = 2; i <= n; i++)
             	memo[i] = memo[i-1] + memo[i-2];
         return memo[n];
     }
     ```

* guide line

  * 몇 차원 DP를 설정할 것인가?
  * 각각의 차원이 어떤 의미를 가지는가?
  * DP 값이 어떤 의미인가?
  * 여러개의 DP값이 존재한다면, 그들은 서로 어떤 연관성을 가지고 있는가?

## more about DP

* DP는 최적값을 구할 때 주로 사용한다.
* DP를 할 때에는 이미 계산 한 것을 다시 계산하지 않기 위해서 초기화에 신경을 써야한다.
* recursion DP는 점화식 그대로 호출이 되기 때문에 형식이나 순서에 얽매이지 않는다는 장점이 있다.
* loop 문 DP는 시간이 적게 걸린다는 장점이 있다.



## 예제

* BOJ 9095번 문제를 통해 DP를 어떻게 활용할 수 있는지 더욱 자세히 알아보자.
  * BOJ 9095번 문제는 **정수 n이 주어졌을 때, n을 1, 2, 3의 합으로 나타내는 경우의 수**를 구하는 program을 구현하는 문제이다.
  * 접근 방법
    * 1, 2, 3을 더하는 순서에 따라 다른 방법으로 인정하기 때문에 모든 경우를 한번씩 훑어야 한다.
      * recursion
    * base case : 0, 1, 2, 3 총 4가지 수에 대한 경우의 수
      * dynamic programming
    * general case : 0, 1, 2, 3으로 n을 만드는 방법의 수
      * f(n) = f(n-1) + f(n-2) + f(n-3)      (n>=4)

```C++
#include <iostream>
#include <iomanip>
#include <string>
using namespace std;

#define ARRAY_SIZE 11

int main(){
	
	int T, n, arr[ARRAY_SIZE];
	
	cout << "\nEnter the 'T' value : ";
	cin >> T;
	
	/*Base Case*/
	arr[0] = 0;
	arr[1] = 1;
	arr[2] = 2;
	arr[3] = 4;
	
	/*General Case*/
	for(int i = 4; i < ARRAY_SIZE; i++)
		arr[i] = arr[i-1] + arr[i-2] + arr[i-3];
	
	while(T--){
		cout << "\nEnter the 'n' value : ";
		cin >> n;
		cout << "The result is " << arr[n];
	}
}
```

![BOJ_9095](C:\Users\eunsi\Desktop\BOJ_9095.jpg)



## Reference

[동적 프로그래밍, Dynamic programming](https://www.zerocho.com/category/Algorithm/post/584b979a580277001862f182)

[DP, norman3's github](https://norman3.github.io/rl/docs/chapter02.html)

[위키피디아, 메모이제이션](https://ko.wikipedia.org/wiki/%EB%A9%94%EB%AA%A8%EC%9D%B4%EC%A0%9C%EC%9D%B4%EC%85%98)

[all about coding, 동적계획법](http://coding-all.tistory.com/2)

