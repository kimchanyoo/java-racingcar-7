# 자동차 경주

## 기능 목록

### 1️⃣ 입력 기능
1. [ ] **자동차 이름 입력**
    - 요구 사항
        1. n개의 자동차 이름을 입력받아야 한다
        2. 각 자동차는 쉼표(,)를 기준으로 구분한다
    - 예외 처리 사항
        1. 자동차의 이름의 길이가 0인 경우
        2. 자동차의 이름의 길이가 5이상인 경우
        3. 중복된 자동차의 이름을 입력한 경우
2. [ ] **이동 횟수 입력**
    - 요구사항
        1. 이동횟수를 입력받는다
    - 예외 처리 사항
        1. 입력받은 이동 횟수가 숫자가 아닌 문자일 경우
        2. 양수가 아닌 0이나 음수가 입력된 경우

### 2️⃣ 게임 진행 기능
1. [ ] **무작위 값 추출**
    - 요구 사항
        1. 각 자동차별로 0 ~ 9 사이에서 무작위 값을 구함
2. [ ] **전진 여부 구분**
    - 요구 사항
        1. 추출한 무작위 값의 크기가 4이상인지 확인
        2. 4이상인 경우 1칸 전진 시킨다

### 3️⃣ 출력 기능
1. [ ] **각 이동 결과 출력**
    - 요구사항
        1. 각 이동이 끝날 때마다 자동차마다 전진 현황에 대해서 보여준다
2. [ ] **우승자 출력**
    - 요구사항
        1. 이동이 모두 끝난 이후 가장 멀리 간 자동차를 우승자로 만든다
        2. 만약 같은 거리를 간 자동차가 있을 경우 공동 우승자 처리를 한다


### 입력
- 경주할 자동차 이름(이름은 쉼표(,) 기준으로 구분)
```
pobi,woni,jun
```
- 시도할 횟수
```
5
```

### 출력
- 차수별 실행 결과
```
pobi : --
woni : ----
jun : ---
```
- 단독 우승자 안내 문구
```
최종 우승자 : pobi
```
- 공동 우승자 안내 문구
```
최종 우승자 : pobi, jun
```

### 실행 결과 예시
````
경주할 자동차 이름을 입력하세요.(이름은 쉼표(,) 기준으로 구분)
pobi,woni,jun
시도할 횟수는 몇 회인가요?
5

실행 결과
pobi : -
woni :
jun : -

pobi : --
woni : -
jun : --

pobi : ---
woni : --
jun : ---

pobi : ----
woni : ---
jun : ----

pobi : -----
woni : ----
jun : -----

최종 우승자 : pobi, jun
````
### 참고사항
- 모든 예외는 `IllegalArgumentException`으로 처리한다.
- 프로그램은 예외 발생 시 해당 메시지를 출력하고 종료된다.
- 단위 테스트와 통합 테스트는 같은 시나리오를 기반으로 한다.

## 프로그래밍 요구 사항 1
- JDK 21 버전에서 실행 가능해야 한다.
- 프로그램 실행의 시작점은 `Application`의 `main()`이다.
- `build.gradle` 파일은 변경할 수 없으며, 제공된 라이브러리 이외의 외부 라이브러리는 사용하지 않는다.
- 프로그램 종료 시 `System.exit()`를 호출하지 않는다.
- 프로그래밍 요구 사항에서 달리 명시하지 않는 한 파일, 패키지 등의 이름을 바꾸거나 이동하지 않는다.
- 자바 코드 컨벤션을 지키면서 프로그래밍한다.

## 프로그래밍 요구 사항 2
- indent(인덴트, 들여쓰기) depth를 3이 넘지 않도록 구현한다. 2까지만 허용한다.
    - 예를 들어 while문 안에 if문이 있으면 들여쓰기는 2이다.
    - 힌트: indent(인덴트, 들여쓰기) depth를 줄이는 좋은 방법은 함수(또는 메서드)를 분리하면 된다.
- 3항 연산자를 쓰지 않는다.
- 함수(또는 메서드)가 한 가지 일만 하도록 최대한 작게 만들어라.
- JUnit 5와 AssertJ를 이용하여 정리한 기능 목록이 정상적으로 작동하는지 테스트 코드로 확인한다.

### 라이브러리
- `camp.nextstep.edu.missionutils`에서 제공하는 `Randoms` 및 `Console` API를 사용하여 구현해야 한다.
    - Random 값 추출은 `camp.nextstep.edu.missionutils.Randoms`의 `pickNumberInRange()`를 활용한다.
    - 사용자가 입력하는 값은 `camp.nextstep.edu.missionutils.Console`의 `readLine()`을 활용한다.

### 사용 예시
- 0에서 9까지의 정수 중 한 개의 정수 반환
````
Randoms.pickNumberInRange(0, 9);
````