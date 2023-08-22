# 할 일 관리 웹 어플리케이션 
- 할 일을 등록 후 완료 또는 삭제 할 수 있고.
- 할 일 목록을 CSV 파일로 다운로드 받을 수 있다.
- 이외 사용자 로그인과 로그아웃, 프로필 이미지 업로드를 제공한다. 

# Application Architecture
- Server-side application would be clean architecture
- 외부에서 내부로 들어가는 의존관계와 영역별 역할 정의에만 집중한다. 

# 제약사항
- 웹 프레임워크로 Spring MVC만 사용해 개발 (보안에 관계된 spring security는 사용하지 않는다)
- 템플릿 엔진은 Thymeleaf를 사용
- 빌드 시스템은 Gradle을 사용

# Dependency
- Gradle을 이용한다. 
- Spring Web
- Thymeleaf
- Validation
- Spring Data JPA
- H2 Database

# 클라이언트 사이드 프로젝트 
TodoApp Client를 사용. (Thymeleaf와 vue.js로 만들어졌다.)

# 서버 사이드(Server-side) 요구사항 및 기능 정의
- 클라이언트 요청에 대해 적절한 응답 컨텐츠(정적 자원, HTML, CSV)을 제공하고, WEB API 요청시 JSON 컨텐츠를 응답해야한다. 
1) 정적 자원 제공
- http(s)://{domain}/assets/**로 접근시 매칭되는 정적 자원을 제공해야한다. 제공할 자원은 웹 클라이언트 내부 assets 폴더의 파일(css, img, js)들이다.
2) 할 일 관리
- 페이지
http(s)://{domain}/todos로 접근시 todos.html 템플릿을 보여줘야한다. 해당 템플릿에는 사이트 작성자와 설명을 노출하는 기능을 가지고있다. 
site.author, site.description에 해당 모델을 제공해야함
- API
할 일(todo) 목록 조회 및 관리(등록, 수정, 삭제, 완료) Web API를 제공해야 한다. 
공백을 제거하고, 최소 4자 이상으로 작성해야한다. 
도메인 모델 및 애플리케이션 서비스 컴포넌트는 클라이언트 요구사항에 맞춰 개발자가 별도로 설계 및 구현해도되나, 워크숍 과정에서는 빠른 학습 진행을 위해
다음 모델 및 인터페이스를 사용
