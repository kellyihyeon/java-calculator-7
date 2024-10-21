#  문자열 덧셈 계산기

# 1. 요구 사항 분석

---
## 1.1. 규칙
- 쉼표(,) 또는 콜론(:)을 구분자로 가지는 문자열을 전달하는 경우 구분자를 기준으로 분리한 각 숫자의 합을 반환한다.
  - "" => 0
  - "1,2" => 3
  - "1,2,3" => 6
  - 1,2:3" => 6
  
- 기본 구분자(쉼표, 콜론) 외에 커스텀 구분자를 지정할 수 있다.
  - 커스텀 구분자 - 문자열 앞부분의 "//"와 "\n" 사이에 위치하는 문자
  - "//;\n1;2;3" => 커스텀 구분자: 세미콜론, 결과 값: 6
  
- 입력 값
  - 구분자, 양수로 이루어진 문자열
  
- 출력 값
  - 덧셈 결과

## 1.2. 예외 상황
- 사용자가 잘못된 값을 입력할 경우 IllegalArgumentException 을 발생시킨 후 애플리케이션은 종료되어야 한다.

## 1.3. 결과
```text
덧셈할 문자열을 입력해 주세요.
1,2:3
결과 : 6
```

# 2. 요구 사항 정의서

---
## 2.1. 연산
- 더하기 연산을 할 수 있다.
  - 숫자가 한 개 이면 해당 숫자를 결과 값으로 반환한다.
  - 숫자 두 개를 더할 수 있다.
  - 숫자 여러 개를 더할 수 있다.
  - 소수를 더할 수 있다.

## 2.2. 구분자
- 문자열에 구분자가 없을 수 있다.
  - 구분자가 있는지 확인한다.
  - 구분자가 없으면 문자열을 그대로 반환한다.
- 문자열에 잘못된 구분자가 있는지 확인한다.
  - 잘못된 기본 구분자가 있으면 예외를 발생시킨다.
  - 잘못된 커스텀 구분자가 있으면 예외를 발생시킨다.
- 문자열에서 구분자를 추출할 수 있다.
  - 구분자의 종류로는 기본 구분자와 커스텀 구분자가 있다.
  - 구분자의 타입을 알 수 있다.
  - 기본 구분자의 종류로는 쉼표(,) 또는 콜론(:) 이 있다.
  - 커스텀 구분자는 문자열 앞부분의 "//"와 "\n" 사이에 있다.

## 2.3. 숫자
- 문자열에 숫자가 없을 수 있다.
  - 추출할 수 있는 숫자가 없으면 숫자 0을 반환한다.
- 문자열에서 숫자를 추출할 수 있다.
  - 추출한 숫자는 양수이어야 한다.
  - 음수가 있으면 예외를 발생시킨다.
  - 추출할 수 있는 숫자는 최소 1개이다.

## 2.4. 입력 및 출력
- 사용자에게 입력값을 받을 수 있다.
  - 제공되는 Console API 를 사용한다.
  - 입력값은 문자열로 받는다.
  - 사용자는 아무것도 입력하지 않을 수 있다.
- 사용자에게 출력값을 전달한다.

## 2.5. 문자열 추출
- 입력값의 개행문자를 줄바꿈으로 치환할 수 있다.
  - 테스트로 주어진 `"//;\\n1"` 문자열의 개행문자가 일반 문자열로 인식되므로 줄바꿈으로 치환
- 문자열에서 연산식을 추출할 수 있다.
  - `"//;\n1;2;3"` → `“1;2;3”`

## 2.6. 예외 처리
- 잘못된 값을 입력하면 예외가 발생한다.
  - IllegalArgumentException 발생시키고 애플리케이션을 종료한다.
  - 잘못된 숫자(음수)를 입력한 경우 예외가 발생한다.
  - 잘못된 구분자를 입력한 경우 예외가 발생한다.

# 3. 미션 목표
- [x]  ChatGPT를 사용하지 않는다.
- [x]  TDD로 구현한다.
    - 간단해 보이는 미션이지만 자체적으로 난이도를 조절해보자!
- [x]  조건문을 사용하는 경우 2 depth 를 넘지 않는다.
- [x]  미션을 풀면서 겪은 이슈를 해결한 과정을 기록해 두자.
- [x]  1주차 미션의 회고를 작성해 두자.