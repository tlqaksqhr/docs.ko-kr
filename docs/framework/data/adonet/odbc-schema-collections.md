---
title: "ODBC 스키마 컬렉션 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# ODBC 스키마 컬렉션
이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 ODBC 드라이버에서 지원하는 스키마 컬렉션에 대해 설명합니다.  
  
## Microsoft SQL Server ODBC Driver  
 Microsoft SQL Server ODBC Driver에서는 공통 스키마 컬렉션을 비롯하여 다음과 같은 특정 스키마 컬렉션을 지원합니다.  
  
-   Tables  
  
-   Indexes  
  
-   Columns  
  
-   절차  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   뷰  
  
### Tables 및 Views  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_CAT|문자열|  
|TABLE\_SCHEM|문자열|  
|TABLE\_NAME|문자열|  
|TABLE\_TYPE|문자열|  
|REMARKS|문자열|  
  
### Indexes  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_CAT|문자열|  
|TABLE\_SCHEM|문자열|  
|TABLE\_NAME|문자열|  
|NON\_UNIQUE|Int16|  
|INDEX\_QUALIFIER|문자열|  
|INDEX\_NAME|문자열|  
|TYPE|Int16|  
|ORDINAL\_POSITION|Int16|  
|COLUMN\_NAME|문자열|  
|ASC\_OR\_DESC|문자열|  
|CARDINATLITY|Int32|  
|PAGES|Int32|  
|FILTER\_CONDITION|문자열|  
|SS\_TYPE\_SCHEMA|문자열|  
|SS\_DATA\_TYPE|Byte|  
  
### Columns  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_CAT|문자열|  
|TABLE\_SCHEM|문자열|  
|TABLE\_NAME|문자열|  
|COLUMN\_NAME|문자열|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|문자열|  
|COLUMN\_SIZE|Int32|  
|BUFFER\_LENGTH|Int32|  
|DECIMAL\_DIGITS|Int16|  
|NUM\_PREC\_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|문자열|  
|COLUMN\_DEF|문자열|  
|SQL\_DATA\_TYPE|Int16|  
|SQL\_DATETIME\_SUB|Int16|  
|CHAR\_OCTET\_LENGTH|Int32|  
|ORDINAL\_POSITION|Int32|  
|IS\_NULLABLE|문자열|  
|SS\_TYPE\_CATALOG|문자열|  
|SS\_TYPE\_SCHEMA|문자열|  
|SS\_DATA\_TYPE|Byte|  
  
### 절차  
  
|열 이름|데이터 형식|  
|----------|------------|  
|PROCEDURE\_CAT|문자열|  
|PROCEDURE\_SCHEM|문자열|  
|PROCEDURE\_NAME|문자열|  
|NUM\_INPUT\_PARAMS|Int32|  
|NUM\_OUTPUT\_PARAMS|Int32|  
|NUM\_RESULT\_SETS|Int32|  
|REMARKS|문자열|  
|PROCEDURE\_TYPE|Int16|  
  
### ProcedureColumns  
  
|열 이름|데이터 형식|  
|----------|------------|  
|PROCEDURE\_CAT|문자열|  
|PROCEDURE\_SCHEM|문자열|  
|PROCEDURE\_NAME|문자열|  
|COLUMN\_NAME|문자열|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|문자열|  
|COLUMN\_SIZE|Int32|  
|BUFFER\_LENGTH|Int32|  
|DECIMAL\_DIGITS|Int16|  
|NUM\_PREC\_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|문자열|  
|COLUMN\_DEF|문자열|  
|SQL\_DATA\_TYPE|Int16|  
|SQL\_DATETIME\_SUB|Int16|  
|CHAR\_OCTET\_LENGTH|Int32|  
|ORDINAL\_POSITION|Int32|  
|IS\_NULLABLE|문자열|  
|SS\_TYPE\_CATALOG|문자열|  
|SS\_TYPE\_SCHEMA|문자열|  
|SS\_DATA\_TYPE|Byte|  
  
### ProcedureParameters  
  
|열 이름|데이터 형식|  
|----------|------------|  
|PROCEDURE\_CAT|문자열|  
|PROCEDURE\_SCHEM|문자열|  
|PROCEDURE\_NAME|문자열|  
|COLUMN\_NAME|문자열|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|문자열|  
|COLUMN\_SIZE|Int32|  
|BUFFER\_LENGTH|Int32|  
|DECIMAL\_DIGITS|Int16|  
|NUM\_PREC\_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|문자열|  
|COLUMN\_DEF|문자열|  
|SQL\_DATA\_TYPE|Int16|  
|SQL\_DATETIME\_SUB|Int16|  
|CHAR\_OCTET\_LENGTH|Int32|  
|ORDINAL\_POSITION|Int32|  
|IS\_NULLABLE|문자열|  
|SS\_TYPE\_CATALOG|문자열|  
|SS\_TYPE\_SCHEMA|문자열|  
|SS\_DATA\_TYPE|Byte|  
  
## Microsoft Oracle ODBC Driver  
 Microsoft SQL Server Oracle ODBC Driver에서는 공통 스키마 컬렉션을 비롯하여 다음과 같은 특정 스키마 컬렉션을 지원합니다.  
  
-   Tables  
  
-   Columns  
  
-   절차  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   뷰  
  
-   Indexes  
  
### Tables 및 Views  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_QUALIFIER|문자열|  
|TABLE\_OWNER|문자열|  
|TABLE\_NAME|문자열|  
|TABLE\_TYPE|문자열|  
|REMARKS|문자열|  
  
### Columns  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_QUALIFIER|문자열|  
|TABLE\_OWNER|문자열|  
|TABLE\_NAME|문자열|  
|COLUMN\_NAME|문자열|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|문자열|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|문자열|  
|ORDINAL\_POSITION|Int32|  
  
### 절차  
  
|열 이름|데이터 형식|  
|----------|------------|  
|PROCEDURE\_QUALIFIER|문자열|  
|PROCEDURE\_OWNER|문자열|  
|PROCEDURE\_NAME|문자열|  
|NUM\_INPUT\_PARAMS|Int16|  
|NUM\_OUTPUT\_PARAMS|Int16|  
|NUM\_RESULT\_SETS|Int16|  
|REMARKS|문자열|  
|PROCEDURE\_TYPE|Int16|  
  
### ProcedureColumns  
  
|열 이름|데이터 형식|  
|----------|------------|  
|PROCEDURE\_QUALIFIER|문자열|  
|PROCEDURE\_OWNER|문자열|  
|PROCEDURE\_NAME|문자열|  
|COLUMN\_NAME|문자열|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|문자열|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|문자열|  
|OVERLOAD|Int32|  
|ORDINAL\_POSITION|Int32|  
  
## Microsoft Jet ODBC Driver  
 Microsoft Jet ODBC Driver                                             .  
  
-   Tables  
  
-   Indexes  
  
-   Columns  
  
-   절차  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   뷰  
  
### Tables 및 Views  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_QUALIFIER|문자열|  
|TABLE\_OWNER|문자열|  
|TABLE\_NAME|문자열|  
|TABLE\_TYPE|문자열|  
|REMARKS|문자열|  
  
### Columns  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_QUALIFIER|문자열|  
|TABLE\_OWNER|문자열|  
|TABLE\_NAME|문자열|  
|COLUMN\_NAME|문자열|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|문자열|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|문자열|  
|ORDINAL\_POSITION|Int32|  
  
### 절차  
  
|열 이름|데이터 형식|  
|----------|------------|  
|PROCEDURE\_QUALIFIER|문자열|  
|PROCEDURE\_OWNER|문자열|  
|PROCEDURE\_NAME|문자열|  
|NUM\_INPUT\_PARAMS|Int16|  
|NUM\_OUTPUT\_PARAMS|Int16|  
|NUM\_RESULT\_SETS|Int16|  
|REMARKS|문자열|  
|PROCEDURE\_TYPE|Int16|  
  
### ProcedureColumns  
  
|열 이름|데이터 형식|  
|----------|------------|  
|PROCEDURE\_QUALIFIER|문자열|  
|PROCEDURE\_OWNER|문자열|  
|PROCEDURE\_NAME|문자열|  
|COLUMN\_NAME|문자열|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|문자열|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|문자열|  
|OVERLOAD|Int32|  
|ORDINAL\_POSITION|Int32|  
  
### ProcedureParameters  
  
|열 이름|데이터 형식|  
|----------|------------|  
|PROCEDURE\_CAT|문자열|  
|PROCEDURE\_SCHEM|문자열|  
|PROCEDURE\_NAME|문자열|  
|COLUMN\_NAME|문자열|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|문자열|  
|COLUMN\_SIZE|Int32|  
|BUFFER\_LENGTH|Int32|  
|DECIMAL\_DIGITS|Int16|  
|NUM\_PREC\_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|문자열|  
|COLUMN\_DEF|문자열|  
|SQL\_DATA\_TYPE|Int16|  
|SQL\_DATETIME\_SUB|Int16|  
|CHAR\_OCTET\_LENGTH|Int32|  
|ORDINAL\_POSITION|Int32|  
|IS\_NULLABLE|문자열|  
  
## 참고 항목  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)