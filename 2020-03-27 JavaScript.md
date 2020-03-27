# 2020-03-27 JavaScript 스터디
## 이 스터디는 Youtube채널 생활코딩 Javascript 강의를 들으며 만든 정리내용입니다.

-------------------------------------------------
## 조건문
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



### 반복문 while 문
소괄호 안의 조건이 참(true)면 중괄호 안의 코드 구간을 반복적으로 실행한다.  
조건이 거짓(false)이라면 반복문은 실행되지 않는다.  
소괄호 안의 조건을 변경하여 반복을 실행하다가 종료시킬 수 있다.  
* true라는 값을 넣어놓는 경우 무한루프에 빠지게 되니 주의하자  

    while (조건){
        반복해서 실행할 코드
    }


아래의 예제를 살펴보자

    var i = 0;                                      
    while(i < 10){                                  // i값이 10보다 작을때 반복문 진행
        document.write(i + '번째 <br />');          // 반복문 시행할 코드 시작, <br />은 한줄 띄움을 의미한다.
        i++                                         // i값이 1 증가한다는 코드로 i = i + 1과 같은 코드이다
    }

반복을 수행할 때 마다 i값을 1씩 증가시키므로 i값은 결국 10에 도달하여 조건이 false가 되므로 반복을 종료하는 구문이다.

### do while 문
while문 과는 반대로 do가 먼저 나오고 반복 코드를 진행 한 후 조건을 확인하는 경우이다.

    do {
        반복해서 실행할 코드
    } while (조건);

* while : 선 조건 후 반복, 한번도 반복하지 못할 수 있다.
* do while : 선 반복 후 조건, 무조건 한번은 반복한다.  
  
상황에 따라 while 혹은 do while 둘다 사용하므로 알아두도록 한다.  
  
### for 문

    for(초기화; 반복조건; 반복이 될 때마다 실행되는 코드){
        반복해서 실행될 코드
    }

for문의 순서는 다음과 같다.
1. 초기화
2. 반복조건
3. 반복해서 실행될 코드
4. 반복이 될 때마다 실행되는 코드  
  
아래의 예제를 참고한다.  

    for(var i = 0; i < 10; i++){
        document.write(i + '번째 <br />');  
    }

i가 0부터 9까지 조건문을 충족하여 총 10번을 반복한다.  
i가 10이 되었을 때는 조건문을 충족하지 못하므로 반복을 종료한다.  
  

### for문과 while문
흥미로운 점이 있다. 아래의 예제를 참고하자.

    //while문 코드
    var i = 0;                                               
    while(i < 10){                                  
        document.write(i + '번째 <br />');          
        i++                                         
    }

    //for문 코드
    for(var i = 0; i < 10; i++){
        document.write(i + '번째 <br />');  
    }

while문의 코드를 for문의 코드로 바꿀 수 있다. 
즉, 위의 예제에서는 for문과 while문의 코드가 사실상 같은 의미이다.  
자신이 사용하기 편한 반복문을 이용하자.