# SearchEverything

### 빠르게 정확한 파일 검색.
#### Search Faster, Accurately. Written in Swift

<p align="center"><img src="Images/스크린샷 2024-05-13 09.25.52.png" height="500"/></p>

[다운로드](https://github.com/ImBada/SearchEverythingForMac/releases/download/latest/SearchEverythingLatest.dmg) (최신 버전 2.0.1)

최소 사양: 14.0 이상

### 특징
- 타이핑 시 실시간으로 탐색
- 순수한 파일 탐색에 특화된 검색 기능 (정확한 파일명 기준 혹은 폴더명 기준 검색)
- 다양한 정렬 옵션
- Quick Look (훑어보기) 지원 (파일 선택 후 스페이스 바, 이후 방향키나 마우스 등으로 선택 전환 가능)
- 검색 결과를 기준으로 파일명을 일괄 수정
- 파일 삭제, 폴더에 드래그 시 복사/이동 등 Finder와 비슷하게 작동하는 UX

### 개요

폴더 기준 검색, 정확한 파일명 검색, Latin Extended 무시, 메모리에 인덱싱하여 엄청 빠른 검색, 네이밍 규칙을 따른 파일의 시각화, 다양한 정렬, 네이티브 Quick Look (훑어보기) 지원 등의 기능이 구현돼있습니다.
즉석으로 영상을 계속 찾아야 하는 라이브 VJ 용도를 중심으로 개발된 것이나 어렵지 않은 기능이라면 요청 시 구현이 가능합니다. 다만 Swift 초보입니다...

빠른 검색을 위해 인덱싱은 기본으로 켜두는 것을 추천합니다. 인덱싱이 완료되면 하단의 경로명 앞에 초록색 원이 보이며, 인덱싱된 데이터를 기반으로 검색합니다.
문제가 발생하는 경우에만 인덱싱을 꺼서 로컬 검색을 사용해주세요.
인덱싱의 장점은 매우 빠르다는 것이고, 단점은 Latin-1과 같은 특수 알파벳 검색 처리에 약하다는 것이나 대부분의 경우 큰 문제가 아닙니다. 또한 인덱싱 시점 이후의 파일/폴더의 변동사항은 검색되지 않습니다. (체크 해제 후 다시 선택 시 재인덱싱합니다.)
인덱싱은 경로를 바꿀 때마다 새로 진행됩니다.

### 주의할 점

- 탐색 경로 안에 파일이 많은 경우 검색이 더 오래 걸립니다. 본 프로그램은 약 2만 개의 파일로 이루어진 700GB 정도의 데이터를 대상으로 테스트를 진행했습니다.
- 경로 내에 클라우드 저장소나 FTP와 같은 원격 저장소 등이 있을 경우 문제가 발생할 수 있습니다. 로컬로만 이루어진 환경에서 사용하는 것을 권장드립니다.
- 폴더 접근에 문제가 생기거나 검색에 오류가 발생하면 개발자에게 알려주세요.

### 사용법

1. 프로그램 연 후 [경로 선택]을 눌러 파일을 검색할 경로를 선택합니다.
   1. 인덱싱은 기본 설정(켜짐)으로 두시는 것을 권장합니다. 자세한 내용은 위 개요를 참고해주세요.
2. 검색합니다.

### 조작법

- 파일을 하나 선택한 상태로 키보드 상/하로 선택된 파일을 이동할 수 있습니다. (이 상태에서 커맨드 + C 입력 시 경로를 제외한 파일명이 복사됩니다.)
- 드래그 앤 드랍의 기본적인 기능은 다 작동합니다.
- 우클릭 메뉴에 파일 삭제, 이름 변경 등의 기능이 있습니다.
- 파일을 선택한 후 **스페이스 바**를 누르면 Quick Look (훑어보기) 창이 나타납니다. 창 크기를 조절 후 SearchEverything에서 계속 조작을 하면 훑어보기 창을 유지한 상태로 미리보기를 전환할 수 있습니다. 이 상태로 방향키, 마우스로 선택된 파일 전환을 해도 됩니다. 검색 수정 시 가장 마지막으로 연 창이 유지됩니다.
- 중복되는 단어의 경우 큰따옴표로 묶으면 해당 키워드가 고정됩니다. 예) "fure fure" (Fure Fure Mirai라는 파일을 검색하는 경우)
  옵션
- 폴더 이름 일치 시 폴더 내 모든 파일 포함
  - 폴더에 일치하는 이름이 있는 것을 우선으로 검색합니다. 파일명에도 매치가 있는 경우 결과에 포함됩니다. ![스크린샷 2024-05-12 08.28.16.png](Images/스크린샷%202024-05-12%2008.28.16.png)
- 파일 이름 아래 폴더 정보 비표시
  - 저의 편의상 파일의 이름 아래에 폴더명이 태그처럼 표시됩니다. 또한 폴더명에 \|가 있는 경우 해당 문자를 기준으로 태그가 분리됩니다.
  - 이것이 보기 불편한 경우 본 옵션을 체크하시면 파일명만 나옵니다.![스크린샷 2024-05-12 08.29.39.png](Images/스크린샷%202024-05-12%2008.29.39.png)

### 네이밍 규칙

- 애니송 VJ를 위해 직접 정한 macos에서 사용하는 네이밍 규칙이 있습니다.
  - 곡명 {아티스트명} (종류OP/ED) [작품명].확장자
    - 곡명의 경우 일본어라면 \|로 구분한 후 영어 발음을 그대로 뒤에 표기 ex) 光 \| Hikari
      - 아티스트명의 경우 생략 가능 (생략 시 {}까지 완전히 지울 것
      - 종류는 일반 크레딧의 경우 OP1/ED1와 같이 표기. 논크레딧의 경우 NCOP1/NCED1과 같이 표기. 버전이 다를 경우 NCOPv1과 같이 표기. 특정 에피소드에만 나오는 노래의 경우 버전 넘버링보단 NCED EP7과 같은 방식을 선호함.
      - 작품명은 기본적으로 폴더의 가장 첫 구분 이름 (\|로 나눈 경우)을 그대로 넣음. 폴더에 관해선 아래 설명 참고.
      - 폴더명은 한국어 공식, 한국어 비공식(고전애니의 경우), 일본어, 영어 순서로 \|로 나누어 폴더 명에 한 번에 넣음. ex) 이것은 좀비입니까? \| これはゾンビですか? \| Kore wa Zombie Desuka?
  - 위의 규칙을 따르고 영상 파일인 경우, 확장자 표시를 생략하며 종류가 오른쪽에 표시됩니다. ![스크린샷%202024-05-12%2008.31.45.png](Images/스크린샷%202024-05-12%2008.31.45.png)
- 원하시는 규칙이 있으면 추가 문의를 보내주세요.

제보 페이지 [github.com/ImBada/SearchEverythingForMac/issues](https://github.com/ImBada/SearchEverythingForMac/issues)

### 크레딧

개발 임바다 [twitter.com/BD_MARU](https://twitter.com/BD_MARU)
