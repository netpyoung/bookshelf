# 삼진규칙
- 어떤 것을 처음할때 : 그냥 한다.
- 2번째로 비슷한 일을 하면 : 중복 때문에 주춤이지만 그냥 중복되게 한다
- 3번째로 비슷한 일을 하면 : 리팩토링 한다.


# 리팩토링 하는 시점
- 기능을 추가할 때
- 버그를 수정할 때
- 코드 리뷰할 때


# 리팩토링을 하면 안될때
- 기존 코드가 엉망이여서 새로 작성하는게 더 나은 경우


# 냄새나는 코드
- 중보된 코드
- 긴 메소드명
- 비대화된 클래스
- 긴 파라미터 리스트
- Switch 문 => 다형성을 생각해라!
- Divergent Change : ex) 한 클래스를 수정시 여러 메소드를 수정해야 하는 경우
- Shotgun Surgery : ex) 하나를 변경시, 여러 클래스를 수정할때
- Feature Envy : ???
- Data Clump : sol) 몰려다니는 여러 데이터를 하나로 묶는다(클래스 or 구조체)
- Primitive Obsession  : ???
- Parallel Inheritance Hierarchies
- Lazy Class
- Speculative Generality(추측성 일반화)
- Message Chain


# 프로그래머의 시간
"무엇을 해야 하지???" | "디자인작업!!" | "코딩!" | "디버깅!!!!"


# 테스트
"클래스는 그 자신의 테스트를 포함해야 한다"


# Refactoring Tip
- 임시 변수가 1번만 사용된다면 inline화 시켜라(1번만 사용되는지 확인하려면, const 제약을 걸어둔다)
- 복잡한 수식이 비교문에 쓰일 경우 boolean 변수에 저장하거나 boolean함수로 빼자.
- Magic Number 제거 비용을 따져봐서, 제거하지 못할시 주석을 달자..
- 배열을 다룰시 각 요소값이 지칭하는 것을 명확하게 알지 못하게 될때에는, 객체로 만들어버리자.
- Exception은 "진짜 예외"만을 위해 사용. 사소한 것은 if문으로 대신해줘라.


# 좋은 인터페이스 - 보여줘야 할 만큼만 보여준다.


# 실제 작업을 하기 위해 필요한 만큼만 리팩토링을 하면 됨. (내일이라도 당장 원래 상태로 되돌릴 수 있게만 만들면 된다)


# 대규모
- 전제 조건 : 프로그래밍 팀 전체의 동의가 필요. 방향을 설정해야함.
- 중요점 : "어떻게 디자인되어야 한다는 완전한 이해가 항상 프로그램에 반영되도록 할 수 있다"


# 리펙토링을 꺼리는 이유
하는일에 대해 완전하게 이해하지 못하고 있다. 작업 기한에 시달리고 있다.


# 안전하게 리펙토링
* 기반
- 여러분의 코딩 능력을 믿어라.
- 여러분이 놓친 에러는 컴파일러가 발견해줄 것이다.
- 컴파일러가 놓친 에러는 test-suite가 발견해 줄 것이다.
- test-suite가 놓친 에러는 코드리뷰에서 발견될 것이다.

* 주의점
- 프로그래머는 오류에 빠질 수 있다.
- 컴파일러가 발견할 수 없는 에러가 있다. ( 특히 상속 관련 )
- 테스트디자이너가 test-suite에서 빠뜨리는 부분도 있다.
- 코드리뷰자도 오류에 빠질 수 있다.

# 리펙토링 후에는
- 코드가 더 낳아졌다면, 작업을 멈추고 릴리즈.
- 코드가 더 낳아지지 않았다면, 작업을 멈추고 그동안 작업한 것을 버린다

# 리펙토링 잘하려면
- 목표를 잡는데 익숙해져라
- 확실하지 않을 때는 멈추어라.
- 되짚어보기 ( 머리를 맑게해라 )
- 둘이서 함께