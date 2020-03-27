# 2020-03-27 JavaScript 스터디
## 이 스터디는 Youtube채널 생활코딩 Javascript 강의를 들으며 만든 정리내용입니다.

## 조건문
주어진 조건에 따라서 동작을 다르게 하는 것.  

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
#### 

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

    for(초기화; 반복조건; 반복이 될 때마다 실행되는 코드 ){
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

### 반복문을 사용하는 이유
아래의 코드를 살펴보자

    document.write('1번째 <br />');  
    document.write('2번째 <br />');  
    document.write('3번째 <br />');  
    document.write('4번째 <br />');  
    document.write('5번째 <br />');  
    document.write('6번째 <br />');  
    document.write('7번째 <br />');  
    document.write('8번째 <br />');  
    document.write('9번째 <br />');  
    document.write('10번째 <br />');

**~~보기만해도 벌써 귀찮다.~~**  
이렇게 반복해서 써야하는 경우가 있는데 이때 반복문을 사용하는 것이다.  

    for(var i = 0; i < 10; i++){
        document.write(i + '번째 <br />');  
    }

위의 10줄코드가 반복문 사용으로 3줄로 확 줄었다.  
이는 간단한 예시일 뿐, 실제로 더 복잡한 환경에서도 반복문을 자주 이용한다.


### break
반복작업을 중간에 중단시키고 싶을때 break를 이용한다.

    for(var i = 0; i < 10; i++){
        if(i === 5) {
            break;
        }
        document.write(i + '번째 <br />');  
    }   

이 코드의 결과는 아래와 같다. 

    0번째
    1번째
    2번째
    3번째
    4번째

i가 5일때 반복문을 빠져나와 이후 작업은 진행하지 않았기 때문에 5번째 ~ 9번째 출력은 나타나지 않았다.


### continue
break와는 전혀 다른 제어 명령이다. 이부분은 예제를 먼저 참고하자

    for(var i = 0; i < 10; i++){
        if(i === 5) {
            continue;
        }
        document.write(i + '번째 <br />');  
    }   

이 코드의 결과는 아래와 같다.

    0번째
    1번째
    2번째
    3번째
    4번째
    6번째
    7번째
    8번째
    9번째

i가 5일때를 제외하고는 모든 반복문이 이루어졌다.
즉, 현재 진행중이었던 i는 넘어가고 다음 i가 시작됐다는 것이다.

### break 와 continue
- break : 반복진행 중에 break문을 만나면 반복을 아예 종료한다.
- continue : 반복진행 중에 continue를 만나면 현재진행 중인 반복은 넘어가고 다음 반복을 진행한다.


### 함수 function
하나의 로직을 재실행 할 수 있도록 하는것으로, 코드의 재사용성을 높여준다.

    function 함수명( [인자...[,인자]] ){
        코드
        return 반환값
    }

반복문에서 사용했던 예제들중 하나를 function으로 묶어 사용한다면 어떻게 될까? 아래의 예제를 확인해보자.

    <script>

        function forLoopBreak(){
            for(var i = 0; i < 10; i++){
                if(i === 5) {
                    break;
                }
                document.write(i + '번째 <br />');  
            }   
        }

        forLoopBreak();

    </script>

결과는 for문에서 사용한 예제와 똑같다.

    0번째
    1번째
    2번째
    3번째
    4번째

반복문을 4번 사용하는 것 보다 반복문을 함수에 한번 정의해준 후, 함수만 호출하면 편리하다.


### return
입력된 값을 연산해서 출력하는 것이 함수의 기본적인 역할이다.  
함수 내에서 사용한 return은 return 뒤에 오는 값을 함수의 결과로 반환함과 동시에 함수를 종료시킨다.

    function getTest1(){
        return "hihi";
    }

    function getTest2(){
        return "hello";
    }

    document.write(getTest1() + '<br\>');
    document.write(getTest2() + '<br\>');

return값이 있는 두 함수를 정의 한 후 출력하는 코드이다. 결과는 아래와 같다.

    hihi
    hello

두 함수를 출력한 결과, 함수내에서 문자열을 return한 결과가 나왔다.  
위에서 언급했던 것 처럼 한번 return을 하면 함수를 종료시키는 역할도 한다.    

    function getTest(){
        return "hello";
        return "my name";
        return "is Steve";
    }
    document.write( getTest() );    //hello


### 인자가 있는 function()
인자(argument)는 함수로 유입되는 입력값을 의미한다.  
어떤 값을 인자로 전달하느냐에 따라 함수가 반환하는 값이나 메소드의 동작 방법을 다르게 할 수 있다.

    function getTest(arg){                  
        return arg;
    }
 
    document.write( getTest(1) + "<br \>");    // 1
    document.write( getTest(2) + "<br \>");    // 2


getTest 다음 소괄호안에 1과 2라는 인자를 주었고, 이 인자값이 함수 정의시 변수 arg로 전달된다.
  
인자 값을 복수로 줄 수 있다. 아래의 예제를 확인해보자

    function getSumTest(arg1, arg2){                
        return arg1 + arg2;
    }

    document.write( getSumTest(10, 20) + "<br\>");    // 30

인자 10과 20을 arg1, arg2로 넘겨주어 arg1에는 10, arg2에는 20이 들어가있는 상태이다.  
후에 arg1 + arg2가 진행되고 난 값을 return한 결과를 나타냈다.

### 다른 함수 정의 방법

    var Test = function(){
        for (i = 0; i < 5; i++) {
            document.write(i + "<br\>");
        }
    }

    Test();

위처럼 함수를 변수에 대입할 수도 있다. 이때 변수를 사용하려면 변수(); 형식으로 호출하면 된다.

### 배열 array
여러개의 데이터를 하나의 변수에 담아서 관리할 수 있는 방법이다.  
변수엠 담은 배열을 색인(index)을 통하여 원하는 원소를 추출할 수도 있다.

    var names = ["Jane", "Love", "James"];
    
    document.write(names + "<br>");         // Jane,Love,James

    document.write(names[0] + "<br>");      // Jane
    document.write(names[1] + "<br>");      // Love
    document.write(names[2] + "<br>");      // James

색인은 0 *(0이 첫번째)* 부터 시작하는데, 첫번째 원소를 가져오고 싶으면 배열변수[0] 을 작성하면 된다.
다른 원소들을 도 마찬가지이다.

### 배열과 반복문의 조화
위의 예제는 원소를 각각 뽑아내고 있는데, 이 부분 또한 반복문을 이용하는 것이 좋다.

    function getNames(){    
        return ["Jane", "Love", "James"];       // 사용자정의 함수 return 값으로 배열을 주었다.
    }

    var getNames = getNames();                  // 새로운 변수에 함수를 대입하는데 return값인 배열이 대입되는 셈이다.
    for (i = 0; i < getNames.length; i++) {     // 배열의 크기가 3이므로, i < 3이나 다름없다.
        document.write(getNames[i] + "<br>");   
    }

length는 배열의 크기를 알려준다. 형식은 **배열.length** 이다.  
즉, getNames 변수는 배열 값이 들어갔으므로, 배열의 크기인 3이 반환된다.  
i가 0, 1, 2 일때 반복하므로 3번 반복하며, getNames의 i번째를 추출한다.   
(결과 확인)  

    Jane
    Love
    James

### 배열 제어
배열은 복수의 데이터를 효율적으로 관리, 전달하기 위한 목적으로 고안된 데이터 타입이다.  
따라서 데이터의 추가/수정/삭제와 같은 일을 편리하게 할 수 있도록 돕는 다양한 기능이 있다.

### array.push 
기존의 배열 끝에 원소를 추가하는 방법이다.

    var array = ['a', 'b', 'c', 'd', 'e'];
    document.write(array + "<br>");         // a,b,c,d,e
    array.push('f', 'g');                   // f와 g 추가
    document.write(array + "<br>");         // a,b,c,d,e,f,g

push함수는 원래의 배열에 원소를 추가하므로, array 변수자체가 f,g가 들어간 변수로 바뀐다.  
이것이 이해되지 않는다면 아래의 concat함수와 비교해보면 된다.

### array.concat
push와 똑같은듯 하지만 미세하게 다르다. 예제를 참고하자

    var array = ['a', 'b', 'c', 'd', 'e'];
    document.write(array + "<br>");         // a,b,c,d,e
    array.concat(['f', 'g']);               // f와 g 추가
    document.write(array + "<br>");         // a,b,c,d,e

array.push를 array.concat으로 바꾼어 원소를 추가 해줬을 뿐인데 결과는 f와 g가 들어가지 않았다.  
이러한 이유는 concat을 이용하면 기존 배열은 건드리지 않은 상태에서 원소를 추가한 배열이 복제(?)된다.
복제 됐는데 있을 곳이 없을뿐이다. 즉, 복제된 배열을 변수에 저장해주어야 한다.

    var array = ['a', 'b', 'c', 'd', 'e'];
    document.write(array + "<br>");         
    array = array.concat(['f', 'g']);       // 복제된 배열을 변수에 담는다.
    document.write(array + "<br>");         // a,b,c,d,e,f,g
  
### push와 concat 비교
* **push : 원소를 추가하면서 기존 배열변수를 업데이트까지 되어버린다.**
* **concat : 원소를 추가하지만 기존 배열변수는 건드리지 않은채 복제(?)된다.**

### 또다른 함수들
* unshift -> 배열의 시작점에 원소를 추가하며, 기존 값들은 index를 1씩 증가시킨다
### 

        var array = ['a', 'b', 'c', 'd', 'e'];       
        li.unshift('z');                        
        document.write(array + "<br>");         // z,a,b,c,d,e

* splice 
### 

        var li = ['a', 'b', 'c', 'd', 'e'];
        li.splice(2, 1);                    // 2번재 원소에서 1개를 잘라라
        document.write(li + "<br>");        // a,b,d,e

        var li = ['a', 'b', 'c', 'd', 'e'];
        li.splice(2, 0, '5');               // 2번째 원소에서 0개를 자르고 2번째 원소에 5를 넣어라
        document.write(li + "<br>");        //a,b,5,c,d,e

------------------------------------