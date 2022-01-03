# 42Seoul
# Day1 (2021/01/03) 클러스터 처음 해야할것 
  1. 새로운 infra 아이디를 받는다(나의 경우 kyoulee 를 새로 받았다)
  - 비밀번호 재설정
  
  2. 로그인후 mac설정
  - 세팅 설정
  - 언어 설정 (한국어 추가)
  - 키보드 (한국어 변환 설정)
  - 마우스 스크롤 설정(정방향 변경)
  - 이어폰 설정 (블루트스)
  
  3. 상단위의 PLAY_ME(https://www.youtube.com/watch?v=a14XiTXjOow&list=PLVQYiy6xNUxxd5TiZL87_v6JOx61umsUz) 실행
  - 크롬 기본 브라우져 설정 
  - 시큐리티 설정 (잠금화면 바로 보안적용)
  - slack 설정
  
  4. 본 서버 접속하기 (https://signin.intra.42.fr/users/sign_in )
  - 새로 받은 아이디와 비번으로 로그인
  - 보안 서약 작성 (https://signin.intra.42.fr/legal/terms/6?redirect_after_sign=https%3A%2F%2Fprofile.intra.42.fr%2F)
  
  5. 프로젝트 실시
  - 프로젝트 그래프를 보고 내가 선택하여 할 프로잭트를 추가한다
  
  6. ssh-key
  - iterm 실행
  - ssh-keygen 입력
  - 위치설정 (기본 추천)
  - 비밀번호 설정 (안설정하는것을 추천)
  - cat ~/.ssh/id_rsa 으로 확인
  - cat ~/.ssh/id_rsa.pub 으로 ssh-key 보기
  - 인프라 접속(https://profile.intra.42.fr/)
  - 설정 ssh-key 선택
  - 복사한 ssh-key  저장
  
  ** 중간 그룹 정해줌 **
  - 나(경근), 정은, 수진, 현진 과 함께 같이 하게 되었다

  7. 프로젝트 예시 동영상 보기 (https://www.youtube.com/watch?v=eTt5NQUO3LY&list=PLVQYiy6xNUxxhvwi0PGmXb5isUdVwmsg8&index=1)
  * 42 방법
  - 프로젝트 선택 방법
  - 프로젝트 평가 시간 설정
  - 동료평가 설정
  - 동료평가 하기
  * shell 방법
  - man 커멘드
  - file 및 dir 관리하기 (cd, mkdir, mv 등등)
  - 권한 설정 chmod
  - echo, cat, ls, touch
  -- echo => 바로 출력
  -- cat -e => 파일 보기
  -- ls => 지금위치 목록보기
  -- touch => 파일 생성
  - 시스템 명령어 설정 env et export
    42>$truc=bidule
    42>$echo truc => 이경우 echo 명령어의 그대로 출력이 된다
    truc
    42>$echo $truc => 이경우 시스템에 저장된 truc를 찾아 작성된다
    bidule
    - sh
    42>$sh
    sh-3.2$ echo $truc => 아무것도 나오지 않음

    sh-3.2$ exit => 나가기
    exit
    - env
    42>$env => 환경변수를 볼 수 있다
    ...
    내용
    ...
    42>$export truc => 환경변수에 추가 적용한다
    42>$env
    ...
    내용
    truc=bidule => 추가됨
    ...
    42>$sh
    sh-3.2$ echo $truc => 아무것도 나오지 않음
    bidule => sh에 나온다
- wc, echo
-- wc => 파일의 문자줄, 단어수, 크기 를 출력해준다  echo
-- echo => 기능이 많다 (*모두 자리수 상관없음, ?모두 자리수 상관있음)
  42>$echo *.txt => 현제 위치의 모든 txt 파일을 찾아준다
  42>$echo t???.txt => 첫글자가 t 
