---
title: "Oracle 스키마 컬렉션 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 89a75de8-dee8-45e2-a97f-254d7e62e7e1
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Oracle 스키마 컬렉션
Microsoft .NET Framework Data Provider for Oracle에서는 공통 스키마 컬렉션을 비롯하여 다음과 같은 특정 스키마 컬렉션을 지원합니다.  
  
-   Columns  
  
-   Indexes  
  
-   IndexColumns  
  
-   절차  
  
-   시퀀스  
  
-   동의어  
  
-   Tables  
  
-   Users  
  
-   뷰  
  
-   함수  
  
-   패키지  
  
-   PackageBodies  
  
-   인수  
  
-   UniqueKeys  
  
-   PrimaryKeys  
  
-   ForeignKeys  
  
-   ForeignKeyColumns  
  
-   ProcedureParameters  
  
## Columns  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|OWNER|문자열|테이블, 뷰 또는 클러스터의 소유자입니다.|  
|TABLE\_NAME|문자열|테이블, 뷰 또는 클러스터 이름입니다.|  
|COLUMN\_NAME|문자열|열 이름입니다.|  
|ID|Decimal|만들어진 열의 시퀀스 번호입니다.|  
|DATATYPE|문자열|열의 데이터 형식입니다.|  
|LENGTH|Decimal|열 길이\(바이트\)입니다.|  
|PRECISION|Decimal|NUMBER 데이터 형식인 경우는 십진수 정밀도이고 FLOAT 데이터 형식인 경우는 이진 정밀도이며 다른 모든 데이터 형식인 경우는 null입니다.|  
|SCALE|Decimal|소수점 오른쪽의 숫자 자릿수입니다.|  
|NULLABLE|문자열|열에서 NULL을 허용하는지 여부를 지정합니다.  열에 NOT NULL 제약 조건이 없거나 열이 PRIMARY KEY의 일부인 경우 값은 N입니다.|  
  
## Indexes  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|OWNER|문자열|인덱스의 소유자입니다.|  
|INDEX\_NAME|문자열|인덱스의 이름입니다.|  
|INDEX\_TYPE|문자열|인덱스의 형식입니다\(NORMAL, BITMAP, FUNCTION\-BASED NORMAL, FUNCTION\-BASED BITMAP 또는 DOMAIN\).|  
|TABLE\_OWNER|문자열|인덱싱된 개체의 소유자입니다.|  
|TABLE\_NAME|문자열|인덱싱된 개체의 이름입니다.|  
|TABLE\_TYPE|문자열|인덱싱된 개체의 형식입니다\(예: TABLE, CLUSTER\).|  
|UNIQUENESS|문자열|인덱스가 UNIQUE인지 또는 NONUNIQUE인지 여부입니다.|  
|COMPRESSION|문자열|인덱스가 ENABLED인지 또는 DISABLED인지 여부입니다.|  
|PREFIX\_LENGTH|Decimal|압축 키 접두사의 열 수입니다.|  
|TABLESPACE\_NAME|문자열|인덱스를 포함하는 테이블스페이스 이름입니다.|  
|INI\_TRANS|Decimal|초기 트랜잭션 수입니다.|  
|MAX\_TRANS|Decimal|최대 트랜잭션 수입니다.|  
|INITIAL\_EXTENT|Decimal|초기 익스텐트 크기입니다.|  
|NEXT\_EXTENT|Decimal|보조 익스텐트 크기입니다.|  
|MIN\_EXTENTS|Decimal|세그먼트에 허용된 최소 익스텐트 수입니다.|  
|MAX\_EXTENTS|Decimal|세그먼트에 허용된 최대 익스텐트 수입니다.|  
|PCT\_INCREASE|Decimal|익스텐트 크기의 증가율입니다.|  
|PCT\_THRESHOLD|Decimal|인덱스 엔트리당 허용된 블록 공간의 임계값 백분율입니다.|  
|INCLUDE\_COLUMN|Decimal|인덱스 구성 테이블 기본 키\(비 오버플로\) 인덱스에 마지막으로 포함될 열의 열 ID입니다.  이 열은 \*\_TAB\_COLUMNS 데이터 사전 뷰의 COLUMN\_ID 열에 매핑됩니다.|  
|FREELISTS|Decimal|이 세그먼트에 할당된 프로세스 freelist 수입니다.|  
|FREELIST\_GROUPS|Decimal|이 세그먼트에 할당된 freelist 그룹 수입니다.|  
|PCT\_FREE|Decimal|블록의 최소 여유 공간 비율입니다.|  
|LOGGING|문자열|로깅 정보입니다.|  
|BLEVEL|Decimal|B\*\-트리 수준: 루트 블록에서 리프 블록까지의 인덱스 깊이입니다.  깊이가 0이면 루트 블록과 리프 블록이 같음을 나타냅니다.|  
|LEAF\_BLOCKS|Decimal|인덱스의 리프 블록 수입니다.|  
|DISTINCT\_KEYS|Decimal|인덱싱된 고유한 값의 수입니다.  UNIQUE 및 PRIMARY KEY 제약 조건이 적용되는 인덱스의 경우 이 값은 테이블의 행 수와 같습니다\(USER\_TABLES.NUM\_ROWS\).|  
|AVG\_LEAF\_BLOCKS\_PER\_KEY|Decimal|각각의 고유한 값이 가장 가까운 정수로 올림되어 나타나는 리프 블록의 평균 개수입니다.  UNIQUE 및 PRIMARY KEY 제약 조건을 적용하는 인덱스의 경우 이 값은 항상 1입니다.|  
|AVG\_DATA\_BLOCKS\_PER\_KEY|Decimal|인덱스의 고유한 값이 가장 가까운 정수로 올림되도록 나타내는 테이블의 평균 데이터 블록 수입니다.  이 통계는 인덱싱된 열에 대해 지정된 값이 들어 있는 행을 포함하는 데이터 블록의 평균 개수입니다.|  
|CLUSTERING\_FACTOR|Decimal|인덱스 값에 따른 테이블의 행 주문량을 나타냅니다.|  
|STATUS|문자열|파티션되지 않은 인덱스가 VALID인지 또는 UNUSABLE인지 여부입니다.|  
|NUM\_ROWS|Decimal|인덱스의 행 수입니다.|  
|SAMPLE\_SIZE|Decimal|인덱스 분석에 사용할 샘플의 크기입니다.|  
|LAST\_ANALYZED|DateTime|이 인덱스를 가장 최근에 분석한 날짜입니다.|  
|DEGREE|문자열|인덱스를 스캔할 인스턴스당 스레드 수입니다.|  
|INSTANCES|문자열|인덱스를 스캔할 인스턴스의 수입니다.|  
|PARTITIONED|문자열|인덱스가 구분되었는지 여부입니다\(YES &#124; NO\).|  
|TEMPORARY|문자열|인덱스가 임시 테이블에 있는지 여부입니다.|  
|GENERATED|문자열|인덱스 이름이 시스템에서 생성되었는지 여부입니다\(Y&#124;N\).|  
|SECONDARY|문자열|인덱스가 Oracle9i 데이터 카트리지의 ODCIIndexCreate 메서드에서 만든 보조 개체인지 여부입니다\(Y&#124;N\).|  
|BUFFER\_POOL|문자열|인덱스 블록에 사용할 기본 버퍼 풀의 이름입니다.|  
|USER\_STATS|문자열|사용자가 직접 통계를 입력했는지 여부입니다.|  
|DURATION|문자열|임시 테이블의 지속 시간을 나타냅니다. 1\)SYS$SESSION: 세션 지속 시간 동안 행이 유지됩니다. 2\) SYS$TRANSACTION: COMMIT 이후에 행이 삭제됩니다. 3\) 영구 테이블인 경우 Null입니다.|  
|PCT\_DIRECT\_ACCESS|Decimal|인덱스 구성 테이블의 보조 인덱스인 경우 VALID 추측을 사용한 행의 백분율입니다.|  
|ITYP\_OWNER|문자열|도메인 인덱스인 경우 인덱스 형식 소유자입니다.|  
|ITYP\_NAME|문자열|도메인 인덱스인 경우 인덱스 형식 이름입니다.|  
|PARAMETERS|문자열|도메인 인덱스인 경우 매개 변수 문자열입니다.|  
|GLOBAL\_STATS|문자열|구분된 인덱스인 경우 통계를 인덱스를 전체적으로 분석하여 수집했는지\(YES\) 또는 기본 인덱스 파티션 및 하위 파티션의 통계에서 추측했는지\(NO\) 여부를 나타냅니다.|  
|DOMIDX\_STATUS|문자열|도메인 인덱스의 상태를 나타냅니다.  NULL: 지정한 인덱스는 도메인 인덱스가 아닙니다.  VALID: 올바른 도메인 인덱스입니다.  IDXTYP\_INVLD: 이 도메인 인덱스의 인덱스 형식이 올바르지 않습니다.|  
|DOMIDX\_OPSTATUS|문자열|도메인 인덱스에서 수행한 작업의 상태를 나타냅니다. NULL: 지정한 인덱스는 도메인 인덱스가 아닙니다.  VALID: 작업이 오류 없이 수행되었습니다.  FAILED: 오류가 발생하여 작업을 수행하지 못했습니다.|  
|FUNCIDX\_STATUS|문자열|함수 기반 인덱스의 상태를 나타냅니다. NULL: 함수 기반 인덱스가 아닙니다. ENABLED: 함수 기반 인덱스가 활성화되었습니다. DISABLED: 함수 기반 인덱스가 비활성화되었습니다.|  
|JOIN\_INDEX|문자열|조인 인덱스인지 여부를 나타냅니다.|  
  
## IndexColumns  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|INDEX\_OWNER|문자열|인덱스의 소유자입니다.|  
|INDEX\_NAME|문자열|인덱스의 이름입니다.|  
|TABLE\_OWNER|문자열|테이블 또는 클러스터의 소유자입니다.|  
|TABLE\_NAME|문자열|테이블 또는 클러스터의 이름입니다.|  
|COLUMN\_NAME|문자열|개체 유형 열의 열 이름 또는 특성입니다.|  
|COLUMN\_POSITION|Decimal|인덱스 내의 열 또는 특성 위치입니다.|  
|COLUMN\_LENGTH|Decimal|열의 인덱싱된 길이입니다.|  
|CHAR\_LENGTH|Decimal|열의 최대 코드 포인트 길이입니다.|  
|DESCEND|문자열|열이 내림차순으로 정렬되어 있는지 여부입니다.|  
  
## 절차  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|OWNER|문자열|개체의 소유자입니다.|  
|OBJECT\_NAME|문자열|개체의 이름입니다.|  
|SUBOBJECT\_NAME|문자열|하위 개체\(예: 파티션\)의 이름입니다.|  
|OBJECT\_ID|Decimal|개체의 사전순 개체 번호입니다.|  
|DATA\_OBJECT\_ID|Decimal|개체를 포함하는 세그먼트의 사전순 개체 번호입니다.|  
|LAST\_DDL\_TIME|DateTime|부여 및 해지 등의 DDL 명령으로 인한 개체의 최종 수정에 대한 타임스탬프입니다.|  
|TIMESTAMP|문자열|개체\(문자 데이터\)의 사양에 대한 타임스탬프입니다.|  
|STATUS|문자열|개체의 상태\(VALID, INVALID 또는 N\/A\)입니다.|  
|TEMPORARY|문자열|임시 개체인지 여부입니다. 임시 개체일 경우 현재 세션은 이 개체 내에 위치하는 데이터만 볼 수 있습니다.|  
|GENERATED|문자열|이 개체 시스템의 이름이 생성되었습니까?  \(Y &#124; N\).|  
|SECONDARY|문자열|Oracle9i 데이터 카트리지의 ODCIIndexCreate 메서드에서 만든 보조 개체인지 여부입니다\(Y &#124; N\).|  
|CREATED|DateTime|개체가 만들어진 날짜입니다.|  
  
## 시퀀스  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|SEQUENCE\_OWNER|문자열|시퀀스 소유자의 이름입니다.|  
|SEQUENCE\_NAME|문자열|시퀀스 이름입니다.|  
|MIN\_VALUE|Decimal|시퀀스의 최소값입니다.|  
|MAX\_VALUE|Decimal|시퀀스의 최대값입니다.|  
|INCREMENT\_BY|Decimal|시퀀스가 증가하는 값입니다.|  
|CYCLE\_FLAG|문자열|제한에 도달하면 시퀀스가 래핑을 수행합니까?|  
|ORDER\_FLAG|문자열|시퀀스 번호가 순서대로 생성되었습니까?|  
|CACHE\_SIZE|Decimal|캐시할 시퀀스 번호의 개수입니다.|  
|LAST\_NUMBER|Decimal|디스크에 기록할 마지막 시퀀스 번호입니다.  시퀀스에서 캐싱을 사용하는 경우 디스크에 기록된 번호는 시퀀스 캐시에 마지막으로 들어갈 번호입니다.  이 번호는 마지막으로 사용한 시퀀스 번호보다 클 수 있습니다.|  
  
## 동의어  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|OWNER|문자열|동의어의 소유자입니다.|  
|SYNONYM\_NAME|문자열|동의어의 이름입니다.|  
|TABLE\_OWNER|문자열|동의어로 참조한 개체의 소유자입니다.|  
|TABLE\_NAME|문자열|동의어로 참조한 개체의 이름입니다.|  
|DB\_LINK|문자열|참조된 데이터베이스 링크 이름입니다\(있는 경우\).|  
  
## Tables  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|OWNER|문자열|테이블의 소유자입니다.|  
|TABLE\_NAME|문자열|테이블의 이름입니다.|  
|TYPE|문자열|테이블 형식입니다.|  
  
## Users  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|NAME|문자열|사용자 이름입니다.|  
|ID|Decimal|사용자의 ID 번호입니다.|  
|CREATEDATE|DateTime|사용자가 만든 날짜입니다.|  
  
## 뷰  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|OWNER|문자열|뷰의 소유자입니다.|  
|VIEW\_NAME|문자열|뷰의 이름입니다.|  
|TEXT\_LENGTH|Decimal|뷰 텍스트의 길이입니다.|  
|TEXT|문자열|뷰 텍스트입니다.|  
|TYPE\_TEXT\_LENGTH|Decimal|형식화된 뷰의 type 절 길이입니다.|  
|TYPE\_TEXT|문자열|형식화된 뷰의 type 절입니다.|  
|OID\_TEXT\_LENGTH|Decimal|형식화된 뷰의 WITH OID 절 길이입니다.|  
|OID\_TEXT|문자열|형식화된 뷰의 WITH OID 절입니다.|  
|VIEW\_TYPE\_OWNER|문자열|뷰가 형식화된 뷰인 경우 뷰 형식의 소유자입니다.|  
|VIEW\_TYPE|문자열|뷰가 형식화된 뷰인 경우 뷰 형식입니다.|  
|SUPERVIEW\_NAME|문자열|슈퍼 뷰의 이름입니다.|  
  
## 함수  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|OWNER|문자열|개체의 소유자입니다.|  
|OBJECT\_NAME|문자열|개체의 이름입니다.|  
|SUBOBJECT\_NAME|문자열|하위 개체\(예: 파티션\)의 이름입니다.|  
|OBJECT\_ID|Decimal|개체의 사전순 개체 번호입니다.|  
|DATA\_OBJECT\_ID|Decimal|개체를 포함하는 세그먼트의 사전순 개체 번호입니다.|  
|OBJECT\_TYPE|문자열|개체의 형식입니다.|  
|CREATED|DateTime|개체가 만들어진 날짜입니다.|  
|LAST\_DDL\_TIME|DateTime|부여 및 해지 등의 DDL 명령으로 인한 개체의 최종 수정에 대한 타임스탬프입니다.|  
|TIMESTAMP|문자열|개체\(문자 데이터\)의 사양에 대한 타임스탬프입니다.|  
|STATUS|문자열|개체의 상태\(VALID, INVALID 또는 N\/A\)입니다.|  
|TEMPORARY|문자열|임시 개체인지 여부입니다. 임시 개체일 경우 현재 세션은 이 개체 내에 위치하는 데이터만 볼 수 있습니다.|  
|GENERATED|문자열|이 개체 시스템의 이름이 생성되었습니까?  \(Y &#124; N\).|  
|SECONDARY|문자열|Oracle9i 데이터 카트리지의 ODCIIndexCreate 메서드에서 만든 보조 개체인지 여부입니다\(Y &#124; N\).|  
  
## 패키지  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|OWNER|문자열|개체의 소유자입니다.|  
|OBJECT\_NAME|문자열|개체의 이름입니다.|  
|SUBOBJECT\_NAME|문자열|하위 개체\(예: 파티션\)의 이름입니다.|  
|OBJECT\_ID|Decimal|개체의 사전순 개체 번호입니다.|  
|DATA\_OBJECT\_ID|Decimal|개체를 포함하는 세그먼트의 사전순 개체 번호입니다.|  
|LAST\_DDL\_TIME|DateTime|부여 및 해지 등의 DDL 명령으로 인한 개체의 최종 수정에 대한 타임스탬프입니다.|  
|TIMESTAMP|문자열|개체\(문자 데이터\)의 사양에 대한 타임스탬프입니다.|  
|STATUS|문자열|개체의 상태\(VALID, INVALID 또는 N\/A\)입니다.|  
|TEMPORARY|문자열|임시 개체인지 여부입니다. 임시 개체일 경우 현재 세션은 이 개체 내에 위치하는 데이터만 볼 수 있습니다.|  
|GENERATED|문자열|이 개체 시스템의 이름이 생성되었습니까?  \(Y &#124; N\).|  
|SECONDARY|문자열|Oracle9i 데이터 카트리지의 ODCIIndexCreate 메서드에서 만든 보조 개체인지 여부입니다\(Y &#124; N\).|  
|CREATED|DateTime|개체가 만들어진 날짜입니다.|  
  
## PackageBodies  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|OWNER|문자열|개체의 소유자입니다.|  
|OBJECT\_NAME|문자열|개체의 이름입니다.|  
|SUBOBJECT\_NAME|문자열|하위 개체\(예: 파티션\)의 이름입니다.|  
|OBJECT\_ID|Decimal|개체의 사전순 개체 번호입니다.|  
|DATA\_OBJECT\_ID|Decimal|개체를 포함하는 세그먼트의 사전순 개체 번호입니다.|  
|LAST\_DDL\_TIME|DateTime|부여 및 해지 등의 DDL 명령으로 인한 개체의 최종 수정에 대한 타임스탬프입니다.|  
|TIMESTAMP|문자열|개체\(문자 데이터\)의 사양에 대한 타임스탬프입니다.|  
|STATUS|문자열|개체의 상태\(VALID, INVALID 또는 N\/A\)입니다.|  
|TEMPORARY|문자열|임시 개체인지 여부입니다. 임시 개체일 경우 현재 세션은 이 개체 내에 위치하는 데이터만 볼 수 있습니다.|  
|GENERATED|문자열|이 개체 시스템의 이름이 생성되었습니까?  \(Y &#124; N\).|  
|SECONDARY|문자열|Oracle9i 데이터 카트리지의 ODCIIndexCreate 메서드에서 만든 보조 개체인지 여부입니다\(Y &#124; N\).|  
|CREATED|DateTime|개체가 만들어진 날짜입니다.|  
  
## 인수  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|OWNER|문자열|개체 소유자의 이름입니다.|  
|PACKAGE\_NAME|문자열|패키지 이름입니다.|  
|OBJECT\_NAME|문자열|프로시저 또는 함수의 이름입니다.|  
|ARGUMENT\_NAME|문자열|인수의 이름입니다.|  
|POSITION|Decimal|인수 목록의 위치이거나 함수 반환 값인 경우 NULL입니다.|  
|SEQUENCE|Decimal|모든 중첩 수준을 포함하는 인수 시퀀스입니다.|  
|DEFAULT\_VALUE|문자열|인수의 기본값입니다.|  
|DEFAULT\_LENGTH|Decimal|인수의 기본값 길이입니다.|  
|IN\_OUT|문자열|인수의 방향입니다\(IN, OUT 또는 IN\/OUT\).|  
|DATA\_LENGTH|Decimal|열 길이\(바이트\)입니다.|  
|DATA\_PRECISION|Decimal|십진수\(NUMBER\) 또는 이진수\(FLOAT\)의 길이입니다.|  
|DATA\_SCALE|Decimal|소수점 오른쪽의 숫자 자릿수입니다.|  
|DATA\_TYPE|문자열|인수의 데이터 형식입니다.|  
  
## UniqueKeys  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|OWNER|문자열|제약 조건 정의의 소유자입니다.|  
|CONSTRAINT\_NAME|문자열|제약 조건 정의의 이름입니다.|  
|TABLE\_NAME|문자열|제약 조건 정의가 포함된 테이블\(또는 뷰\)과 연결된 이름입니다.|  
|SEARCH\_CONDITION|문자열|CHECK 제약 조건에 대한 검색 조건의 텍스트입니다.|  
|R\_OWNER|문자열|참조 제약 조건에서 참조된 테이블의 소유자입니다.|  
|R\_CONSTRAINT\_NAME|문자열|참조된 테이블에 대한 UNIQUE 제약 조건 정의의 이름입니다.|  
|DELETE\_RULE|문자열|참조 제약 조건에 대한 규칙\(CASCADE 또는 NO ACTION\)을 삭제합니다.|  
|STATUS|문자열|제약 조건의 상태\(ENABLED 또는 DISABLED\)를 적용합니다.|  
|DEFERRABLE|문자열|제약 조건의 지연 가능 여부입니다.|  
|VALIDATED|문자열|모든 데이터가 제약 조건\(VALIDATED 또는 NOT VALIDATED\)을 따르는지 여부입니다.|  
|GENERATED|문자열|제약 조건의 이름이 사용자인지 또는 시스템 생성인지 여부입니다.|  
|BAD|문자열|YES 값은 이 제약 조건의 세기 지정 방식이 모호함을 나타냅니다.  이 모호성으로 인한 오류가 발생하지 않도록 하려면 TO\_DATE 네 자릿수 연도와 함께 사용하여 제약 조건을 다시 작성합니다.|  
|RELY|문자열|활성화된 제약 조건이 적용되는지 또는 적용되지 않는지 여부입니다.|  
|LAST\_CHANGE|DateTime|제약 조건이 마지막으로 활성화되거나 비활성화된 시간입니다.|  
|INDEX\_OWNER|문자열|인덱스를 소유하는 사용자의 이름입니다.|  
|INDEX\_NAME|문자열|인덱스의 이름입니다.|  
  
## PrimaryKeys  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|OWNER|문자열|제약 조건 정의의 소유자입니다.|  
|CONSTRAINT\_NAME|문자열|제약 조건 정의의 이름입니다.|  
|TABLE\_NAME|문자열|제약 조건 정의가 포함된 테이블\(또는 뷰\)과 연결된 이름입니다.|  
|SEARCH\_CONDITION|문자열|CHECK 제약 조건에 대한 검색 조건의 텍스트입니다.|  
|R\_OWNER|문자열|참조 제약 조건에서 참조된 테이블의 소유자입니다.|  
|R\_CONSTRAINT\_NAME|문자열|참조된 테이블에 대한 UNIQUE 제약 조건 정의의 이름입니다.|  
|DELETE\_RULE|문자열|참조 제약 조건에 대한 규칙\(CASCADE 또는 NO ACTION\)을 삭제합니다.|  
|STATUS|문자열|제약 조건의 상태\(ENABLED 또는 DISABLED\)를 적용합니다.|  
|DEFERRABLE|문자열|제약 조건의 지연 가능 여부입니다.|  
|VALIDATED|문자열|모든 데이터가 제약 조건\(VALIDATED 또는 NOT VALIDATED\)을 따르는지 여부입니다.|  
|GENERATED|문자열|제약 조건의 이름이 사용자인지 또는 시스템 생성인지 여부입니다.|  
|BAD|문자열|YES 값은 이 제약 조건의 세기 지정 방식이 모호함을 나타냅니다.  이 모호성으로 인한 오류가 발생하지 않도록 하려면 TO\_DATE 네 자릿수 연도와 함께 사용하여 제약 조건을 다시 작성합니다.|  
|RELY|문자열|활성화된 제약 조건이 적용되는지 또는 적용되지 않는지 여부입니다.|  
|LAST\_CHANGE|DateTime|제약 조건이 마지막으로 활성화되거나 비활성화된 시간입니다.|  
|INDEX\_OWNER|문자열|인덱스를 소유하는 사용자의 이름입니다.|  
|INDEX\_NAME|문자열|인덱스의 이름입니다.|  
  
## ForeignKeys  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|PRIMARY\_KEY\_CONSTRAINT\_NAME|문자열|제약 조건 정의의 이름입니다.|  
|PRIMARY\_KEY\_OWNER|문자열|제약 조건 정의의 소유자입니다.|  
|PRIMARY\_KEY\_TABLE\_NAME|문자열|제약 조건 정의가 포함된 테이블\(또는 뷰\)과 연결된 이름입니다.|  
|FOREIGN\_KEY\_OWNER|문자열|제약 조건 정의의 소유자입니다.|  
|FOREIGN\_KEY\_CONSTRIANT\_NAME|문자열|제약 조건 정의의 이름입니다.|  
|FOREIGN\_KEY\_TABLE\_NAME|문자열|제약 조건 정의가 포함된 테이블\(또는 뷰\)과 연결된 이름입니다.|  
|SEARCH\_CONDITION|문자열|CHECK 제약 조건에 대한 검색 조건의 텍스트입니다.|  
|R\_OWNER|문자열|참조 제약 조건에서 참조된 테이블의 소유자입니다.|  
|R\_CONSTRAINT\_NAME|문자열|참조된 테이블에 대한 UNIQUE 제약 조건 정의의 이름입니다.|  
|DELETE\_RULE|문자열|참조 제약 조건에 대한 규칙\(CASCADE 또는 NO ACTION\)을 삭제합니다.|  
|STATUS|문자열|제약 조건의 상태\(ENABLED 또는 DISABLED\)를 적용합니다.|  
|VALIDATED|문자열|모든 데이터가 제약 조건\(VALIDATED 또는 NOT VALIDATED\)을 따르는지 여부입니다.|  
|GENERATED|문자열|제약 조건의 이름이 사용자인지 또는 시스템 생성인지 여부입니다.|  
|RELY|문자열|활성화된 제약 조건이 적용되는지 또는 적용되지 않는지 여부입니다.|  
|LAST\_CHANGE|DateTime|제약 조건이 마지막으로 활성화되거나 비활성화된 시간입니다.|  
|INDEX\_OWNER|문자열|인덱스를 소유하는 사용자의 이름입니다.|  
|INDEX\_NAME|문자열|인덱스의 이름입니다.|  
  
## ForeignKeyColumns  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|OWNER|문자열|제약 조건 정의의 소유자입니다.|  
|CONSTRAINT\_NAME|문자열|제약 조건 정의의 이름입니다.|  
|TABLE\_NAME|문자열|제약 조건 정의가 들어 있는 테이블 이름입니다.|  
|COLUMN\_NAME|문자열|제약 조건 정의에 지정된 개체 유형 열의 열 또는 특성 이름입니다.|  
|POSITION|Decimal|개체 정의에서 열 또는 특성의 원래 위치입니다.|  
  
## ProcedureParameters  
  
|열 이름|데이터 형식|설명|  
|----------|------------|--------|  
|OWNER|문자열|개체의 소유자입니다.|  
|OBJECT\_NAME|문자열|프로시저 또는 함수의 이름입니다.|  
|PACKAGE\_NAME|문자열|프로시저 또는 함수의 이름입니다.|  
|OBJECT\_ID|Decimal|개체의 개체 번호입니다.|  
|OVERLOAD|문자열|고유 식별자를 오버로드합니다.|  
|ARGUMENT\_NAME|문자열|인수의 이름입니다.|  
|POSITION|Decimal|인수 목록의 위치이거나 함수 반환 값인 경우 null입니다.|  
|SEQUENCE|Decimal|모든 중첩 수준을 포함하는 인수 시퀀스입니다.|  
|DATA\_LEVEL|Decimal|복합 형식에 대한 인수의 중첩 한도입니다.|  
|DATA\_TYPE|문자열|인수의 데이터 형식입니다.|  
|DEFAULT\_VALUE|문자열|인수의 기본값입니다.|  
|DEFAULT\_LENGTH|Decimal|인수의 기본값 길이입니다.|  
|IN\_OUT|문자열|인수의 방향입니다\(IN, OUT 또는 IN\/OUT\).|  
|DATA\_LENGTH|Decimal|열 길이\(바이트\)입니다.|  
|DATA\_PRECISION|Decimal|십진수\(NUMBER\) 또는 이진수\(FLOAT\)의 길이입니다.|  
|DATA\_SCALE|Decimal|소수점 오른쪽의 숫자 자릿수입니다.|  
|RADIX|Decimal|숫자의 인수 기수입니다.|  
|CHARACTER\_SET\_NAME|문자열|인수의 문자 집합 이름입니다.|  
|TYPE\_OWNER|문자열|인수 형식의 소유자입니다.|  
|TYPE\_NAME|문자열|인수 형식의 이름입니다.  형식이 패키지 사양에서 선언되는 패키지 로컬 형식인 경우 이 열에는 패키지의 이름이 표시됩니다.|  
|TYPE\_SUBNAME|문자열|패키지 로컬 형식에 대해서만 관련이 있습니다.  TYPE\_NAME 열에서 식별되는 패키지에 선언된 형식의 이름이 표시됩니다.|  
|TYPE\_LINK|문자열|TYPE\_NAME 열에서 식별된 패키지가 원격 패키지인 경우의 패키지 로컬 형식에 대해서만 관련이 있습니다.  이 열에는 원격 패키지를 참조하는 데 사용되는 데이터베이스 링크가 표시됩니다.|  
|PLS\_TYPE|문자열|숫자 인수인 경우 PL\/SQL 형식의 인수 이름입니다.  그렇지 않으면 Null입니다.|  
|CHAR\_LENGTH|Decimal|문자열 데이터 형식의 문자 제한입니다.|  
|CHAR\_USED|문자열|문자열에 공식적으로 사용되는 것이 바이트 제한\(B\)인지 또는 문자열 제한\(C\)인지 여부를 나타냅니다.|  
  
## 참고 항목  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)