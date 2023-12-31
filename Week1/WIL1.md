1장


컴파일: 소스 코드를 실행하기 전 기계어로 번역하는 행위
컴파일러: 컴파일을 수행하는 소프트웨어
컴파일 언어: 소스 코드 여러 개를 하나로 묶어서 컴파일 한 뒤에 실행하는 프로그래밍 언어 ex)c,c++,java
인터프리터 언어: 프로그램을 한 줄마다 기계어로 번역하는 행위
인터프리터: 프로그램을 번역해서 실행시키는 소프트웨어 ex)javascript, python, ruby ...


2장

factorial.js

function fact(n) {
	if( n<=1 ) return n;
	return n*fact(n-1);
}
for(var i=1; i<10; i++) {
	console.log(i + "! = " + fact(i));
}

factorial.html

<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <title>팩토리얼 계산</title>
</head>
<body>
    <script>
        function fact(n) {
	     if( n<=1 ) return n;
	        return n*fact(n-1);
        }
        for(var i=1; i<10; i++) {
        	console.log(i + "! = " + fact(i));
        }
    </script>
</body>
</html>

2.4프로그램 작성법
    2.4.1 자바스크립트 프로그램은 유니코드 문자로 작성
    2.4.2 대문자와 소문자 구별
    2.4.3 토큰과 공백문자
        토큰: 프로그램을 구성한느 최소 단위, 의미를 가지는 최소한의 문자 덩어리
        공백문자: 토큰을 구별하기 위해 사이에 입력
        공백문자 생략: 산술 연산자 앞뒤 공백문자,세미콜론,쉼표,마침표,콜론 앞뒤 공백문자는 생략 가능
        가독성 높이기: 공백문자, 탭 문자, 개행 문자를 적절히 추가해 코드 가독성을 높임
    2.4.4 문장
        문장
            var x;   //변수 선언
            message = "Hi" + name;   //표현식의 대입
            counter++;  //변수 값 증가
            prompt("이름을 입혁하세요")   //함수호출
            문장 끝에는 반드시 세미콜론을 붙이고 개행 문자로 줄을 바꿔라
            한 줄에는 한 문장만 작성해라
        복합문
            문장 여러 개를 중괄호로 감싼 코드
            {
                sum = sum + x;
                console.log("sum = " + x)
            }
            복합문 끝에는 세미콜론을 붙이지 않음
        빈 문장
            빈 문장은 세미콜론으로 작성
            실행해도 아무런 작업을 하지 않음
        세미콜론 자동 추가
            예외) return문, break문, continue문
    2.4.5 주석
        /* 주석문 */
        // 주석문 


3장
3.1 변수
    3.1.1 변수
        변수: 값을 담기 위해 이름 붙인 상자
    3.1.2 변수선언
        변수를 사용하기 위해 변수 선언
        ex) var sum; 에서
        var은 선언자, sum은 변수 이름
        자바스크립트는 변수 선언자가 var 하나뿐임
        쉼표를 사용하여 여러 개의 변수를 한 문장으로 선언가능 ex) var sum, a;
        변수를 선언하면 변수 안에는 정의되지 않음을 위미하는 undefined 값이 들어감
        ex) var x; console.log(x);  //->undefined
        프로그램에서 =연산자는 오른쪽 값을 왼쪽 변수에 대입하겠다는 의미
        ex) var a=1, b=2, c=3;
    3.1.3 변수 선언 생략
        var문으로 선언하지 않은 변수값을 읽으려고 시도하면 참조오류 발생
        ex) console.log(x);     //<-ReferenceError: x is not defined(오류메세지)
        var문을 선언하지 않고 변수에 값을 대입할 때는 오류가 발생하지 않음
        ex) x=2; console.log(x);    //->2
    3.1.4 변수 끌어올림과 변수 중복 선언
        프로그램은 작성순서에 따라 윗줄부터 차례대로 실행되지만 변수 선언은 예외를 가짐
        ex) console.log(x);     //->undefined
            var x;
        변수 선언의 끌어올림(호이스팅hoisting): 변수를 프로그램 중간에 선언하더라도 변수가 프로그램 첫머리에 선언된 것처럼 문장 앞에 생성
        단, 선언과 동시에 대입하는 코드는 끌어올리지 않음
        ex) console.log(x);      //->undefined
            var x = 5;
            console.log(x);      //-> 5
    3.1.5 변수의 명명 규칙
        사용가능 문자는 알파벳,숫자,밑줄,달러($)
        첫 글자는 숫자 사용 불가
        예약어를 식별자로 사용 불가
            변수 이름 짓는 방법
            1.캐멀 표기법: 두번째 이후 단어의 첫 글자를 대문자표시 ex) createLifeGame
            2.파스칼 표기법: 각 단어 첫 글자를 대문자표시 ex) CreateLifeGame
            3.밑줄 표기법: 단어와 단어 사이를 밑줄로 구분 ex) create_life_game
            4.일반적 표기법: 루프카운터 변수는 i,j,k 사용, 상수는 대문자로 표시, 생성자 이름은  파스칼 표기, 논리값 변수는 이름 앞에 is 붙임
    3.1.6 예약어
        자바스크립트 문법을 규정짓기 위해 자바스크립트 언어 사양에서 사용하는 특수한 키워드
        break, case, catch, class, const, contiue, debugger, default, delete, do, else, export, extends, false, finally, for, function, if, import, in, instanceof, new, null, return, super, switch, this, throw, true, try, typeof, var, void, while, with, yield
    
3.2 데이터 타입
    3.2.1 데이터 타입과 변수의 동적 타이핑
        정적 타입 언어: 변수의 타입과 일치하는 데이터만 저장할 수 있는 언어 ex) C, Java
        동적 타입 언어: 같은 변수에 숫자나 문자열과 같은 다양한 타입의 데이터를 대입할 수 있는 언어 ex) 자바스크립트
    3.2.2 데이터 타입의 분류
        자바스크립트는 원시 타입과 객체 타입 두가지를 처리할 수 있음
        원시 타입(primitive type): 데이터를 구성하는 가장 기본적인 요소로 불변 값으로 정의됨
            ex) 숫자, 문자열, 논리값, 특수값(undefined,null), 심벌                      
        객체 타입: 원시 타입에 속하지 않은 javascript값, 여러 개의 변수가 모여서 만든 복합 데이터 타입, 객체는 참조 타입, 객체 타입의 값을 변수에 대입하면 변수에 객체에 대한 참조가 할당됨
            ex) 배열, 함수, 정규 표현식
    3.2.3 숫자
        숫자를 모두 64비트 부동소수점으로 표현하는 double타입
        리터럴: 프로그램에 직접 작성할 수 있는 상수 값, 정수 리터럴과 부동소수점 리터럴이 있음
    3.2.4 문자열
        문자열 리터럴은 작은따옴표나 큰따옴표를 문자열의 앞뒤에 붙여서 표현
        ""  //-> 빈 문자열
        자바스크립트를 html요소에 끼워 넣을 때는 자바스크립트 프로그램을 문자열로 작성
    3.2.5 논리값
        조건식이 참인지 거짓인지 표현하기 위해 사용하는 값 
        True, False
    3.2.6 특수한 값
        값이 없음을 표현하는 null, undefined
        undefined: 값이 아직 할당되지 않은 변수값
                   없는 객체의 프로퍼티를 읽으려고 시도
                   아무것도 반환하지 않는 함수가 반환하는 값
                   함수를 호출했을 때 전달받지 못한 인수의 값
        null: 아무것도 없음, 무언가를 검색했지만 찾지 못했을 때의 아무것도 없음을 전달하기 위한 값

3.3 ECMAScript 6부터 추가된 데이터 타입
    3.3.1 심벌
        심벌은 자기 자신을 제외한 그 어떤 값과도 다른 유일무이한 값
        Symbol()을 사용해 생성
        Symbol()은 호출될 때 마다 새로운 값
        Symbol,for()을 활용해 문자열과 연결된 심벌을 생성할 수 있음 ex) var sym1 = Symbol.for('club);
        Symbol.keyFor()로 심벌과 연결된 문자열을 구함
    3.3.2 템플릿 리터럴
        템플릿 리터럴은 역따옴표(`)로 묶은 문자열
        템플릿: 일부만 변경해서 반복하거나 재사용할 수 있는 틀
        템플릿 리터럴을 사용하면 일반적인 줄 바꿈 문자를 사용가능
        ex) var t = `Man errs as long as
        he strives`;
        태그 함수 String.raw를 붙여 이스케이프 시퀀스 문자를 그대로 출력가능
        ex) var t = String.raw`Man errs as long as\nhe strives`;
            var t = `Man errs as long as\\nhe strives`;
        템플릿 리터럴 안에 플레이스 홀더를 넣을 수 있음

4장
4.1 객체의 기초①객체 리터럴
    4.1.1 객체
        객체는 이름과 값을 한 쌍으로 묶은 데이터를 여러 개 모은 것
        객체는 데이터 여러 개를 하나로 모은 복합 데이터로 연관배열 또는 사전이라고 부름
        프로퍼티: 객체에 포함된 데이터 하나
        프로퍼티 이름, 프로퍼티 키: 프로퍼티의 이름부분
        객체를 생성하려면 객체 리터럴을 사용하거나 생성자라는 함수를 사용
    4.1.2 객체 리터럴로 객체 생성하기
        var card = {suit:'하트', rank:'A'};
        {}부분이 객체 리터럴, 객체 리터럴을 변수 card에 대입
        {프로퍼티 이름: '프로퍼티 값'}
        변수에 대입한 객체 안의 프로퍼티 값을 읽거나 쓸 때 마침표연산자(.) 또는 대괄호 연산자([]) 사용
        객체 없는 프로퍼티를 읽으려고 시도하면 undefined를 반환
        cf) 선언되지 않은 변수를 읽으려고 시도시 참조요류 referenceError 발생하는 것과 대조적
    4.1.3 프로퍼티 추가와 삭제
        없는 프로퍼티 이름에 값을 대입하면 새로운 프로퍼티 생성
        delete연산자를 이용해 프로퍼티 삭제
    4.1.4 in 연산자로 프로퍼티가 있는 지 확인하기
        프로퍼티가 객체에 포함되면 true 없으면 false
        프로퍼티 이름을 뜻하는 문자열 in 객체명
        toString 프로퍼티는 객체 안에 없지만 변수가 object변수를 상속받아 있다는 결과가 나옴
        ex) console.log('toString' in card);    //true
    4.1.5 객체 리터럴 예제
        ex1) var p = {x:1.0,y:2.5};
        ex2) var circle = {
                 center:{{x:1.0,y:2.5},
                 radius: 2.5
             };
        ex3) var person = {
                 name : "홍은기"
                 age : 23
                 sex : "male"
                 married: false
             };
    4.1.6 메서드
        프로퍼티에 저장된 값의 타입이 함수
    4.1.7 객체는 참조 타입
        