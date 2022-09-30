# JavaScript TIL

## **JavaScript의 자료형과 특성.**
    1. 느슨한 타입의 동적언어이며
    자바 스크립트의 변수는 어떠한 특정 타입과 연결되지 않고 모든 타입의 값으로 할당, 재할당이 가능하다.

    2. JavaScript 형변환
        
        암시적 변환과 명시적 변환
        
        1. 암시적 변환이란 자바스크립트 엔진이 필요에 따라 자동으로 데이터타입을 변환시키는 것이다.
        2. 명시적변환이란 개발자가 의도를 가지고 데이터타입을 변환시키는 것이다.

        3. etc..

            + var 변수 = parseInt(문자);  문자를 정수형 숫자로 변환해줌
            + var 변수 = parseFloat(문자);     //문자를 실수형 숫자로 변환해줌
            + var 변수 = Nember(문자);    //문자를 정수&실수형 숫자로 변환해줌
            + var 변수 = String(숫자);    //숫자를 문자로 변환해줌
            + var 변수 = 숫자.toString(진법);    //숫자를 문자로 변환해줌 - 변환하면서 진법을 바꿀 수 있음
            + var 변수 = 숫자.toFixed(소수자리수);    //숫자를 문자로 변환해줌 - 실수형의 소수점 자리를 지정할 수 있음
            + var 변수 = 숫자 + "문자열";    //숫자와 문자열을 한 문자열로 더해줌

    3. '=='와 '==='

         ===는 변수 유형을 고려하는 반면, ==는 변수 값을 기반으로 유형을 수정한다.

    4. 느슨한 타입(loosely typed)의 동적(dynamic) 언어의 문제점은 무엇이고 보완할 수 있는 방법

        동적타입 언어는 런타임 시 확인할 수 밖에 없기 때문에, 코드가 길고 복잡해질 경우 타입 에러를 찾기가 어려워 집니다. 이러한 불편함을 해소하기 위해 TypeScipt나 Flow 등을 사용할 수 있습니다.

    5. undefined와 null의 미세한 차이들을 비교해보세요.

        undefined은 변수를 선언하고 값을 할당하지 않은 상태, null은 변수를 선언하고 빈 값을 할당한 상태(빈 객체)이다. 즉, undefined는 자료형이 없는 상태이다.

## **JavaScript 객체와 불변성이란**

    1. 기본형 데이터와 참조형 데이터

        + 기본형 타입
        
            + 종류: 논리형(boolean), 정수형(int), 실수형(double), 문자형(char)

        + 참조형 타입

            + 종류: 배열(Array), 클래스(Class), 인터페이스(Interface)

    2. 불변 객체를 만드는 방법

        + freeze 와 immutable

    3. 얕은 복사와 깊은 복사

        + 얕은 복사

            + 객체를 복사할 때, 해당 객체만 복사하여 새 객체를 생성한다.
            + 복사된 객체의 인스턴스 변수는 원본 객체의 인스턴스 변수와 같은 메모리 주소를 참조한다.
            + 따라서, 해당 메모리 주소의 값이 변경되면 원본 객체 및 복사 객체의 인스턴스 변수 값은 같이 변경된다.

## **호이스팅과 TDZ**

    1. 스코프, 호이스팅, TDZ

        + 스코프: 변수, 함수, 클래스가 접근할 수 있는 유효 범위.
        + 호이스팅: 인터프리터가 변수와 함수의 메모리 공간을 선언 전에 미리 할당하는 것을 의미합니다.
        + TDZ : Temporal Dead Zone 호이스팅과 연계하여 생각하기

    2. 함수 선언문과 함수 표현식에서 호이스팅 방식의 차이

        + 함수 선언문 : 맨 위로 호이스팅
        + 함수 표현식 : 정의된 줄부터 함수 코드내용 적용

    3. let, const, var, function

        + const : 재할당 불가능, 기본적으로 사용하자
        + let : 재할당가능, 재할당이 필요할 때 사용하자
        + var : 재할당가능, 사용하지말자

    4. 실행 컨텍스트와 콜 스택

        + 콜 스택 : 항상 맨 위에 놓인 함수를 우선으로 실행된다.
        + 실행 컨텍스트 : 실행할 코드에 제공할 환경 정보들을 모아놓은 객체  
        
        (주소참고 : https://junilhwang.github.io/TIL/Javascript/Domain/Execution-Context/#_2-%E1%84%89%E1%85%B5%E1%86%AF%E1%84%92%E1%85%A2%E1%86%BC-%E1%84%8F%E1%85%A5%E1%86%AB%E1%84%90%E1%85%A6%E1%86%A8%E1%84%89%E1%85%B3%E1%84%90%E1%85%B3-%E1%84%80%E1%85%AE%E1%84%89%E1%85%A5%E1%86%BC )

    5. 스코프 체인, 변수 은닉화

        + 스코프  체인 : 스코프에 식별자가 없으면 상위 스코프에서 다시 찾아 나간다. 이 현상을 스코프 체인 이라고 하며 스코프가 중첩되어있는 모든 상황에서 발생한다.
        + 변수 은닉화 : 외부 객체로부터 '속성 값(데이터, 멤버 변수값)'을 감추는 특성

##  **JWT (Json Web Tokens)**

    이것은 유저를 인증하고 식별하기 위한 토큰 기반 인증이다.
    이것의 특징은 토큰 자체에 사용자의 권한 정보나 서비스를 사용하기 위한 정보가 포함된다는 것이다.

     jwt 는 아래의 순서로 진행된다

        1. 클라이언트 사용자가 아이디, 패스워드를 통해 웹서비스 인증.
        2. 서버에서 서명된 jwt 를 생성하여 클라이언트에 응답(response)으로 돌려줌.
        3. 클라이언트가 서버에 데이터를 추가적으로 요구할 떄 jwt 를 http header에 첨부함.
        4. 서버에서 클라이언트로부터 온 jwt를 검증.

    jwt 의 구조는 HEADER, PAYLOAD, SIGNATURE 로 구성된다.

    @ 자세한 설명 다음 참고.(https://pronist.dev/143)
    @ 집적 실습한 내용 다음 참고.(https://github.com/ParkBig/Simple_toyproject_gamestroy)
## **API (Application Programming Interface)**

    이것은 응용 프로그램에서 사용할 수 있도록, 운영 체제나 프로그래밍 언어가 제공하는 기능을 제어할 수 있게 만든 인터페이스를 뜻한다.

    @ 직접 실습한 내용 다음 참고.(https://github.com/ParkBig/Simple_toyproject_gamestroy)
## **CDN**(ContentS Delivery Network)

    CDN은 지리적으로 분산된 여러 개의 서버이다. 웹 콘텐츠를 사용자와 가까운 곳에서 전송하여 전송 속도를 높인다.  
    따라서 사용자는 가까운 서버를 통해 웹 활성화 디바이스 또는 브라우저에서 인터넷 콘텐츠에 빠르게 접속 할 수 있다.

--------------------------------------- 
--------------------------------------- 
## **정규표현식**

1. 내용정리중입니다..

    + 정리중입니다..

        ```javascript
        console.log("안녕\t나는\t작성자야\n네\t이름은\t뭐니?")      // 안녕 나는 작성자야 (줄바꿈) 네 이름은 뭐니?

        ```






--------------------------------------- 
---------------------------------------  
## **Array method**  
(일부 String, Number 가능.)

1. .forEach()  

    + 대상이되는 배열의 길이만큼 콜백함수를 호출한다.

        ```javascript
        const a = [1,2,3] // 길이 3
        a.forEach((prop, index)=> console.log(`a[${index}] = ${prop} 입니다.`))
        // a[0] = 1 입니다.
        // a[1] = 2 입니다.
        // a[2] = 3 입니다.
        ```
    
2. .map()

    + 대상이되는 배열의 길이만큼 콜백함수 호출값을 새로운 배열에 담아 리턴한다.

        ```javascript
        const a = [1,2,3] // 길이 3
        const b = a.map((prop, index)=> `a[${index}] = ${prop} 입니다.`)

        console.log(b) // ["a[0] = 1 입니다.", "a[1] = 2 입니다.", "a[2] = 3 입니다."]
        ```

3. .filter()

    + 대상이되는 배열에서 prop과 index를 받아 콜백함수의 조건을 만족했을때의 prop만 골라서 새로운 배열을 리턴한다.  
    이때 콜백함수에는 return값이 무조건 있어야한다.  
    ex) ()=>조건 or ()=>{return 조건}

        ```javascript
        const a = [1,2,3,4,5]
        const b = a.filter((prop)=> prop > 2) 

        console.log(b) // [3,4,5]
        ```

4. .slice(startIndex, endIndex)

    + 대상에 startIndex 부터 endIndex바로전까지 요소를 리턴한다.  
    (대상 배열 변화없음.)
    ```javascript
        let test = [1,2,3,4,5,6,7];
        let b = test.slice(2,5)

        console.log(b)                   // [3, 4, 5]
    ```

5. .splice(startIndex, length)

    + 대상에 대상의 startIndex 부터 length 만큼 추출한다.  
    (추가 기능도 있음.)
    ```javascript
        let test = [1,2,3,4,5,6,7];
        let b = test.splice(2,3)

        console.log(b)                   // [3, 4, 5]
    ```

6. .indexOf( searchValue, position )

    + 대상에서 찾고자하는 값을 첫 발견시 그 값의 인덱스를 리턴하고 종료.
    ```javascript
    let test = [1,2,3,4,5,5,5,6,7,8,9]
    let a = test.indexOf(5)
    let b = test.indexOf(5,5)
    let c = test.indexOf(10)

    console.log(a, b, c)                    // 4, 5, -1
    ```

7. .find()

    + 콜백함수의 조건을 만족하는 요소를 첫 발견시 그값을 리턴하고 종료.
    ```javascript
        let test = [1,2,3,4,5,6,7];
        let a = test.find((ele,index)=>ele>5)

        console.log(a)                   // 6
    ```

8. .findIndex()

    + 콜백함수의 조건을 만족하는 요소를 첫 발견시 그 인덱스 값을 리턴하고 종료.
    ```javascript
        let test = [1,2,3,4,5,6,7];
        let a = test.findIndex((ele,index)=>ele>5)
        let b = test.findIndex((ele,index)=>ele<0)

        console.log(a, b)                   // 5, -1
    ```

9. .sort( (a,b)=> 0이상 === 오름차순, 0이하 === 내림차순 )

    + 내부함수의 return 값이 0 보다 크면 오름차순, 작으면 내림차순 정렬.  
    요소를 아스키코드값으로 인식하기 때문에 .sort()만 하면 에러가 날 수 있다.
        ```javascript    
        let a = [1,4,3,2,6,5,7,8,9] 

        console.log(a.sort((a,b)=>a-b))             // [1,2,3,4,5,6,7,8,9]
        console.log(a.sort((a,b)=>b-a))             // [9,8,7,6,5,4,3,2,1]
        ```













---------------------------------------
## **Number method**


1. .toFixed(n)  

    + 소수점이하 n번까지만 출력한다

        ```javascript
        const test = 123.456789

        console.log(test.toFixed(3))            // 123.457
        ```

2. Number.isNaN()

    + NaN 을 판별한다.
    












--------------------------------------- 
## **String method**  
(일부 Array, Number 가능.)


1. .trim()  

    + 문자열 앞뒤의 공백을 제거한다

        ```javascript
        const test = "   hello "

        console.log(test.trim())            // "hello"
        ```

2. .split(s)

    + s 를 기준으로 문자 내부를 나누어 배열값에 저장하고 리턴한다.

        ```javascript
        const test = "1,2,3,4,5"

        console.log(test.split(","))        // ["1", "2", "3", "4", "5"]
        
        ```

3. JSON 
    
    +
        ```
        1. .stringify(data,null,들여쓰기칸설정) 
        2. .parse(json문자열)  
        ```

4. .localeCompare()

    + 대상과 괄호안의 값의 사전순서를 판별하여 결과에따라 -1,0,1 을 리턴한다
        ```javascript
        let a = "a";
        let A = "A";
        let b = "b";
        let B = "B";
        a.localeCompare(A)          // -1
        a.localeCompare(b)          // -1
        b.localeCompare(a)          //  1
        b.localeCompare(A)          //  1
        ```

5. .substr(start, length)

    + 파라미터로 입력받은 start index부터 length 길이만큼 string을 잘라내어 반환하는 함수이다.
        ```javascript
        let str = "안녕하세요?"
        let first_char = str.substr(0, 1);          // 안
        let second_char = str.substr(1, 1);         // 녕
        ```

6. .substring(startIndex, endIndex)

    + substr와 같은 역할을 하지만 start index 부터 지정한 endIndex전 까지 잘라내어 반환하는 함수이다.
        ```javascript
        let str = "안녕하세요?"
        let first_char = str.slice(0, 1);           // 안
        let second_char = str.slice(1, 2);          // 녕
        ```















--------------------------------------- 
--------------------------------------- 

## **함수**

1. 함수의 기본형태 

    + 함수 선언식

        ```javascript
        function test() {
            return "hi"
        }
        ```
    + 함수 표현식

        ```javascript
        const test = function () {
            return "hi"
        }
        ```
    + 화살표 함수 
    
        ```javascript
        const test = () => {
            return "hi"
        }
        ```     
    + 즉시 실행 함수

        ```javascript
        (function () {
            return "hi"
        })();
        ```  
    함수에 인자를 받을때 ...문법을 이용하면 여러개의 인자를 배열로 받아올 수 있다.

    + ex1)
        ```javascript
        function test (...props) {
            console.log(props)
        }
        test(1,2)       // [1,2]
        test(1,2,3)     // [1,2,3]
        ```
    + ex2)
        ```javascript
        function test (a,b,...rest) {
            console.log(a,b,rest)
        }
        test(1,2,3,4,5,6)   // 1,2,[3,4,5,6]
        ```
    + ex3)
        ```javascript
        function test (...props) {
            console.log(props)
        }
        const arr = [1,2,3,4]
        test(arr)       // [[1,2,3,4]]
        test(...arr)    // [1,2,3,4]
        ```
    -------------------------------------  
2. 기본 매개변수

    이름 그대로 함수를 사용할떄 받는 요소에 기본값을 설정해 놓는 것.  
    만약 요소를 받지 못하면 기본값으로 함수를 계산한다.

    + ex)

        ```javascript
        function test (a=1) {
            console.log(a)
        }
        test()      // 1
        test(4)     // 4
        ```
-------------------------------------
## **객체**

1. 객체 속 함수 표기

    + 구 버전

        ```javascript
        const test = {
            name : "bob",
            hello : function (name) {
                console.log(`${this.name}, hello!`)
            }
        }
        test.hello()    // "bob, hello!"
        ```
    + 최신버전에서는 다음과 같이 표기 가능.

        ```javascript
        const test = {
            name : "bob",
            hello (name) {
                console.log(`${this.name}, hello!`)
            }
        }
        test.hello()    // "bob, hello!"
        ```
    + 화살표 함수 역시 표시가능하지만 화살표함수에 this 를 사용할 경우 전역을 가르키기 때문에   
    이 경우에는 사용하지않는다.

2. prototype

    + 숫자, 문자열, 불리안에는 일반적으로 속성을 가질 수 없다.  
    ex)

        ```javascript
        const test =273;
        test.sample = 10        
                                // 10
        console.log(test.sample)                        // undefined
        ```
    + new (Number, String, Boolean)을 사용하면 속성을 추가 할 수 있다.  
    ex)

        ```javascript
        const test = new Number(273);
        typeof(test);                                   // object
        test.sample = 10;

        console.log(test.sample)                        // 10
        console.log(test)                               // Number {273, sample:10}
        console.log(test + 7)                           // 280
        ```








--------------------------------------- 
--------------------------------------- 

## **CLASS**

1. ES6 이후로 사용가능.  
기존에 생성자 함수와 그 함수에 전부 적용되는 프로토타입을 따로 써주던것을 class 에선 선언속에서 한번에 할 수 있다.

    + 기존의 방법 Info 에 전부 프로토타입 적용시.
    
        ```javascript
        function Info(name, age) {
            this.name = name;
            this.age = age;
        }
        Info.prototype.race = "human"
        Info.prototype.hello = function () {console.log("hello")}

        let test = new Info("park", "secret");
        console.log(test)                           // {name: "park", age: "secret", race: "human", hello: function () {window.runnerWindow.proxyConsole.log("hello")}}
        ```

    + class 로 표현 했을 때.

        ```javascript
        class Info {
            constructor(name, age) {
                this.name = name;
                this.age = age;
                // 생성자 객체에 조건문 써줄 수 있다.
            }

            race : "human"
            
            hello () {console.log("hello")}
        }

        let test = new Info("park", "secret")
        console.log(test)                           // {name: "park", age: "secret", race: "human", hello: function () {window.runnerWindow.proxyConsole.log("hello")}}
        ```

2.  서로 다른 class 속 프로토타입 함수가 상당수 중복 될 경우 **extends** 를 사용하여 상속 받을 수 있다.

    +  **class (상속받을 클라스) extends (상속해 줄 클라스) {}**

        ```javascript
        ( 상속 받기 전의 두개의 class )

        class Rectangle {
            constructor(width, height) {
                this.width = width;
                this.height = height;
            }

            getPerimeter() {
                return (this.width + this.height)*2
            }

            getArea() {
                return this.width * this.height
            }
        }

        class Square {
            constructor(length) {
                this.length = length;
            }

            getPerimeter() {
                return this.length *2
            }

            getArea() {
                return this.width **2
            }
        }

        ////////////////////////////////////////////////////////>  
        ////////////////////////////////////////////////////////>  

        ( 상속 받은 후의 두개의 class )

        class Rectangle {
            constructor(width, height) {
                this.width = width;
                this.height = height;
            }

            getPerimeter() {
                return (this.width + this.height)*2
            }

            getArea() {
                return this.width * this.height
            }
        }

        class Square extends Rectangle {
            constructor(length) {
                super(length, length) // super는 상속받고 부모값사용할 때 고정이다.
            }
        }
        ```

3. **static** method and porperty.

    + new 를 통해 class 함수를 호출하면, constructor에 의해 새로운 객체가 만들어진다.  
    이때 constructor의 this 가 가르키는 것은 이 새로운 객체이다.  
    **하지만,** static 이 붙은 메소드의 this 는 class 함수이다.

    + **다시 말해**, static 을 붙이면 프로토타입 method가 아니라 class의 method가 되는 것이다.  
    **따라서** static method를 호출하려면 className.method() 로 직접 호출해야된다.
        ```javascript
        class Test {
            static counter = 1;

            static name = "park";
            
            static helloTo () {return `${this.name}, hello`}

            constructor(name) {
                this.name = name;
                Test.counter++
            }
            
            hello () {return `${this.name}, hello`}
        }

        let a = new Test("kim")
        let b = new Test("lee")
        let c = a.hello()
        let d = Test.name
        let e = Test.helloTo()
        let f = Test.counter

        console.log(a, b, c, d, e, f)  
        // {name: "kim"}, {name: "lee"}, "kim, hello", "park", "park, hello", 3
        ```
--------------------------------------- 
--------------------------------------- 