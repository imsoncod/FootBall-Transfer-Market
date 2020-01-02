-- 테이블 생성

-- 감독 생성
CREATE TABLE 감독 (
    감독번호   INTEGER PRIMARY KEY,
    감독명    VARCHAR2(30) NOT NULL
);

-- 리그 생성
CREATE TABLE 리그 (
    리그명   VARCHAR2(30) PRIMARY KEY,
    지역    VARCHAR2(20) NOT NULL
);

-- 팀 생성
CREATE TABLE 팀 (
    감독번호   INTEGER NOT NULL,
    리그명    VARCHAR2(30) NOT NULL,
    팀명     VARCHAR2(30) PRIMARY KEY,
    경기장    VARCHAR2(30) UNIQUE,
    자산     INTEGER DEFAULT 0 NOT NULL CHECK(자산=0),
    FOREIGN KEY(감독번호) REFERENCES 감독(감독번호),
    FOREIGN KEY(리그명) REFERENCES 리그(리그명)
);

-- 선수 생성
CREATE TABLE 선수 (
    선수명   VARCHAR2(30) NOT NULL,
    등번호   INTEGER NOT NULL,
    팀명    VARCHAR2(30) NOT NULL,
    포지션   CHAR(3) NOT NULL,
    키     INTEGER NOT NULL,
    몸무게   INTEGER NOT NULL,
    국적    VARCHAR2(20) NOT NULL,
    주발    VARCHAR2(10) NOT NULL,
    PRIMARY KEY(선수명, 등번호, 팀명),
    FOREIGN KEY(팀명) REFERENCES 팀(팀명)
);

-- 매물 생성
CREATE TABLE 매물 (
    매물번호   INTEGER PRIMARY KEY,
    리그명    VARCHAR2(30) NOT NULL,
    팀명     VARCHAR2(30) NOT NULL,
    선수명    VARCHAR2(30) NOT NULL,
    등번호    INTEGER NOT NULL,
    이적료    INTEGER NOT NULL,
    판매여부   CHAR(1) DEFAULT 'N' NOT NULL,
    FOREIGN KEY(리그명) REFERENCES 리그(리그명),
    FOREIGN KEY(선수명, 등번호, 팀명) REFERENCES 선수(선수명, 등번호, 팀명)
);

-- 주문 생성
CREATE TABLE 주문 (
    주문번호     INTEGER PRIMARY KEY,
    매물번호     INTEGER NOT NULL,
    이적리그명    VARCHAR2(30) NOT NULL,
    이적팀명     VARCHAR2(30) NOT NULL,
    이적료      INTEGER NOT NULL,
    이적일자     DATE NOT NULL,
    선수동의여부   CHAR(1) DEFAULT 'N' NOT NULL,
    FOREIGN KEY(매물번호) REFERENCES 매물(매물번호),
    FOREIGN KEY(이적리그명) REFERENCES 리그(리그명),
    FOREIGN KEY(이적팀명) REFERENCES 팀(팀명)
);

-- 레코드 삽입문

-- 리그 삽입
INSERT INTO 리그 VALUES('K리그','대한민국');
INSERT INTO 리그 VALUES('프리미어리그','잉글랜드');
INSERT INTO 리그 VALUES('프리메라리그','스페인');
INSERT INTO 리그 VALUES('세리에A','이탈리아');
INSERT INTO 리그 VALUES('분데스리가','독일');
INSERT INTO 리그 VALUES('리그1','프랑스');
INSERT INTO 리그 VALUES('에레디비시','네덜란드');
INSERT INTO 리그 VALUES('프리미어십','스코틀랜드');
INSERT INTO 리그 VALUES('슈퍼리그','터키');
INSERT INTO 리그 VALUES('수페르리가','덴마크');

-- 감독,팀 삽입
-- K리그
INSERT INTO 감독 VALUES(1,'박지성');
INSERT INTO 팀 VALUES(1,'K리그','FC서울','서울월드컵경기장',3000);
INSERT INTO 감독 VALUES(2,'이영표');
INSERT INTO 팀 VALUES(2,'K리그','FC광주','광주월드컵경기장',2500);
INSERT INTO 감독 VALUES(3,'홍명보');
INSERT INTO 팀 VALUES(3,'K리그','FC강원','춘천송암스포츠타운',4000);
INSERT INTO 감독 VALUES(4,'김병지');
INSERT INTO 팀 VALUES(4,'K리그','FC대구','대구은행파크',1800);

-- 프리미어리그
INSERT INTO 감독 VALUES(5,'클로프');
INSERT INTO 팀 VALUES(5,'프리미어리그','리버풀','안필드',6000);
INSERT INTO 감독 VALUES(6,'과르디올라');
INSERT INTO 팀 VALUES(6,'프리미어리그','맨시티','에티하드스타디움',10000);
INSERT INTO 감독 VALUES(7,'로저스');
INSERT INTO 팀 VALUES(7,'프리미어리그','레스터시티','킹파워스타디움',6000);
INSERT INTO 감독 VALUES(8,'램파드');
INSERT INTO 팀 VALUES(8,'프리미어리그','첼시','스탬퍼드브리지',4000);
INSERT INTO 감독 VALUES(9,'에메리');
INSERT INTO 팀 VALUES(9,'프리미어리그','아스널','에미레이트스타디움',4800);
INSERT INTO 감독 VALUES(10,'솔샤르');
INSERT INTO 팀 VALUES(10,'프리미어리그','맨유','올드트래포드',7000);
INSERT INTO 감독 VALUES(11,'포체티노');
INSERT INTO 팀 VALUES(11,'프리미어리그','토트넘','토트넘스타디움',9000);

-- 프리메라리그
INSERT INTO 감독 VALUES(12,'발베르데');
INSERT INTO 팀 VALUES(12,'프리메라리그','FC바르셀로나','캄프누',13000);
INSERT INTO 감독 VALUES(13,'지단');
INSERT INTO 팀 VALUES(13,'프리메라리그','레알마드리드','산티아고베르나베우',9000);
INSERT INTO 감독 VALUES(14,'시메오네');
INSERT INTO 팀 VALUES(14,'프리메라리그','AT마드리드','메트로폴리타노',7000);
INSERT INTO 감독 VALUES(15,'로페테기');
INSERT INTO 팀 VALUES(15,'프리메라리그','세비야','피스후안',6500);
INSERT INTO 감독 VALUES(16,'카예하');
INSERT INTO 팀 VALUES(16,'프리메라리그','비야레알CF','세라미카',8000);

-- 세리에A
INSERT INTO 감독 VALUES(17,'사리');
INSERT INTO 팀 VALUES(17,'세리에A','유벤투스','알리안츠스타디움',8000);
INSERT INTO 감독 VALUES(18,'콘테');
INSERT INTO 팀 VALUES(18,'세리에A','인테르','주세페메아차스타디움',4700);
INSERT INTO 감독 VALUES(19,'폰세카');
INSERT INTO 팀 VALUES(19,'세리에A','라치오','올림피코스타디움',5500);
INSERT INTO 감독 VALUES(20,'안첼로티');
INSERT INTO 팀 VALUES(20,'세리에A','나폴리','산파올로',8700);

-- 분데스리가
INSERT INTO 감독 VALUES(21,'파브레');
INSERT INTO 팀 VALUES(21,'분데스리가','도르트문트','이두나파크',7500);
INSERT INTO 감독 VALUES(22,'아레나');
INSERT INTO 팀 VALUES(22,'분데스리가','바이에른뮌헨','알리안츠아레나',10000);
INSERT INTO 감독 VALUES(23,'글라스너');
INSERT INTO 팀 VALUES(23,'분데스리가','볼프스부르크','폴크스바겐 아레나',6000);
INSERT INTO 감독 VALUES(24,'보츠');
INSERT INTO 팀 VALUES(24,'분데스리가','레버쿠젠','바이 아레나',4800);

-- 리그1
INSERT INTO 감독 VALUES(25,'투헬');
INSERT INTO 팀 VALUES(25,'리그1','PSG','파르크데프랭스',11000);
INSERT INTO 감독 VALUES(26,'가르시아');
INSERT INTO 팀 VALUES(26,'리그1','올림피크리옹','그루파마스타디움',9000);

-- 에레디비시
INSERT INTO 감독 VALUES(27,'텐하그');
INSERT INTO 팀 VALUES(27,'에레디비시','아약스','요한크루이프아레나',11000);
INSERT INTO 감독 VALUES(28,'보멀');
INSERT INTO 팀 VALUES(28,'에레디비시','PSV','필립스스타디움',8800);

-- 프리미어십
INSERT INTO 감독 VALUES(29,'레논');
INSERT INTO 팀 VALUES(29,'프리미어십','셀틱','셀틱파크',6000);
INSERT INTO 감독 VALUES(30,'제라드');
INSERT INTO 팀 VALUES(30,'프리미어십','레인저스','아이브록스스타디움',4900);

-- 슈퍼리그
INSERT INTO 감독 VALUES(31,'테림');
INSERT INTO 팀 VALUES(31,'슈퍼리그','갈라타사라이','튀르크텔레콤아레나',5200);
INSERT INTO 감독 VALUES(32,'아브즈');
INSERT INTO 팀 VALUES(32,'슈퍼리그','베식타스','보다폰아레나',5100);

-- 수페르리가
INSERT INTO 감독 VALUES(33,'임건태');
INSERT INTO 팀 VALUES(33,'수페르리가','ESC','인하스타디움',1000);
INSERT INTO 감독 VALUES(34,'솔바켄');
INSERT INTO 팀 VALUES(34,'수페르리가','FC코펜하겐','파르켄스타디움',3000);

-- 선수 삽입
INSERT INTO 선수 VALUES('박주영','10','FC서울','FW',177,70,'대한민국','오른발');
INSERT INTO 선수 VALUES('김현명','7','FC서울','FW',174,72,'대한민국','왼발');
INSERT INTO 선수 VALUES('펠리페','9','FC광주','FW',193,90,'브라질','오른발');
INSERT INTO 선수 VALUES('김정환','11','FC광주','MF',175,70,'대한민국','왼발');
INSERT INTO 선수 VALUES('정조국','9','FC강원','FW',185,70,'대한민국','오른발');
INSERT INTO 선수 VALUES('서명원','24','FC강원','DF',185,88,'대한민국','오른발');
INSERT INTO 선수 VALUES('임재혁','15','FC대구','MF',170,65,'대한민국','오른발');
INSERT INTO 선수 VALUES('정승원','18','FC대구','DF',178,72,'대한민국','왼발');
INSERT INTO 선수 VALUES('마네','10','리버풀','FW',177,70,'코트디부아르','오른발');
INSERT INTO 선수 VALUES('살라','7','리버풀','FW',169,65,'이집트','왼발');
INSERT INTO 선수 VALUES('피르미누','9','리버풀','FW',183,70,'잉글랜드','오른발');
INSERT INTO 선수 VALUES('아구에로','9','맨시티','FW',168,72,'아르헨티나','오른발');
INSERT INTO 선수 VALUES('스털링','7','맨시티','FW',171,63,'잉글랜드','오른발');
INSERT INTO 선수 VALUES('워커','4','맨시티','DF',185,70,'잉글랜드','왼발');
INSERT INTO 선수 VALUES('바디','9','레스터시티','FW',189,72,'잉글랜드','오른발');
INSERT INTO 선수 VALUES('마레즈','10','레스터시티','MF',175,63,'이란','오른발');
INSERT INTO 선수 VALUES('윌리안','10','첼시','MF',178,70,'브라질','오른발');
INSERT INTO 선수 VALUES('체흐','1','첼시','GK',193,75,'러시아','오른발');
INSERT INTO 선수 VALUES('음키타리안','6','아스널','MF',178,70,'이탈리아','오른발');
INSERT INTO 선수 VALUES('월콧','7','아스널','FW',171,75,'잉글랜드','오른발');
INSERT INTO 선수 VALUES('포그바','10','맨유','MF',195,80,'프랑스','오른발');
INSERT INTO 선수 VALUES('데헤아','1','맨유','GK',193,75,'잉글랜드','오른발');
INSERT INTO 선수 VALUES('손흥민','7','토트넘','FW',178,70,'대한민국','양발');
INSERT INTO 선수 VALUES('케인','9','토트넘','FW',188,75,'잉글랜드','오른발');
INSERT INTO 선수 VALUES('메시','10','FC바르셀로나','FW',169,70,'아르헨티나','왼발');
INSERT INTO 선수 VALUES('푸욜','4','FC바르셀로나','DF',178,75,'스페인','오른발');
INSERT INTO 선수 VALUES('모드리치','10','레알마드리드','MF',178,73,'크로아티아','양발');
INSERT INTO 선수 VALUES('마르셀루','6','레알마드리드','DF',178,75,'브라질','왼발');
INSERT INTO 선수 VALUES('그리즈만','7','AT마드리드','MF',178,73,'프랑스','오른발');
INSERT INTO 선수 VALUES('사울','8','AT마드리드','DF',183,80,'브라질','오른발');
INSERT INTO 선수 VALUES('세징야','13','세비야','MF',185,72,'아르헨티나','오른발');
INSERT INTO 선수 VALUES('미켈','9','세비야','DF',188,80,'프랑스','오른발');
INSERT INTO 선수 VALUES('호날두','7','유벤투스','FW',188,72,'포르투갈','오른발');
INSERT INTO 선수 VALUES('부폰','4','유벤투스','GK',189,78,'이탈리아','오른발');
INSERT INTO 선수 VALUES('루카쿠','9','인테르','FW',192,85,'가나','오른발');
INSERT INTO 선수 VALUES('산체스','7','인테르','FW',172,70,'잉글랜드','오른발');
INSERT INTO 선수 VALUES('사비','10','라치오','FW',177,70,'스페인','양발');
INSERT INTO 선수 VALUES('임모빌레','5','라치오','FW',185,70,'독일','오른발');
INSERT INTO 선수 VALUES('미르텐스','10','나폴리','FW',178,72,'벨기에','양발');
INSERT INTO 선수 VALUES('요렌테','9','나폴리','FW',192,72,'스페인','오른발');
INSERT INTO 선수 VALUES('로이스','10','도르트문트','FW',179,65,'독일','양발');
INSERT INTO 선수 VALUES('하키미','6','도르트문트','DF',188,80,'스페인','오른발');
INSERT INTO 선수 VALUES('노이어','1','바이에른뮌헨','GK',195,80,'독일','왼발');
INSERT INTO 선수 VALUES('보아텡','4','바이에른뮌헨','DF',188,80,'독일','오른발');
INSERT INTO 선수 VALUES('나우두','18','볼프스부르크','DF',195,75,'브라질','오른발');
INSERT INTO 선수 VALUES('브룩스','8','볼프스부르크','DF',187,75,'독일','오른발');
INSERT INTO 선수 VALUES('베일리','9','레버쿠젠','FW',180,70,'자메이카','오른발');
INSERT INTO 선수 VALUES('파울리뉴','7','레버쿠젠','FW',179,75,'브라질','오른발');
INSERT INTO 선수 VALUES('네이마르','10','PSG','FW',178,65,'브라질','오른발');
INSERT INTO 선수 VALUES('나바스','1','PSG','GK',189,70,'스페인','오른발');
INSERT INTO 선수 VALUES('뎀벨레','9','올림피크리옹','MF',178,65,'가나','오른발');
INSERT INTO 선수 VALUES('트라오레','1','올림피크리옹','GK',191,85,'코트디부아르','오른발');
INSERT INTO 선수 VALUES('데용','7','아약스','MF',178,65,'네덜란드','양발');
INSERT INTO 선수 VALUES('반더바르트','4','아약스','DF',185,85,'네덜란드','오른발');
INSERT INTO 선수 VALUES('마렌','10','PSV','FW',168,65,'브라질','오른발');
INSERT INTO 선수 VALUES('미하타렌','22','PSV','MF',180,85,'이탈리아','왼발');
INSERT INTO 선수 VALUES('기성용','26','셀틱','FW',188,78,'대한민국','오른발');
INSERT INTO 선수 VALUES('테일러','4','셀틱','DF',183,85,'그리스','왼발');
INSERT INTO 선수 VALUES('데포','9','레인저스','FW',185,72,'잉글랜드','오른발');
INSERT INTO 선수 VALUES('잭','13','레인저스','MF',175,80,'잉글랜드','왼발');
INSERT INTO 선수 VALUES('드록바','12','갈라타사라이','FW',191,89,'코트디부아르','오른발');
INSERT INTO 선수 VALUES('팔카오','9','갈라타사라이','MF',178,78,'콜롬비아','오른발');
INSERT INTO 선수 VALUES('알칸타라','13','베식타스','DF',191,80,'독일','오른발');
INSERT INTO 선수 VALUES('비달','8','베식타스','MF',178,75,'스페인','오른발');
INSERT INTO 선수 VALUES('아자르','10','ESC','DF',178,70,'벨기에','양발');
INSERT INTO 선수 VALUES('운채','6','ESC','FW',175,65,'스리랑카','오른발');
INSERT INTO 선수 VALUES('크리스텐센','9','FC코펜하겐','GK',190,70,'덴마크','오른발');
INSERT INTO 선수 VALUES('호글리','8','FC코펜하겐','DF',175,70,'덴마크','왼발');

-- 매물 삽입
INSERT INTO 매물 VALUES(1,'K리그','FC서울','박주영',10,450,'Y');
INSERT INTO 매물 VALUES(2,'프리미어리그','리버풀','피르미누',9,1200,'Y');
INSERT INTO 매물 VALUES(3,'프리미어리그','맨시티','워커',4,850,'Y');
INSERT INTO 매물 VALUES(4,'프리미어리그','토트넘','손흥민',7,1280,'Y');
INSERT INTO 매물 VALUES(5,'프리메라리그','FC바르셀로나','푸욜',4,1100,'N');
INSERT INTO 매물 VALUES(6,'프리메라리그','AT마드리드','그리즈만',7,1400,'Y');
INSERT INTO 매물 VALUES(7,'세리에A','유벤투스','호날두',7,600,'N');
INSERT INTO 매물 VALUES(8,'세리에A','라치오','임모빌레',5,1000,'N');
INSERT INTO 매물 VALUES(9,'분데스리가','도르트문트','로이스',10,1600,'Y');
INSERT INTO 매물 VALUES(10,'분데스리가','바이에른뮌헨','노이어',1,1500,'Y');
INSERT INTO 매물 VALUES(11,'리그1','PSG','네이마르',10,2700,'Y');
INSERT INTO 매물 VALUES(12,'에레디비시','아약스','데용',7,2400,'Y');
INSERT INTO 매물 VALUES(13,'프리미어십','레인저스','데포',9,500,'N');
INSERT INTO 매물 VALUES(14,'슈퍼리그','갈라타사라이','드록바',12,1600,'Y');
INSERT INTO 매물 VALUES(15,'수페르리가','FC코펜하겐','호글리',8,450,'N');

-- 주문 삽입
INSERT INTO 주문 VALUES(1,1,'프리미어리그','아스널',450,'2020-02-18','Y');
INSERT INTO 주문 VALUES(2,2,'리그1','PSG',1200,'2020-01-09','N');
INSERT INTO 주문 VALUES(3,3,'프리미어리그','토트넘',850,'2019-12-26','Y');
INSERT INTO 주문 VALUES(4,4,'프리메라리그','레알마드리드',1280,'2020-05-07','Y');
INSERT INTO 주문 VALUES(5,6,'프리메라리그','FC바르셀로나',1400,'2020-03-07','Y');
INSERT INTO 주문 VALUES(6,9,'에레디비시','아약스',1600,'2019-12-09','N');
INSERT INTO 주문 VALUES(7,10,'프리메라리그','AT마드리드',1500,'2020-03-24','Y');
INSERT INTO 주문 VALUES(8,11,'프리미어십','레인저스',2700,'2020-04-03','Y');
INSERT INTO 주문 VALUES(9,12,'프리메라리그','FC바르셀로나',2400,'2020-06-18','Y');
INSERT INTO 주문 VALUES(10,14,'프리미어리그','첼시',1600,'2020-01-04','Y');

-- 테이블 모든 정보 확인
SELECT  FROM 감독;
SELECT  FROM 리그;
SELECT  FROM 팀;
SELECT  FROM 선수;
SELECT  FROM 매물;
SELECT  FROM 주문;

-- SQL문
-- 1) '프리미어리그'에 소속된 팀들의 이름과 경기장을 출력
SELECT 팀명, 경기장 FROM 팀 WHERE 리그명 = '프리미어리그';

-- 2) 키가 183cm 이상이고 왼발을 사용하는 선수의 이름과 소속팀을 출력
SELECT 선수명, 팀명, 키, 주발 FROM 선수 WHERE 키=183 AND 주발='왼발';

-- 3) 이름이 3글자이고 '드'로 끝나는 감독의 번호와 이름을 출력
SELECT 감독번호, 감독명 FROM 감독 WHERE 감독명 LIKE '__드'; 

-- 4) 골키퍼인 선수의 이름과 국적을 몸무게가 큰순으로 출력
SELECT 선수명, 국적, 몸무게 FROM 선수 WHERE 포지션 = 'GK' ORDER BY 몸무게 DESC;

-- 5) 등록된 매물의 총 개수와 가장 비싼 이적료를 출력
SELECT COUNT() AS 총 매물 개수, MAX(이적료) AS 최고 이적료 FROM 매물; 

-- 6) 리그별로 이적료의 합과 평균을 합이 작은 순서대로 출력, 합이 같은경우 평균이 작은것부터 출력
SELECT 리그명, SUM(이적료) 합, AVG(이적료) 평균 FROM 매물 GROUP BY 리그명 ORDER BY 합, 평균;

-- 7) '클로프' 감독이 운영하는 팀의 이름과 자산 출력
SELECT 팀명, 자산 FROM 감독 INNER JOIN 팀 ON 감독.감독번호 = 팀.감독번호 WHERE 감독명 = '클로프';

-- 8) 이적계약이 된 선수 중 등번호가 7인 선수의 이름과 이적전 팀이름, 이적후 팀이름, 이적일자(YYYY-MM-DD형식으로)를 출력
SELECT 선수명, 팀명, 이적팀명, TO_CHAR(이적일자,'YYYY-MM-DD')이적일자 FROM 매물 INNER JOIN 주문 ON 매물.매물번호 = 주문.매물번호 WHERE 선수동의여부 = 'Y' AND 등번호 = 7;

-- 9) '과르디올라'감독의 운영하는 팀의 공격수 이름을 모두 출력
SELECT 선수명, 포지션 FROM 팀 INNER JOIN 감독 ON 팀.감독번호 = 감독.감독번호 INNER JOIN 선수 ON 팀.팀명 = 선수.팀명 WHERE 감독명 = '과르디올라' AND 포지션 = 'FW' ;

-- 10) 주문된 매물과 주문되지 않은 매물의 정보를 출력하되 주문되지 않음을 보이고 매물 이적료가 1000이상인 매물만 출력
SELECT 리그명, 팀명, 선수명, NVL(이적팀명,'미주문')이적팀명, 주문.이적료 FROM 매물 LEFT OUTER JOIN 주문 ON 매물.매물번호 = 주문.매물번호 WHERE 매물.이적료 = 1000;

-- 11) '프리메라리그'에 소속된 팀에 소속된 미드필더 선수들의 이름과 국적 출력
SELECT 선수명, 국적, 포지션 FROM 선수 WHERE 포지션 = 'MF' AND 팀명 IN(
SELECT 팀명 FROM 팀 WHERE 리그명 = '프리메라리그');

-- 12) 이적료가 전체매물의 평균 이적료보다 큰 선수의 선수명과 등번호, 이적료를 출력하되 이적료가 높은 5명만 출력
SELECT  FROM (SELECT 선수명, 등번호, 이적료 FROM 매물 WHERE 이적료 = (SELECT AVG(이적료) FROM 매물) ORDER BY 이적료 DESC) WHERE ROWNUM = 5;

-- 13) '피르미누'선수가 소속된 리그로 이적하는 선수중 2020년에 이적하는 선수의 이름과 이적료를 출력
SELECT 선수명, 이적료 FROM 매물 WHERE 매물번호 IN(
SELECT 매물번호 FROM 주문 WHERE 이적일자 = '2020-01-01' AND 이적리그명 IN(
SELECT 리그명 FROM 팀 WHERE 팀명 IN(
SELECT 팀명 FROM 선수 WHERE 선수명 = '피르미누')));

-- 14) 매물로 등록되지 않은 선수 중 키가 178cm이상인 공격수의 이름을 출력
SELECT 선수명, 키, 포지션 FROM 선수 WHERE 키 = 178 AND 포지션 = 'FW' AND NOT EXISTS (
SELECT  FROM 매물 WHERE 매물.팀명 = 선수.팀명 AND 매물.선수명 = 선수.선수명 AND 매물.등번호 = 선수.등번호);

-- 15) '슈퍼리그'의 모든 선수들보다 키가 큰 선수의 선수명과 국적을 출력, 또한 키가 195cm이면 '최장신' 나머지는 '-' 표시
SELECT 선수명, 국적, 키, DECODE(키,195,'최장신','-')키순위 FROM 선수 WHERE 키  ALL (SELECT 키 FROM 선수 WHERE 팀명 IN(
SELECT 팀명 FROM 팀 WHERE 리그명 = '슈퍼리그'));

-- 16) '슈퍼리그'에 소속되고 미드필더이거나 'FC서울'에 소속되고 키가 176cm이상인 선수의 선수명을 출력
SELECT 선수명 FROM 선수 INNER JOIN 팀 ON 선수.팀명 = 팀.팀명 WHERE 리그명 = '슈퍼리그' AND 포지션 = 'MF'
UNION
SELECT 선수명 FROM 선수 WHERE 팀명 = 'FC서울' AND 키 = 176;

-- 17) '프리미어리그'이고 키가 178cm이상인 선수의 이름과 등번호, 역할을 출력. 
-- 단 역할은 등번호가 1이면 '골키퍼', 4이면 '중앙수비수', 7이면 '키플레이어', 9이면 '스트라이커', 10이면 '에이스', 나머지는 '자유'표시
SELECT 팀.리그명, 선수.선수명, 선수.등번호, CASE(선수.등번호) 
WHEN 1 THEN '골키퍼'
WHEN 4 THEN '중앙수비수'
WHEN 7 THEN '키플레이어'
WHEN 9 THEN '스트라이커'
WHEN 10 THEN '에이스'
ELSE '자유' END 역할
FROM 팀 INNER JOIN 선수 ON 팀.팀명 = 선수.팀명 INNER JOIN 리그 ON 팀.리그명 = 리그.리그명
WHERE 팀.리그명 = '프리미어리그' AND 키=178;

-- 18) '클로프'감독이 운영하는 팀의 경기장 이름을 '리버풀 아레나'로 변경
UPDATE 팀 SET 경기장 = '리버풀아레나' WHERE 감독번호 IN
(SELECT 감독번호 FROM 감독 WHERE 감독명 = '클로프');

-- 19) '부폰'선수가 속한 리그를 '로마'로 변경
UPDATE 리그 SET 지역 = '로마' WHERE 리그명 IN
(SELECT 리그명 FROM 팀 WHERE 팀명 IN
(SELECT 팀명 FROM 선수 WHERE 선수명 = '부폰'));

-- 20) 주문되어 이적계약까지 체결된 매물을 삭제
DELETE FROM 매물 WHERE 매물번호 IN
(SELECT 매물번호 FROM 주문 WHERE 선수동의여부 ='Y');
