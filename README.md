# 오라클 DB의 실행 계획 비교 도구

이 도구는 오라클 데이터베이스가 여럿 있을 때, 같은 쿼리가 각각 다른 데이터베이스에서 실행 계획이 달라지는지 먼저 확인하기 위한 것이다.

인덱스 생성시 실행계획이 어떻게 달라지는지 확인하거나, DB 버전이 다를 때 실행계획이 변경되는지 확인하는 용도로 사용하기 좋다.

VBA macro를 이용해서 작성되었으며, Oracle를 위한 윈도우용 ODBC 드라이버와 TNS 정보는 미리 구성 돼 있어야 한다.

Oracle AWR을 이용해서 실행계획을 비교, 차이나는 실행계획을 비교해서 출력해준다.

* 테스트된 DB: Oracle 10g, Oracle 11g

### 작동흐름

1. "대상 모듈", "sql_id", "조회대상 object_name" 조건은 "AND" 조건으로 사용된다.
2. 해당 조건을 총족하는 SQL문과 실행계획을 "원본 DB"의 AWR에서 추출한다.
3. 추출한 SQL을 가지고 "비교대상 DB"에서 실행계획을 만들어 본다. (explain plan)
4. "원본 DB"의 실행계획과 "비교대상 DB"의 실행계획을 비교해서 결과를 엑셀의  "Plans" 시트에 표시한다.

### "기초정보입력" 화면

![Main UI](https://cloud.githubusercontent.com/assets/20263138/17649504/d7c96218-6271-11e6-97e2-76cb808483a1.JPG)


### "Plans" 화면

![Plans UI](https://cloud.githubusercontent.com/assets/20263138/17649569/c3eab27c-6273-11e6-8540-fd18ff722153.jpg)

