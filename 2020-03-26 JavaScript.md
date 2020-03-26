# 2020-03-26 JavaScript 스터디

## Javascript
프로그래밍 쪽으로 웹브라우저를 제어하는 역할을 하기 위한 도구 또는 언어.
웹서버를 동작하기 위한 도구.

브라우저에서 동작하는 자바스크립트는 클라이언트 사이드 스크립트 라고 함


### Node.js
웹브라우저를 제어 하기 위한 기술로써의 자바스크립트
웹서버를 제어하기 위한 기술로써의 자바스크립트  
# 

### 기본 자바스크립트 작성

    <!DOCTYPE html>
    <html>
        <head>
            <meta charset="utf-8"/>
        </head>
        <body>

            <script>
                alert('Hello world');  //자바 스크립트 코드
            </script>

        </body>
    </html>



### 크롬 개발자 도구 사용
* 단축키 : Ctrl + Shift + I  
# 


### javascript 사용시 실행 도구
* Visual Studio code  
# 


### 결과를 Chrome 브라우저로 띄우기
1. vs code의 확장(Extensions) 메뉴로 진입 한 후 "open in browser"를 다운로드 받는다.
2. 실행하고자 하는 파일에서 우클릭 후 사용자의 편의에 따라 "Open in Default Browser" 혹은 "Open In Other Browser"를 클릭하여 결과를 확인한다.  

    - "Open in Default Browser" 단축키 : Alt + B
    - "Open In Other Browser" 단축키 : Shift + Alt + B  

# 

### 숫자와 문자

"와 '가 붙지 않은 숫자는 숫자로 인식한다.

    alert(1);                // 숫자 1
    alert("1");              // 문자 1
    alert('1');              // 문자 1
      

숫자 연산도 가능하다.

    alert(1+1);          // 2
    alert(2-1);          // 1
    alert(4*2);          // 8

단 여기에서는 &는 나머지, /는 몫을 구하는 연산이다.

    alert(15%8);         // 7
    alert(15/8);         // 1


### Math 객체
* 수학에서 자주 사용하는 상수와 함수들을 미리 구현해 놓은 자바스크립트 표준 내장 객체
* 수학적인 상수와 함수를 위한 속성과 메서드를 가진 내장 객체

### Math 연산 이용

    alert( Math.pow(3,2) );      // 9, 3의 2제곱
    alert( Math.round(5.7) );    // 6, 5.7 반올림
    alert( Math.ceil(14.2) );    // 15, 14.2 올림
    alert( Math.floor(10.6) );   // 10, 10.6 내림
    alert( Math.sqrt(25) );      // 5, 25의 제곱근 
    alert( Math.random() );      // 0.0이상 1.0 미만인 값들 중 무작위로 뽑아 낸다.


### ★ 1 ~ 100 랜덤 숫자 뽑아내기 ★

##### 1. 랜덤 숫자를 뽑아내는 것이 먼저다

    Math.random();

##### 2. 0.xxxxx 형태가 되었으므로 100을 곱해준다.

    100 * Math.random();

##### 3. 위 상태는 100을 곱해주어 범위를 0.0이상 100.0미만으로 확장 시켰다.  
##### *단*, 이렇게 되면 100은 나올수가 없으므로 +1을 추가해야 한다.

    (100 * Math.random()) + 1; //1.0 이상 101.0미만 범위에서 무작위 숫자

##### 4. 이 상태에서 Math.floor만 해주어 소수점만 버린다. **완성!**

    Math.floor((100 * Math.random()) + 1);


-------------

#### 문자및 문자열은 아래와 같이 나타낸다.

    alert( "안녕하세요" );      // 안녕하세요
    alert( '안녕하세요' );      // 안녕하세요
    alert( "2" );               // 문자 2 

#### 문자열을 연결할 때는 문자열+문자열 형식을 이용한다.

    alert( "안녕하세요." + " 안녕히 계세요." ); 

#### 문자열안에 " 혹은 '를 넣고 싶다면 \" 혹은 \'를 이용한다. 

    alert( "게임 아이디를 만들었어요. 제 게임 아이디는 \"만병통치약퇴근\" 이에요."); 

#### typeof를 이용하여 데이터 타입을 알 수 있다. 

    alert( typeof 5 );           // number
    alert( typeof "안녕" );      // string


### 변수 선언
##### 값을 담는 그릇이라 생각하면 된다.
##### 값을 유지할 수도 있으며, 다른 값으로 바꿀 수도 있다.

    var a = 1;
    alert(a+1); // 2

    var b = 2;
    alert(b+2); // 4

    alert(a+b); // 3

    var a = 5;
    alert(a+b); // 7

    var a = "원해요", b = " 휴가"
    alert(a+b)  // 원해요 휴가


### 세미콜론(;)
하나의 구문이 끝났음을 명시적으로 나타내는 기호. 

    var a = 2, b = 3; //콤마(,)를 이용하여 변수를 여러개 선언한 후 마지막에 ;를 쓰는 형식도 있다.


## 자바스크립트 에서의 주석
##### 실제 코드에는 적용되지 않도록 하는 것.

    //   <-  한줄 단위 주석

    /*  */   <-  블록 단위 주석   



## 연산자
* 컴퓨터에게 지시하기 위한 기호

### 대입연산자 " = "
같다의 의미가 아닌 대입을 시킨다는 의미를 지닌 대입연산자 " = " 이다. 

    """
        a = 1       //우항인 1을 좌항인 a에 대입 시켜라
    """

### 비교연산자
주어진 값들을 같은지, 다른지, 큰지, 작은지 등 비교하는 것을 의미한다.  
결과는 비교결과가 참 이라는 "True"나 거짓 이라는 "False" 값을 반환한다.  

##### 이 같이 True, False 값을 반환하는 자료형을 불린(Boolean) 이라고 한다.

### 동등 연산자 ==
##### 좌항과 우항을 비교하여 서로 값이 같으면 True, 다르면 False가 된다.
##### * =은 대입연산자, ==은 동등연산자 이므로 주의!! 

    alert(1==1)             // True
    alert(1==3)             // False
    alert("one"=="one")     // True 
    alert("one"=="two")     // False

### 일치 연산자 ===
좌항과 우항이 '정확'하게 같을 때 True, 다르면 False가 된다.  
여기에서 '정확'하게 라는 말은 **"값도 같으면서 값의 자료형까지 같다"** 라는 말을 의미한다.  

    alert(1=='1');           // true  -> 숫자1과 문자1 즉, 자료형은 다르지만 서로 같은수를 표현했기 때문
    alert(1==='1');          // false -> 같은 수를 표현했더라고 자료형이 다르기 때문 

* 비슷하면 같다고 하는 == 보다는 정확하게 같다고 하는 ===를 사용하는 것을 추천!

### null과 undefined 비교
"a", "b", "c"가 String 타입 인것 처럼 null과 undefined도 타입이 있는데,  
null은 null타입 undefined는 undefined타입이다.  
즉, 각각 자체를 타입으로 한다.  
  
##### - undefined -> 프로그래머가 의도하지 않은 상태의 값이 없다.
##### - null ->  프로그래머가 의도적으로 부여한 상태의 값이 없다.  

    var a;
    alert(a); // undefined

    var a = null;
    alert(a); // null

    alert(undefined == null);   // True -> 프로그래머가 의도했던 의도하지 않았던 비었으므로 True
    alert(undefined === null);  // False -> 프로그래머의 의도한것과 의도하지 않은 것 까지 비교하므로 False



* 동등연산자는 숫자 1을 True로 간주, 숫자 1이 아닌수를 False로 간주  
* 일치연산자는 "True"가 아니면 모든 값 False로 간주  
##### 

    alert(true == 1);               //true
    alert(true === 1);              //false
    alert(true == '1');             //true
    alert(true === '1');            //false
 
    //참고
    alert(0 === -0);                //true
    alert(NaN === NaN);             //false, NaN은 0/0과 같은 연산의 결과로 만들어지는 특수한 데이터 형인데 숫자가 아니라는 뜻이다.



### !=
같지 않다라는 의미이며 ==와 정 반대이다

    alert(2!=1);            // true
    alert(1!=1);            // false
    alert("one"!="two");    // true
    alert("one"!="one");    // false

### !==
===의 반대이므로 "정확하게 같지않다"를 의미한다.  
  


### >, <, >=, <=
설명없이 예제를 통하여 확인한다.

    alert(10>20);       //false
    alert(10>1);        //true
    alert(10>10);       //false
    alert(10>=20);      //false 
    alert(10>=1);       //true 
    alert(10>=10);      //true



****************
TMI : 마크다운 문법도 같이 공부했습니다. ㅎㅎㅎㅎ ~~칭찬해주세요~~