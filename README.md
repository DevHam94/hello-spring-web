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