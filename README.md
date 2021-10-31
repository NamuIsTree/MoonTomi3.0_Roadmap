# MoonTomi 3.0 Roadmap
1. Front End
   <br/> React
2. Back End
   <br/> Spring Boot
3. WAS
   <br/> Spring Boot 내장 Tomcat

## Improvement Point
* 업로드 탭 삭제

  사용성이 좋지 않은 업로드 탭을 삭제 
  기존 업로드 탭에 있던 기능들은 음평회 페이지로 
  
* 장르 enum 삭제

  장르를 따로 관리하는 테이블을 정의
  유동적으로 장르를 추가할 수 없는 기존 환경 대체
  
* 평점 계산 자동화

  Update를 누르지 않으면 반영되지 않는 기존 방식을 버리고
  자동으로 계산하여 반영하도록
  
* 음평회 날짜 기록

  음평회를 진행한 날짜를 기록
* admin 페이지 생성

  별도로 페이지를 관리할 수 있는 admin 페이지 정의
  
* tomcat https 설정

  기존 node.js 서버에서 설정하지 않았던 tls를 적용
  보다 더 안전한 상태 유지
  
* 모바일 최적화

  모바일에서 업로드 기능을 제한하지 않도록
 
* 검색 기능?

  가능하다면 검색까지

## Data Table
* albums : 앨범
  - album_id : 앨범 ID
  - artist_id : 아티스트 ID
  - album_nm : 앨범명
  - album_img : 앨범 아트 link
  - release_ymd : 출시일 (yyyyMMdd)
* album_genre : 앨범 장르
  - album_id : 앨범 ID
  - genre_id : 장르 ID
* artists : 아티스트
  - artist_id : 아티스트 ID
  - artist_nm : 아티스트명
  - artist_img : 아티스트 이미지 link
  - nation : 국적
* genres : 장르
  - genre_id : 장르 ID
  - genre_nm : 장르 이름
  - category_id : 상위 장르 ID (Nullable)
* reviews : 비평
  - review_id : 리뷰 ID
  - reviewer : 리뷰어 별명
  - album_id : 앨범 ID
  - text : 비평글
  - url : 비평한 앨범 관련 URL (spotify / youtube)
  - rating : 평점
  - release_ymd : 발매일
  - review_ymd : 비평일
* comments : 댓글
  - comment_id : 댓글 ID
  - eval_id : 음평회 ID
  - nickname : 평가자 닉네임
  - rating : 별점
  - best1 : 베스트 1 트랙 (track_enum)
  - best2 : 베스트 2 트랙 (track_enum)
  - best3 : 베스트 3 트랙 (track_enum)
  - comment : 한줄평
  - comment_ymd : 평가일
* evaluation
  - eval_id : 음평회 ID
  - badge_id : 뱃지 ID
  - album_id : 앨범 ID
  - eval_ymd : 음평회 날짜
* badges
  - badge_id : 뱃지 ID
  - badge_img : 뱃지 이미지
  - badge_nm : 뱃지 이름
* simples - 간단한 앨범 비평
  - simple_id : 간단한 비평 ID
  - album_id : 앨범 ID
  - rating : 평점
  - simple_ymd : 비평일
* playlists : 싱글 트랙 추천 
  - playlist_id : 싱글 트랙 ID
  - album_id : 앨범 ID
  - rating : 별점
  - date : 추천 날짜
  - url : 추천한 트랙 관련 url (spotify / youtube)
* tracks - 트랙
  - album_id : 앨범 ID
  - track_enum : 트랙 번호
  - track_nm : 트랙 이름
