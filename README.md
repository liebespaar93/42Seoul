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
    42>$echo t???.txt => 첫글자가 t이면서 4글자인 txt파일
    42>$echo \특수문자  => 이경우 특수문자를 출력한다 (같은것 '', 조금 다른것 "" 안에 $가있을경우 저장된 값을 찾는다)
- cat과 more 차이 head, tail, grep
  --cat => 파일을 전체적으로 보여준다
  --more => /로 검색어를 입력해 찾을수 있다
  -- head -n 2 파일.txt => 원하는 줄을 보여준다
  -- head -c 9 파일.txt => 원하는 문자 수만큼를 보여준다
  -- tail => head와 같고 뒤에서 부터 보여준다
  -- cat -e 파일.txt => $가 추가되어 보여준다
  -- grep simple(찾을내용) 파일.txt => 처음으로 줄을 찾아 보여준다
  -- grep -v simple(찾을내용) 파일.txt => 모든 줄을 찾아 보여준다
  -- grep -i Simple(찾을내용) 파일.txt => 대소문자를 무시하고 찾아준다
- 명령어 같이 쓰는 방법 stdout, stderr, stdin, 입출력 방식에 대한정보(>, 2>, >> 등)
  42>$ ls | grep txt => 검색에 맞는 리스트를 보여준다
  42>$ ls > rex.txt => rex.txt 에 리스트의 목록을 저장한다
  42>$ ls 찾을거 > res.txt => 결과 출력을 res.txt에 저장한다
  ### 나중에 "2>에관한 입출력 방식에대한 정보"https://cloud-oky.tistory.com/43
  42>$ cat batman.txt | grep 찾을내용 | wc -l => 파일의 줄의 갯수를 찾아준다
  42>$ cat << FIN (출력시작문자)
  > 입력할 내용
  > 내용2
  > FIN (끝네기 처음시작한 문자를 입력해준다)
  입력할 내용
  내용2
- find, wc, bc 에 관하여
  -- find => 찾는 파일을 찾아준다
  -- find . -name 찾을 파일 => 현재 위치에서 찾아준다 
  -- find . -type d => 폴더를 찾아준다
  -- find . -maxdepth 숫자 => 깊이를 지정하여 찾아준다
  -- wc -l 파일.txt => 줄 갯수를 알려준다
  -- wc -w 파일.txt => 단어의 갯수를 알려준다
  -- wc -c 파일.txt => 문자의 갯수를 알려준다
  -- bc => 수학적 계산을 할수 있다 (파이썬 같이 실행된다)
- cat, 
  -- cat 그대로 출력해준다 (파이썬같음)
8. git에 관하여 
- init, add, rm, commit 에관하여
  -- init => 깃을 생성해준다
  -- git status => 상태를 알려준다
  -- git diff => 변경사항을 알려준다.
  -- git add => 수정된 사항을 적어준다
  -- git commit -m "수정되었다" => 수정된 사항을 내용을 남겨 저장한다(전에거와 비교하여 저장한다)
- log, checkout, branch, reset
  -- git log 변경 저장된 메세지들을 보여준다 
  -- git branch 작업위치를 보여준다
  -- git branch -d 작업이름 => 작업이름을 삭제한다
  -- git branch -b 작업이름 => 작업이름을 생성한다
  -- git checkout 작업위치를 변경한다
  -- git reset HEAD 작업이름 => 작업이름으로 돌아간다
