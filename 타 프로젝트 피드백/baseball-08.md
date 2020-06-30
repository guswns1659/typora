## 좋은점 

- 깃허브  프로젝트를 각 클래스 별로 진행하지 않고 팀 전체가 함께 진행하는 점.

- CommonStatics로 상수를 관리하는 점 

  ```java
  public class CommonStatics {
  
      public static final String OAUTH_URL_LOCAL = "https://github.com/login/oauth/authorize?client_id=cee445a015d00ce7828f&scope=user:email";
      public static final String OAUTH_URL_SERVER = "https://github.com/login/oauth/authorize?client_id=8d92d01b11ba14d3d18f&scope=user:email";
  
      public static final String HEADER_ACCEPT = "Accept";
      public static final String HEADER_MEDIA_TYPE = "application/json";
      public static final String GITHUB_ACCESS_TOKEN_URL = "https://github.com/login/oauth/access_token";
      public static final String GITHUB_USER_INFO_URL = "https://api.github.com/user";
  
      public static final String USER_ID = "userId";
      public static final Integer EXPIRE_TIME = 60*60*6;
  
      public static final String HEADER_LOCATION = "Location";
      public static final String REDIRECT_URL = "http://13.125.56.23";
  
      public static final String HIT = "H";
      public static final String STRIKE = "S";
      public static final String BALL = "B";
      public static final String OUT = "O";
  
      public static final int RANDOM_BOUND = 100;
  }
  ```

  

- 깃허브 로그인 성공하면 메인 페이지로 redirect 시키기.

  ```java
  cookie.setMaxAge(EXPIRE_TIME);
          response.addCookie(cookie);
          response.setHeader(HEADER_LOCATION, REDIRECT_URL);
          return new ResponseEntity(HttpStatus.FOUND);
  ```

- JdbcTemplate를 적절하게 사용한 점 

  - GROUP_CONCAT도 사용. 

## 아쉬운점 

- 프로젝트가 끝났는데 프로젝트는 마무리가 안된 상태. 떠난 자리가 다시 한번 보자.
- 테스트 코드가 없는 점.

## 궁금한점 

- response.setHeader(HEADER_LOCATION, REDIRECT_URL); 
  - HEADER_LOCATION에 해당하는 변수가 없는데 어떻게 사용하는지? 