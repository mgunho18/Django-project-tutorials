# 파이썬 학습내용

***
> Python은?
- 범용 프로그래밍 언어
- 모든 데이터는 객체(object)인 객체 지향 인터프리터 언어 
- 동적 형 변환을 지원해 변수에 다양한 객체를 자유롭게 할당 가능

> Python 코드 권장 스타일
- pep-8 참조
- 들여쓰기는 4칸(스페이스) 사용

> 컴프리헨션(comprehension)
- 파이써닉한 코드를 작성하는 방법 중 하나
- 하나 이상의 이터레이터(iterator)로부터 파이썬의 자료구조를 만드는 compact한 방법 
- ex) ```list = [x for x in range(10) if x%2==0]```

>함수 
- Python에서 함수는 1급 객체
- 입력값(인자)을 주었을 때 어떤 결과값(반환)을 돌려줌
- 재사용이 가능하고 프로그램의 흐름을 일목요연하게 볼 수 있음
- 정의하기, 호출하기의 두 단계로 구성 

  ##### * 함수의 구성 요소
  - 순서 -> 인자, 위치인자, 키워드인자
  - 위치인자 : *args, 함수의 매개변수를 튜플로 묶는다, 인자 이름을 지정하지 않고 차례대로 나열
  - 키워드인자 : **kwargs, 함수의 매개변수를 딕셔너리로 묶는다, 인자 이름을 지정하고 차례대로 나 
 
> 모듈과 패키지
- 모듈은 파이썬 파일 
- 파이썬에서는 데이터 타입-> 선언문-> 함수 -> 모듈과 같은 계층구조가 존재
- 패키지는 파일 디렉토리, 여러 모듈이 포함될 수 있음, 디렉토리에 __ init __.py가 있으면 파이썬은 이 디렉토리를 패키지로 간주

> Decorator
- 데코레이터는 함수를 꾸며주는 함수
- 기존 함수에 기능을 추가, 새로운 함수를 만드는 역할
- 예시로 로그인을 했을 때 보여지는 페이지에 관한 함수를 작성할 때 decorator 사용
 ```
 def login_required(func):     
     def wrapper(*args, **kwargs):  
         user = kwargs.get('user', None)         
         if user is None:             
             raise Exception('login required')         
         return func(*args, **kwargs)  
     return wrapper
   
 @login_required 
 def change_password(*args,**kwargs): 
     print('change password')
 ```
> Iterator 
- 반복가능한 Iterable 객체 중 하나
- next() method로 순차적 반복

> Generator
- yield문이 있으면 Generator
-lazy factory로서 값 생산을 최후의 순간까지 연기해 실행 시 메모리를 줄이는 효과 
```
def fib():     
  prev, curr = 0, 1     
  while True:         
    yield curr         
    prev, curr = curr, prev + curr
``` 

