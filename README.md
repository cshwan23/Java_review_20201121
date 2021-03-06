# Java_review_20201121
자바 문법 총 복습


[식별자] : class 이름, 메소드 이름, 변수 이름

[키워드] : 자바 언어에서 미리 정해놓은 식별자. 문법상 영단어
     >예약어 라고도 한다.

[참조형 데이터 타입]
클래스가 객체화 될 때 메모리에 올라가는데
이때 [객체의 메모리 위치 주소값]을 말한다.

[변수 선언과 데이터 저장]
1. [속성변수]일 경우
     > 자료형 속성변수 = 데이터;
          =>속성변수 선언과 동시에 개발자가 데이터를 저장(수동 초기화)
     > 자료형 속성변수명;
          =>속성변수 선언과 동시에 자동으로 기본값 데이터 저장(자동 초기화)

2. [지역변수]일 경우
     > 자료형 지역변수명 = 데이터;
          => 지역변수 선언과 동시에 개발자가 데이터를 저장(수동 초기화)
     > 자료형 지역변수명;
          => 지역변수 선언. 데이터 저장 없음 (자동 초기화 실패)
     > 지역변수명 = 데이터;
          => 개발자가 데이터를 저장(수동 초기화)

> 지역변수는 자동 초기화가 불가능하다.
> 지역변수는 지역변수 선언 후 그 지역 안에서 개발자가 직접 할당하지 
   않으면 컴파일 에러가 발생한다.
[switch]문

> [변수]의 값이 설정한 [데이터]와 같을 때 [실행구문]을 수행한다.

[switch 문 형식]

<1>
switch (변수) {
          case 데이터1 : 실행구문1 ;
}
<2>
switch (변수) {
          case 데이터1 : 실행구문1; break;
          case 데이터2 : 실행구문2; break;
          .....
          case 데이터n : 실행구문n; break;
}
> break를 만나면 swhich 문을 탈출한다.
> break가 없으면 다음 case 문의 조건을 무시하고
   다음 case 문의 [실행구문]을 실행한다.

<3>
switch (변수) {
          case 데이터1 : 실행구문1; break;
          case 데이터2 : 실행구문2; break;
          .....
          case 데이터n : 실행구문n; break;
         default : 실행구문n+1;
}
=> default 도 else 와 동일한 기능.
=> switch 변수의 자료형은 byte short int char 만 가능.



[while 문]

while(조건식) {
          실행구문;
}
=> 초기설정값이 없고 증감식도 없다.
=> 처음 조건식이 false면 실행구문이 한번도 실행 안될 수 있다.


[do~while 문]

do{
          실행구문;
}while(조건식);

(1) [실행구문]을 먼저 실행.
(2) while 뒤에 (조건식)의 결과가 true면 다시한번 실행구문 실행.
(3)false 면 반복문 탈출.

=> 조건식이 뒤에 있어 실행구문이 최소한 한번은 실행된다.

[분기문]

> 반복문 안에서 사용되어 강제로 명령어의 [처리 순서]를 바꾸는 명령문을 말한다.

1. [break]
     > 반복문(for, while, do while) 문 안에서 사용되어 강제로 반복문을 탈출한다.
     > switch 문 안에서도 사용.

1-1. [break 형식]

for( 초기값 ; 조건식 ; 증감식 ) {
          ~
          if(조건식2) {break;}
          실행구문 2;
}
실행구문3;


2. [continue]
     > 반복문(for, while, do while) 문 안에서 사용되어 강제로 다음 반복 구문으로
        건너 뛴다.

2-1. [continue 형식]
     
for( 초기값; 조건식; 증감식) {
          ~
          if(조건식2) {continue;}
          실행구문 2;
}
실행구문3;

=> <주의> continue가 나오면 다음 실행구문 실행하지 않고
     다음 증감식으로 바로 이동.


[클래스]

[속성변수], [메소드], [생성자]를 정의해 놓은 일종의 틀이다.

[클래스의 특징]

> 클래스에 정의된 [속성변수]와 [메소드]를 호출하여 사용하려면
   [Heap]이라는 메모리 공간에 올려놓고 호출한다.
   이때 [Heap]이란 메모리 공간에 올라간 클래스를 [객체]라고 한다.
> 클래스를 객체화 하는 이유는 객체가 소유한 메소드 또는 속성변수를 호출하기 위함이다.

[클래스 정의 형식]

클래스명.java
package 패키지명;
import 수입클래스패키지명.수입클래스명;

[public] [abstract | final] class 클래스명 {

      public  | protected | default | private    [static]   [final] 
      기본자료형 | 클래스명 | 인터페이스명   속성변수명  [= 데이터 ] ;

      public | protected | default | private   생성자명 ( [자료형 매개변수, ~] ) {
            실행구문 ~ ;
      }

      public | protected | default | private   [static] [synchronized] [final | abstract]
      기본자료형 | 클래스명 | 인터페이스명 | void   메소드명 ([자료형 매개변수,~]) {
            실행구문~;
      } 

}

[package]

      => 비슷하게 관련된 클래스나 인터페이스를 묶어놓음
      => package com.naver.staff; (3단계 이상이 관용적)

[import]

      => 타패키지 소속 클래스를 객체화하여 사용할 경우
      => 수입패키지명.클래스명을 지정한다.
      => import com.naver.staff* 클래스명 대신 *를 넣으면
      => 해당패키지의 모든 클래스를 수입하겠다는 의미.
      => 같은 패키지 안 모든 클래스는 코딩없이 자동 수입된다.

[클래스 성격 지정자]

   > abstract
      => {~}바디 없는 메소드를 하나 이상 소유한 클래스임을 지정하는 키워드다.
      => 추상클래스라고 하는데 객체화를 할 수 없고 메소드 호출도 못한다.
      => 상속이 목적이다. 빨리 상속해서 빨리 객체화 해서 바디없는 메소드를 재정의 하라는 의미.

[속성변수]

   > [기본형 데이터] 또는 [참조형 데이터](=객체의 메모리 위치 주소값)을 저장하는 변수.

[초기화] [initialization]

   > 변수 선언 후 처음 데이터를 저장하는 행위

[속성변수 선언 형식]

   public | protected | default | private  [static] [final] 
   기본자료형 | 클래스명 | 인터페이스명  속성변수명([자료형 매개변수,~]) { 실행구문~ }

[속성변수의 접근 지정자]

   > 관용적으로 대부분 [속성변수]는 private를 붙인다
   > 타 클래스에서 직접 호출을 막기위해서
   > 하지만 동료 메서드를 사용하여 이용할 수 있다.
   > 메서드는 대부분 public 으로 되어있기 때문에
   > public으로 되어있는 동료메서드 getter 메서드를 이용하여
   > 속성변수를 호출해서 쓸 수있다.

[속성변수의 성격 지정자]

   > static이 붙는 속성변수는
   > [객체참조변수.속성변수명] 또는 [클래스명.속성변수명] 형식으로 호출이 가능하고
   > 이 속성변수를 소유한 모든 동일 객체가 공유하게 된다.

      => 객체 생성 후 [객참변수명.속성변수명 = 데이터1;] 가 실행되면
           [클래스명.속성변수명] 으로 호출해도 데이터1이 저장되어 있다.

      => [클래스명.속성변수명 = 데이터1;] 가 실행되면
           객체 생성 후 [객참변수명.속성변수명]으로 호출해도 데이터1이 저장되어 있다.

   > static 이 없는 속성변수는 [객체참조변수.속성변수명] 형식으로만 호출이 가능하다.

   > static 이 붙은 변수를 [클래스 변수], [공유 변수]라고도 한다.

[속성변수의 자료 유형]

   > [클래스명]
      => 클래스명에 해당하는 클래스를 개체화한 [객체의 메모리 위치 주소값]
      => 클래스명에 해당하는 클래스의 후손 클래스를 객체화한 [객체의 메모리 위치 주소값]
      => null 값

[메소드]

   > 1. 메소드명(기능) 2. 리턴데이터자료형(어떤값으로 받을지) 3. 매개변수(어떤값을줘야할지)


[메소드 선언 형식]

public | proteceted | default | private  [static] [synchronized]  [final | abstract] 
기본자료형 | 클래스명 | 인터페이스명 | void  메소드명( [자료형 매개변수,~] ) {
   실행구문~;
}

> final : 메소드 오버라이딩 금지
> abstract : 바디없는 메소드가 하나 이상 있다.

[메소드 성격 지정자]

   > static  
      => stiatic 이 붙는 메소드는 [객체참조변수.메소드명] 또는 [클래스명.메소드명] 형식
           으로 호출이 가능하다.
      => static 이 없는 메소드는 [객체참조변수.메소드명] 형식으로만 호출이 가능하다.
      => static 이 붙은 메소드 안에서 나오는 동료 속성변수에는 static이 붙어야 한다.

   > final 
      => 소속 클래스를 타 클래스에 상속해 줄 경우 타클래스에서 메소드의 재정의 불가능.
      => 메소드 오버라이딩 금지

   > abstract
      => {~}바디가 없는 메소드에 붙인다.
      => {~}바디가 없는 메소드가 존재하면 클래스 앞에도 abstract가 붙어야 한다.

   > synchronized
      => 메소드 실행 중일 때 다른 스레드에서 호출 불가능

[메소드 리턴형]

   >메소드가 내놓는 반환 데이터의 자료 유형
   > return 의 의미는 메소드 실행을 중지하고 오른쪽 데이터를 호출한 곳으로 반환하라.
   > void
      => 메소드가 실행된 후 아무런 값도 반환하지 않는다.
      => 메소드 내부에 return 데이터; 가 있으면 안된다.
      => 단 return; 은 있어도 된다.

[메소드 오버로딩]

   > 같은 이름의 [메소드]를 두개이상 정의하는 것을 말한다.
   > 메소드 오버로딩 규칙
      => 메소드의 이름은 같고
      => 매개변수의 개수나 매개변수의 자료형은 달라야 한다.
      => 메소드의 리턴형은 상관없다.

[생성자]

   > 클래스를 객체화 한 후 자동으로 한번만 호출되는 실행구문 영역을 말한다.

[생성자 선언 형식]

public | protected | default | private  생성자명([매개변수자료형,~]){
   실행구문~;
}

   > 생성자의 실행구문은 대부분 속성변수의 초기화 작업이다.

[생성자 특징]

   > 생성자 호출 시 데이터를 전달해서 호출할 경우 매개변수를 설정한다.
      => 클래스명 객참변수 = new 생성자명(데이터) ; 코딩 실행 시 데이터가 생성자 매개변수로 전달된다.

   > 생성자가 0개면 컴파일시 기본생성자인 public 생성자명(){}이 자동 들어간다

[생성자 오버로딩]

   > 같은 이름의 [생성자]를 2개 이상 정의하는 것,
   > 생성자 오버로딩의 규칙
      => [생성자명]은 같더라도 [매개변수의 개수]나 [매개변수의 자료형]은 달라야 한다.

[생성자 호출 방법]

   > new 에 의한 객체 생성 과정에서 new 생성자명(~) 형식으로 호출
   > 동료 생성자 안에서 this(~)를 사용하여 호출
   > 자식 생성자 안에서 super(~)를 사용하여 호출

[클래스로부터 객체 생성, 속성변수/메소드 호출 방법]

> 1. 클래스 수입
> 2. 클래스 객체화 -> 클래스명 객참변수 = new 생성자명([데이터1,~]);
   (=> static 이 붙으면 객체화 과정 없이 호출 가능.)
> 3. 속성변수/메소드 호출
   => 객참변수.속성변수명;
   => 객참변수.메소드명([데이터1,~]);

[클래스명 객참변수 = new 생성자명( [데이터1, ~]);의 의미]

   > new 키워드 (역할)
      => 객체 생성할 때 나온다.
      => new 오른쪽 생성자명 나옴. 그생성자를 갖고있는 클래스를 찾음.
      => 메모리 공간에 올려서 객체화
      => 메모리에 올라간 생성자를 호출
      => 객체의 메위주를 리턴
   > 1. [객참변수] 선언
   > 2. [Method 영역]에 존재하는 클래스 중 호출 가능한 생성자명( [데이터1,~])를 가진 클래스를
          [Heap 영역]에 올린다.  
          => Heap 영역에 올라간 클래스를 객체라고 부른다
          => 생성자의 접근지정자에 따라 호출 불가능 생성자면 에러가 발생한다.
          => 생성자의 접근지정자가 private 면 누구도 객체 생성이 불가능하다
   > 3. [객체]의 생성자명([데이터1,~])을 호출한다
   > 4. [객체의 메모리 주소값]을 리턴하여 [객참변수]에 저장
   > 결국 new의 기능
      => [호출 가능 생성자를 소유한 클래스를 객체화 -> 생성자 호출-> 객체의 메모리위치주소값 리턴]이다.

   > 객참변수 없이 객체 생성과 동시에 속성변수나 메소드를 호출 할 수도 있다.
   > 이럴 경우 객참변수가 없으므로 객체의 메위주를 모르므로 속변이나 메소드를 재호출 불가하다.
         new 클래스명([매개변수]).속성변수명
         new 클래스명([매개변수]).메소드명([데이터1,~])

   > static 이 붙은 속성변수 또는 메소드는 new에 의한 객체 생성 코딩 없이
      클래스명.속성변수명   클래스명.메소드명(~)으로도 호출 가능하고
      객체 유무와 관계없이 호출한 모두가 공유한다.

[this 예약어]

   > [클래스]가 소유한 고유 멤버인 [속성변수], [메소드], [생성자]를 지칭하거나 [클래스]가 객체화 될 때
      [객체의 메모리 위치 주소값]을 말한다.

[상속]

> 클래스가 소유한 멤버 ( 속성변수, 메소드) 를 다른[클래스]에게 그대로 물려주는 것.

[슈퍼 클래스 형식]

> [public] [abstract] class 슈퍼클래스명 {
     ~
}
=> 부모클래스 앞에는 final 이 없어야 한다.

[서브 클래스 형식]
> [public] [abstract | final] class 서브클래스명 extends 슈퍼클래스명 {
      ~
}

[상속의 특징]

> 서브클래스는 단 1개의 슈퍼클래스만 가질 수 있다. (다중 상속불가능)
> 서브클래스를 객체화 하면 자동으로 슈퍼클래스도 객체화 된다.
> 서브클래스의 [생성자] 안의 첫줄에는 반드시 슈퍼클래스의 생성자를 호출하는 super(~)가 있어야 한다.
> 서브클래스가 객체화 되면 [슈퍼클래스의 생성자 구문]이 먼저 실행되고 난 후
   서브클래스의 생성자 실행구문이 실행된다.
> 서브클래스 영역에서 슈퍼클래스 속변,메소드를 호출할 수있는데 private이 붙어있을 경우 호출 불가능하다.
> 서브클래스 객체화 후 속변/메소드 를 호출하면 먼저 [서브클래스]에서 찾고난 후 없으면
   [슈퍼클래스]쪽에서 찾아 호출한다.
> 서브클래스 영역에서 슈퍼클래스의 메소드를 재 정의 할 수 있다 => 오버라이딩(Overriding)
> final이 붙은 메소드는 오버라이딩 불가능하고 오버라이딩 규칙에 맞게 재정의해야한다.

[오버라이딩(Overriding)]

> 슈퍼클래스가 소유한 메소드를 서브클래스에서 같은 메소드 이름으로 재정의 하는 것을 말한다.

[오버라이딩 하는 이유]

> 슈퍼클래스의 메소드를 서브클래스가 그대로 사용하기에 맞지 않아서
   원하는 형태로 수정해 사용하기 위함이다.

[메소드 오버라이딩 규칙]

> 오버라이딩 할 [슈퍼클래스]의 메소드에 private 또는 final 이 없어야 하고
> [리턴형], [메소드명], [매개 변수 개수], [매개 변수 자료형] 이 같아야 한다.
> 실행구문만 바꿀 수 있다.
> [서브클래스의 접근지정자]는 [슈퍼클래스의 접근지정자]보다 같거나 커야한다.

[@Override]

> 클래스, 속성변수, 매개변수, 메소드 앞에 붙어서 특정기능을 부여하는 표기방법
> 메소드 앞에 붙으면 무조건 오버라이딩 규칙을 검사하여 에러 여부를 검사한다.

[@Override 붙지 않은 경우 고유 메소드로 보는 경우]

> 메소드명이 같고 [매개변수 개수] 또는 [매개변수 자료형]이 다른 경우
> [메소드명], [매개변수 개수], [매개변수 자료형]이 모두 같고 private이 붙은 경우

[@Override 가 붙지 않은 경우에 오버라이딩 시도로 보는 경우]

> [메소드명], [매개변수 개수], [매개변수 자료형]이 같으면 오버라이딩 시도로 보고
> 리턴형과 접근 지정자를 오버라이딩 규칙 차원에서 점검하여 에러 여부를 검사한다.

[super 예약어]

> [서브클래스] 내부에서 [슈퍼클래스]가 소유한 고유 멤버인 [속성변수], [메소드], [생성자]를
   호출하기 위해 사용한다.

> super의 사용 형식
   => super.속성변수
   => super.메소드(~)
   => super(~) 

[추상 클래스]

> {~} 바디없는 메소드를 한개 이상 소유하고 있거나 [조상 클래스]가 한개 이상 소유하고 있는 [클래스]를 말한다.
   단 조상 클래스 부터 자기 클래스 사이에 이 메소드를 재정의하지 않아야 한다.

[추상 클래스의 특징]

> 추상클래스는 객체화 할 수 없다. 추상 메소드 호출이 불가능하기 때문이다.
> 추상클래스가 소유한 추상 메소드 에는 private, static, final이 붙을 수 없다.
   => static 이 붙으면 객체 생성 없이 클래스명.메소드(~)형식으로 호출이 가능하지만 {바디}가 없으므로
        호출이 불가능하다
> 추상클래스를 상속받은 서브클래스가 추상클래스가 소유한 모든 추상메소드를 재정의하면
   서브클래스는 객체화 가능한 일반클래스가 된다.
> 추상클래스를 상속받은 서브클래스가 추상클래스가 소유한 모든 추상메소드를 재정의하지 않으면
   서브클래스도 추상클래스가 된다.

[abstract 주의]

> 자기 클래스 또는 조상클래스 누구도 바디 없는 메소드를 가지고 있지 않더라도
   abstract 를 붙일 수 있다.
> 객체화 금지의 목적이거나
> 추후 { }없는 메소드를 추가하여 추상 클래스를 만들 예정일 경우 일반클래스에도 abstract 를 붙인다.

[상속 관련 클래스의 객체화 형식]

[메소드/ 속성변수의 호출방식]
[호출 가능 여부]

> 서브클래스명   객참변수 = new 서브클래스생성자명(~);

> 슈퍼클래스명   객참변수 = new 서브클래스생성자명(~);
            => 이때 서브클래스의 고유메소드/고유속성변수는 호출이 불가능하다.
           => 임의의 2개 이상의 클래스 중 무작위로 선택된 임의의 클래스가 객체화 될 경우
                 객참변수의 자료형을 무엇으로 선언할 지 딜레마에 빠지는 경우가 있으므로
                 이를 해결하기 위해 객체 생성 대상 모든 클래스에게 하나의 슈퍼클래스를 만들어주고
                  객참변수의 자료형을 슈퍼클래스로 허락해주면 해결이 된다.

[부모클래스] -   Z클래스 {  z1() { 실행구문1 }  }  

[자식클래스] - A클래스 { a1() {~~} , z1() {실행구문2} }
[자식클래스] - B클래스 { b1() {~~} , z1() {실행구문3} }
[자식클래스] - C클래스 { c1() {~~} , z1() {실행구문4} }

Z a = new ? ( ); 
a.z1();

[인터페이스]

> public, final, static의 성격을 가진 [속성변수]
> public, abstract 의 성격을 가진 [메소드]
   로만 구성된 단위 프로그램이다.
     => [추상 메소드]와 [일반 메소드]가 섞여 있으면 [추상클래스]라고 한다.

[인터페이스의 사용 목적]

> [인터페이스]에 정의한 [추상메소드]를 다른 클래스에서 재정의하여 사용하므로
   [클래스의 메소드 제작 명세표] 역할을 한다.
      => 인터페이스에 계획된 메소드 명을 만들고 클래스가 이 메소드 이름만 그대로 가져다 
           실행구문을 만듦으로서 계획된 메소드로 구성된 클래스를 만들 수 있다.
> 다중 구현이 가능하므로 클래스의 단일 상속이 가지는 문제점인 확장성, 재사용성의 한계를 보완한다.


[interface의 형식]

[public]    interface    인터페이스명 {

      public   static   final   자료형   속성변수 = 데이터;

      public   abstract   리턴형   메소드명( [자료형 매개변수] );
}
   => [속성변수], [메소드]는 각각 0개이상 나올 수 있다.
   => [인터페이스]가 소유한 [속성변수] 앞에 public, final, static 이 생략되어도
        public, final, static 의 성질을 가진다.
   => [인터페이스가 소유한 [추상메소드] 앞에 public, final, statc 이 생략되어도
        public, final, static 의 성질을 가진다.

   => [인터페이스]는 클래스와 같은 생성자가 없다.

[interface의 상속과 interface의 구현]

> [인터페이스]가 다른 [인터페이스]에게 멤버를 물려주는 것을 상속(inheritance)라고 한다.
     => 이때 다른 [인터페이스]에게서 물려받은 [추상메소드]를 재정의 하면 안된다([인터페이스니깐)
     => 이때 다른 [인터페이스]에게서 물려받은 [속성변수]를 갱신 할 수 없다(final 성격이 있으니깐)
     => [클래스]가 다른 [클래스]에게 멤버를 물려주는 것도 상속이다.
> [인터페이스]가 다른 [클래스]에게 멤버를 물려주는 것을 구현(implements)라고 한다.
      => 이때 [인터페이스]에서 물려받은 [추상메소드]를 모두 재정의 해야만 객체화가 가능한 [일반클래스]가 된다.
          다 재정의 하지 않으면 추상클래스가 된다. 오버라이딩 하면 일반클래스가 된다.
      => 이때 [인터페이스]에서 물려받은 [속성변수]를 갱신할 수 없다. (final 성격이 있으니까)
      => 이때 [인터페이스]와 [클래스]를 [부모자식관계]라고 표현하지 않는다.
           부모 자식관계는 클래스 사이의 상속만 가능하다

[인터페이스 상속 형식 ]


[public] interface   인터페이스명1 {
   ...
} 

[public] interface   인터페이스명2    extends    인터페이스명1 {
   ...
}

[인터페이스 구현 형식]


[public]   interface   인터페이스명1 {
   ....
}
[public]   class   클래스   implements   인터페이스명1 {
   ....
}

[interface 특징]

> 인터페이스의 속성변수는 static 성격이므로
   new 에 의한 객체 생성 없이 "인터페이스명.속성변수"로 호출이 가능하다.
> 인터페이스가 소유한 추상메소드 앞에 public, abstract 가 붙지 않아도
   public, abstract 성질을 가진다.
> 인터페이스를 구현한 클래스는 메소드를 재정의 할 때 반드시 public 접근 지정자를 붙여야 한다.
> 다중상속가능
   => 여러개의 인터페이스가 하나의 인터페이스에게 상속해줄 수 있다.
> 다중구현가능
   => 여러 인터페이스에게 상속받은 클래스는 왜 없냐면 그놈을 호출할 일이 없기때문에 상속이 아니다.
   => 여러 인터페이스 - 클래스 간의 다중 구현은 가능하다.


[인터페이스를 구현한 클래스의 객체화 형식과 메소드/속성변수 호출]


인터페이스구현클래스명  객참변수 = new 인터페이스구현클래스생성자명(~);
     
     호출 가능(o)
        > 객참변수.인터페이스구현클래스의 고유메소드(~) 
        > 객참변수.인터페이스구현클래스의 고유속성변수
        > 객참변수.인터페이스구현클래스의 재정의메소드(~)
        > 객참변수.인터페이스의 속성변수

인터페이스명     객참변수 = new 인터페이스구현클래스생성자명(~);

     호출 불가능(x)
          > 객참변수.인터페이스구현클래스의 고유메소드(~)
          > 객참변수.인터페이스구현클래스의 고유속성변수
     호출 가능(o)
          > 객참변수.인터페이스구현클래스의재정의메소드(~)
          > 객참변수.인터페이스의속성변수
          > ((인터페이스구현클래스명)객참변수).인터페이스구현클래스의고유메소드(~)
          > ((인터페이스구현클래스명)객참변수).인터페이스구현클래스의고유속성변수

z 인터페이스
z1(~);

<z인터페이스를 구현>
a클래스
{ z1(){실행구문1}
  a1(){~}
}
b클래스 
{ z1(){실행구문2} 
  b1(){~}
}
c클래스 
{ z1(){실행구문2} 
  c1(){~}
}

Z.xxx = new ? ();
xxx.z1();
xxx.a1();
xxx.b1();
xxx.c1();










