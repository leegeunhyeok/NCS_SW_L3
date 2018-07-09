# 응용 SW 기초기술 활용

## 운영체제 구성요소
- 프로세스 관리자
- 주기억장치 관리자
- 파일 관리자
- 장치 관리자

## 운영체제의 사용 목적
- 편리성
- 호율성

## 운영체제 성능 평가 기준
- 처리능력, 반환시간, 신뢰도, 사용가능도

## 컴퓨터 구성 장치
- 입력장치
- 출력장치
- 연산장치
- 제어장치

## 데이터베이스
- `DDL (Data Definition Language)` : 데이터 정의어
    - CREATE
    - DROP
    - ALTER
    - INDEX

- `DML (Data Manipulation Language)` : 데이터 조작어
    - SELECT
    - INSERT
    - UPDATE
    - DELETE

- `DCL (Data Control Language)` : 데이터 제어어
    - GRANT
    - REVOKE
    - COMMIT
    - ROLLBACK

## 통신
- OSI 7계층
- FTP (File Transfer Protocol)
- Telnet: 원격 HOST에 접속하는 명령어
- Ping: HOST가 살아있는지 죽어있는지 체크하는 명령어
- HTML (Hyper Text Markup Language)

# 오라클 Database

```SQL
-- system 유저로 접속
conn system

-- 비밀번호 입력
Enter password: 1234

-- sysdba 유저로 접속
conn /as sysdba

-- system 유저 이름을 hrdkorea로 변경
ALTER USER system IDENTIFIED BY hrdkorea

-- reservation_tbl 테이블 생성
-- Commend Line 에서 우클릭 시 붙여넣기 됨
CREATE TABLE reservation_tbl (
    lentno VARCHAR2(6) PRIMARY KEY, -- 기본키는 NOT NULL 포함 됨
    custname VARCHAR2(20),
    bookno VARCHAR2(3),
    outdate date,
    indate date,
    status char(2)
);

-- 생성 된 테이블 정보 확인
DESC reservation_tbl;

-- 데이터 삽입 (INSERT)
-- 컬럼 명 지정 방식
INSERT INTO reservation_tbl (lentno, custname, bookno, outdate, status) VALUES ('1', '김한국', '101', '20171201', '1');

-- 모든 컬럼에 추가할 경우 컬럼 명 생략 가능
INSERT INTO reservation_tbl VALUES ('2', '진선미', '102', '20171204', '20171206', '2');

-- AS로 별칭 지정 가능
SELECT count(*) AS "데이터 수" FROM reservation_tbl;
```