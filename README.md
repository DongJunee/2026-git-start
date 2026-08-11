# 2026-git-start

로컬 컴퓨터에서 추가한 내용입니다.

오늘의 학습 목표 'GitHub와 로컬 저장소의 Merge 충돌 해결 실습'

GitHub 웹에서 추가한 내용입니다.

# 2026 Git Start

오늘의 학습 목표: 작업자 B의 Merge 충돌 실습

오늘의 학습 목표: 작업자 A의 Git 협업 실습

오늘의 학습 목표: 작업자 A·B의 Git 협업 및 Merge 충돌 해결

# Python 실습 과정

## 시퀀스 다이어그램

```mermaid
sequenceDiagram
    actor User as 사용자
    participant Main as main_app.py
    participant Basic as magic_calc/basic_ops.py
    participant Advanced as magic_calc/advanced_ops.py
    participant AgeFunc as input_age()
    participant AgeError as AgeException

    User->>Main: 프로그램 실행

    Main->>Main: if __name__ == '__main__' 확인

    alt 직접 실행한 경우
        Main->>Main: print('hi')
    else 모듈로 import된 경우
        Main-->>Main: __main__ 코드 실행 안 함
    end

    Main->>Basic: basic_ops 모듈 호출
    Basic-->>Main: 기본 연산 기능 제공

    Main->>Advanced: advanced_ops 모듈 호출
    Advanced-->>Main: 고급 연산 기능 제공

    Note over Main: 기본 예외 처리 실습

    Main->>Main: raise TypeError('입력값 오류')

    alt TypeError 발생
        Main->>Main: except TypeError as te
        Main->>Main: print(te.args)
    end

    Note over Main,AgeError: 사용자 정의 예외 처리 실습

    Main->>AgeFunc: input_age() 호출
    AgeFunc->>User: 나이를 입력하세요
    User-->>AgeFunc: 나이 입력

    AgeFunc->>AgeFunc: int()로 숫자 변환
    AgeFunc->>AgeFunc: 입력한 나이 검사

    alt age < 0
        AgeFunc->>AgeError: raise AgeException("나이는 양수입니다.")
        AgeError-->>Main: AgeException 발생
        Main->>Main: except AgeException as e
        Main->>User: 예외 메시지 출력

    else age > 150
        AgeFunc->>AgeError: raise AgeException("진짜?")
        AgeError-->>Main: AgeException 발생
        Main->>Main: except AgeException as e
        Main->>User: 예외 메시지 출력

    else 정상적인 나이
        AgeFunc-->>Main: return age
        Main->>Main: else 실행
        Main->>User: 입력한 나이 출력
    end
```

## 프로젝트 구조

```text
my_first_package/
│
├── main_app.py
│
└── magic_calc/
    ├── basic_ops.py
    └── advanced_ops.py
```

## 예외 처리 흐름

`input_age()` 함수에서 입력값을 검사하고 잘못된 나이가 입력되면
`AgeException` 예외를 발생시킨다.

발생한 예외는 `input_age()`를 호출한 부분의 `except AgeException`에서
처리한다.

정상적인 값이 입력되면 `age`를 반환하고 `else` 블록에서 결과를 출력한다.
