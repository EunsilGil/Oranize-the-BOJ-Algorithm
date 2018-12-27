# C++ STL

#### Standard Template Library

표준 C++ 라이브러리로, program에 필요한 자료구조와 알고리즘을 template으로 제공하는 library

----

### 구성

----

* containers 
  * data를 저장하는 공간을 구성
  * class template으로 구현되어 있다.
* iterators 
  * container의 원소를 가리키는 변수 (pointer와 유사)
  * 가리키는 원소에 접근하여 순회기능을 한다.
* algorithms 
  * container의 원소에 적용가능한 function
  * 정렬, 삭제, 검색, 연산 등을 해결하는 일반화된 방법을 제공한다.
* function object
  * 함수처럼 동작하는 객체
  * operator() 연산자를 오버로딩한 객체이다.
  * container와 algorithm등에 client 정책을 반영하게 한다.
* container adaptor
  * 구성요소의 interface를 변경해 새로운 interface를 갖는 구성요소로 변경하는 역할을 한다.
  * stack과 queue등이 이에 속한다.
* allocator
  * container의 메모리 할당 정책을 캡슐화한 class 객체
  * 모든 container는 자신만의 할당기를 가지고 있다.

### container 의 member 함수

----

``` markdown
p1 = a.begin();			//첫 원소의 위치
p2 = a.end();			//끝 원소의 다음 위치

* 통상적으로 p1부터 p2까지를 가리킬때는 [p1,p2)로 나타낸다. * 
```



### 자주 사용하는 STL

----

#### 1. Stack

```C++
#include <stack>

stack<int> s1;			//empty integer stack 's1'생성

/* Member 함수 */
s1.push(3);				//원소 추가
s1.push(5);
s1.pop();				//원소 삭제(void type)

n = s1.top();			//내용변화 없이 top원소 읽기

n = s1.size();			//현재 원소의 갯수
if(s1.empty()) {		//empty test(booloan type)
    
}
```

#### 2. Queue

```c++
#include <queue>

queue<int> q1;			//empty interger queue 'q1'생성

/* Member 함수 */
q1.push(3);				//원소 추가
q1.push(6);		
q1.pop();				//원소 삭제(void type)

x = q1.front();			//현재 queue의 첫 원소 읽기
x = q1.back();			//현재 queue의 끝 원소 읽기

x = q1.size();			//현재 원소의 갯수 
if(q1.empty()){			//empty test(boolian type)
    
}
```

#### 3. Vector

* dynamic array
* 원소 갯수의 제약이 없다.

```c++
#include <vector>

vector<int> a;
vector<mynode> a1;		//user가 정의한 node 구조체를 저장하는 vector 'a1'생성

vector<int> b(a);		//현재 vector a의 내용과 완전히 동일한 vector 'b'생성
vector<int> c(5);		//길이가 5인 vector 'c' 생성

/* Member 함수 */
a.push_back(3);			//끝 원소로 추가
a.pop_back();			//끝 원소 삭제
a.size();
if(a.empty()){
    
}
c[1] = 2;				//이미 공간이 확보되어 있는 vector에 한해 []연산 지원
c.clear();				//모든 원소를 삭제하고 초기 empty 상태가 됨
c.resize(10);			//vector 'c'의 크기를 10으로 재설정
b.front();				//첫 원소 읽기
b.back();				//끝 원소 읽기

b.insert(p,t);			//p : 넣을 위치(iterator), t : 넣을 값
						//p의 앞쪽에 t를 추가(list에서도 사용 가능)
b.insert(p,n,t);		//p의 앞쪽에 n개의 t를 추가
b.insert(p,p1,p2);		//p의 앞쪽에 [p1,p2) 볌위의 data를 추가
```

#### 4. List

* 이중 연결 list로 구현
  * 순차적 접근만 가능하다.
* 원소가 node단위로 저장된다.

``` c++
#include <list>

list<int> x;

/* Member 함수 */
x.push_back(3);			//끝 원소로 추가
x.push_front(7);		//첫 원소로 추가
x.pop_front();			//첫 원소 삭제

x.sort();				//ascending sort
x.reverse();			//원소를 역순으로 재구성
x.merge(y);				//2개의 ordered list 'x'와 'y'를 merge하여 'x'로 생성
						//이후 'y'는 empty가 되며, unordered list의 경우 error
x.remove(x);			//list 'a'의 원소들 중 x 값을 갖는 원소를 모두 삭제
```



### Iterator

* container의 원소를 가리키는 변수
* C 의 pointer와 유사한 역할을 한다.

```c++
list<int> a;
list<int>::iterater p;

for(p=a.begin(); p!=a.end(); p++)
    cout << *p << "\n";				//list에 속한 모든 원소를 출력
```
