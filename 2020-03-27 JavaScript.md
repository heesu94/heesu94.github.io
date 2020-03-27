# 2020-03-27 JavaScript 스터디
## 이 스터디는 Youtube채널 생활코딩 Javascript 강의를 들으며 만든 정리내용입니다.


### 조건문
주어진 조건에 따라서 동작을 다르게 하는 것.  
# 

### if문 문법 

    if(true){                   // ( ) 안에 조건이 오며 조건이 될수있는 값은 boolean형이다.
        alert('result : true'); // 조건이 true이므로 { } 안의 내용 실행
    }                 

    if(false){
        alert('result : true'); // 조건이 false이므로 { } 안의 내용 실행 X
    }


### else  
if로는 좀 부족하다.. 아래 예제를 참고하자  

    if(true){
        alert(1);
    } else {
        alert(2);
    }

위의 예제는 조건문이 True일때 alert(1)을, False일때 else구문으로 진입하여 alert(2)를 수행한다는 코드다.  


### else if
다양하게 쓰일 수 있는 것이 장점이다. 예제를 참고하자  

    var a = 3;
    if(a===1){
        alert("a는 1 입니다");
    } else if (a===2) {
        alert("a는 2 입니다");
    } else if (a===3) {
        alert("a는 3 입니다");
    } else {
        alert("위의 조건문을 모두 성립하지 못했어요")
    }

a라는 변수에 3이라는 값을 대입시켰고, 위의 예제 조건문에 접근했다.  
a가 3이므로 첫 조건문인 a===1은 성립하지 못하여 다음 else if문으로 넘어갔다.  
넘어간 else if문 또한 조건문을 성립하지 못했고, 다음 else if문에서 조건문을 충족하고 안의 해당과정을 수행했다.  
  
위와 같이 좀더 다양한 조건을 검사할 수 있다.  



### 논리연산자 &&
좌항과 우항이 ***모두 참(true)***일때 참(True)이 된다.

    if(true && true){       // 좌항과 우항 모두 true 이므로 alert(1) 수행
        alert(1);
    }
    if(true && false){      // 우항이 false 이므로 alert(2) 수행X
        alert(2);
    }
    if(false && true){      // 좌항이 false 이므로 alert(3) 수행X
        alert(3);
    }
    if(false && false){     // 좌항과 우항 모두 false 이므로 alert(4) 수행 X
        alert(4);
    }  

예제를 보면 알수 있듯이, 하나라도 false가 있다면 그 조건문의 최종결과는 false 인 것이다.  

### 논리연산자 ||
좌항과 우항중 ***하나라도 참(true)***일때 참(True)이 된다. 예제를 참고해보자.

    if(true || true){       // 하나만 true 이면 되지만 좌항과 우항 모두 true 이므로 alert(1) 수행
        alert(1);
    }
    if(true || false){      // 우항이 false 이지만 좌항이 true 이므로 alert(2) 수행
        alert(2);
    }
    if(false || true){      // 좌항이 false 이지만 우항이 true 이므로 alert(3) 수행
        alert(3);
    }
    if(false || false){     // 좌항과 우항 모두 false 이므로 alert(4) 수행 X
        alert(4);
    }  


### 부정의 의미 !
***True를 False로, False를 True***로 바꾼다. not 연산자 라고도 한다.  
* !true -> false
* !false -> true  
### 

    if(!true && !true){     // false, false이므로 결과는 false
        alert(1);
    }
    if(!false && !true){    // true, false이므로 결과는 false
        alert(2);
    }
    if(!true && !false){    // false, true이므로 결과도 false
        alert(3);
    }
    if(!false && !false){   // true, true 이므로 결과는 true
        alert(4);
    }
    
### false로 간주되는 경우
위와같이 !는 부정을 의미하는데, 아래의 예제 처럼 False로 간주되는 경우도 있으니 참고바란다.  

    if(!''){
    alert('빈 문자열이다')
    }
    if(!undefined){
        alert('undefined');
    }

    var a;
    if(!a){
        alert('값이 할당되지 않은 변수'); 
    }
    if(!null){
        alert('null');
    }
    if(!NaN){
        alert('NaN');
    }


### 중첩 if문
if문 안에 다시 if문을 사용한 케이스이다. 예제를 참고하자.  

    var a = "1"
        if(a == 1){
            alert("1 맞아요")
            if( a === "1"){
                alert("자료형도 똑같은 문자 1이에요");
            } else {
                alert("자료형은 달랐던 숫자 1이에요");
            }
        } else {
            alert("숫자1도, 문자1도 아니네요");
        }

첫번째 if else문 조건을 검사한 결과가 True 이므로 if문으로 진입한다.  
if문 안에있는 두번째 if else문의 조건이 True 이므로 if문으로 진입하여 과정을 진행한다.  
  
위처럼 if문, if else문, else if문을 중첩하여 사용할 수 있다.  
  
#### ~~사실 논리연산자를 이용하면 되지만 중첩 할수 있다라는 것을 보여주기 위한 예제였다 ㅎㅎ~~

### 논리연산자 &&
좌항과 우항이 모두 참(true)일때 참이 된다.

숫자 연산도 가능하다.

    alert(1+1);          // 2
    alert(2-1);          // 1
    alert(4*2);          // 8

단 여기에서는 &는 나머지, /는 몫을 구하는 연산이다.

    alert(15%8);         // 7
    alert(15/8);         // 1



### ★ prompt()을 이용한 조건문 로그인 예제 ★
**prompt() 함수**는 사용자가 입력한 값을 가져와서 변수의 값으로 대입한다.

        id = prompt('아이디를 입력하세요');
        password = prompt('비밀번호를 입력하세요');

        if(id === 'Offwork' && password === 'qwer1234'){
            alert('로그인 완료!');
        } else if (id === 'Offwork') {
            alert('비밀번호가 다릅니다.');
        } else {
            alert('없는 아이디 입니다.');
        }

* prompt함수를 이용하여 입력한 값을 id, password 변수에 입력한다.
* 로그인을 완료하기 위해선 id와 password가 모두 같아야 하므로 if문의 조건을 위와같이 한다.
* 조건에 만족하지 않는 사항을 구현하기 위해 else if 조건에 아이디 확인을 묻는다.
* id가 같으면 비밀번호의 문제가 있었던 것이므로 이와 관련된 알람을 띄운다.
* 이 문제가 아니라면 아이디의 문제이므로 추가 조건문 필요 없이 else문만 이용하여 아이디 관련 알람을 띄운다.

### 조건문 Boolean형 대체
조건문에 사용하는 데이터 형중 꼭 Boolean형만 되는것은 아니다. 아래의 예제 참고

    if(0){          // 0은 false
        alert(1)
    }
    if(1){          // 0이 아닌값은 모두 true로 인식
        alert(2)
    }



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