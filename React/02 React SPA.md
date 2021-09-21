# React SPA

## Achievement Goals
 - SPA(Single-Page Application) 개녕 이해
 - SPA 장단점 이해
 - 와이어프레임 보고 컴포넌트 구분

## SPA
=> 문서 전체가 아닌 업데이트에 필요한 데이터만 받아서 화면에 보여주는 형식

### 장점
- 필요한 부분만 렌더링 하기 때문에 사용자의 행동에 빠르게 반응
- 서버에서 요청 받은 데이터만 넘겨주면 되기에 과부하가 줄어듦
- 전체 페이지 렌더링x 유저환경 좋아짐

### 단점
- SPA 경우 자바스크립트 파일이 크므로, 첫 화면 로딩시간이 길다.
- SEO(검색 엔진 최적화)가 좋지 않음 // HTML 파일에 별다른 자료 없음

# React Router
## Achievement Goals

- React에서 npm으로 React Router DOM을 설치(`npm install react-router-dom`) 
- React Router DOM으로 SPA 구현
- 라우팅 구조 짜기 && 문법 배우기

## React Router
### Routing 이란❓
=> 다른 주소에 따라 다른 뷰를 보여 주는 과정 (경로에 따라 변경)
-> react에는 이 기능이 없으므로 직접 주소마다 보여줘야함
-> react SPA는 이를 위해 react router라는 브라우저를 가장 많이 쓴다.


#### 주요 컴포넌트

- 라우터 역할 router
-> `BrowserRouter`
- 경로 매칭 route matcher
-> `Switch` `Route`
- 경로 변경 Link
-> `Link`

`import{BrowserRouter,Switch,Route,Link}from "react-router-dom`
-> 컴포넌트 사용하기 위해 라이브러리에서 불러오기
