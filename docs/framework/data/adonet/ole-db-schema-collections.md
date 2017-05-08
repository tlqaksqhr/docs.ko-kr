---
title: "OLE DB 스키마 컬렉션 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# OLE DB 스키마 컬렉션
이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 OLE DB 공급자에서 지원하는 스키마 컬렉션에 대해 설명합니다.  
  
## Microsoft SQL Server OLE DB 공급자  
 Microsoft SQL Server OLE DB Driver에서는 공통 스키마 컬렉션을 비롯하여 다음과 같은 특정 스키마 컬렉션을 지원합니다.  
  
-   Tables  
  
-   Columns  
  
-   절차  
  
-   ProcedureParameters  
  
-   Catalog  
  
-   Indexes  
  
### Tables  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_CATALOG|문자열|  
|TABLE\_SCHEMA|문자열|  
|TABLE\_NAME|문자열|  
|TABLE\_TYPE|문자열|  
|TABLE\_GUID|Guid|  
|DESCRIPTION|문자열|  
|TABLE\_PROPID|Int64|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Columns  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_CATALOG|문자열|  
|TABLE\_SCHEMA|문자열|  
|TABLE\_NAME|문자열|  
|COLUMN\_NAME|문자열|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_HASDEFAULT|Boolean|  
|COLUMN\_DEFAULT|문자열|  
|COLUMN\_FLAGS|Int64|  
|IS\_NULLABLE|Boolean|  
|DATA\_TYPE|Int32|  
|TYPE\_GUID|Guid|  
|CHARACTER\_MAXIMUM\_LENGTH|Int64|  
|CHARACTER\_OCTET\_LENGTH|Int64|  
|NUMERIC\_PRECISION|Int32|  
|NUMERIC\_SCALE|Int16|  
|DATETIME\_PRECISION|Int64|  
|CHARACTER\_SET\_CATALOG|문자열|  
|CHARACTER\_SET\_SCHEMA|문자열|  
|CHARACTER\_SET\_NAME|문자열|  
|COLLATION\_CATALOG|문자열|  
|COLLATION\_SCHEMA|문자열|  
|COLLATION\_NAME|문자열|  
|DOMAIN\_CATALOG|문자열|  
|DOMAIN\_SCHEMA|문자열|  
|DOMAIN\_NAME|문자열|  
|DESCRIPTION|문자열|  
|COLUMN\_LCID|Int32|  
|COLUMN\_COMPFLAGS|Int32|  
|COLUMN\_SORTID|Int32|  
|COLUMN\_TDSCOLLATION|Byte\[\]|  
|IS\_COMPUTED|Boolean|  
  
### 절차  
  
|열 이름|데이터 형식|  
|----------|------------|  
|PROCEDURE\_CATALOG|문자열|  
|PROCEDURE\_SCHEMA|문자열|  
|PROCEDURE\_NAME|문자열|  
|PROCEDURE\_TYPE|Int16|  
|PROCEDURE\_DEFINITION|문자열|  
|DESCRIPTION|문자열|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### ProcedureParameters  
  
|열 이름|데이터 형식|  
|----------|------------|  
|PROCEDURE\_CATALOG|문자열|  
|PROCEDURE\_SCHEMA|문자열|  
|PROCEDURE\_NAME|문자열|  
|PARAMETER\_NAME|문자열|  
|ORDINAL\_POSITION|Int32|  
|PARAMETER\_TYPE|Int32|  
|PARAMETER\_HASDEFAULT|Boolean|  
|PARAMETER\_DEFAULT|문자열|  
|IS\_NULLABLE|Boolean|  
|DATA\_TYPE|Int32|  
|CHARACTER\_MAXIMUM\_LENGTH|Int64|  
|CHARACTER\_OCTET\_LENGTH|Int64|  
|NUMERIC\_PRECISION|Int32|  
|NUMERIC\_SCALE|Int16|  
|DESCRIPTION|문자열|  
|TYPE\_NAME|문자열|  
|LOCAL\_TYPE\_NAME|문자열|  
  
### Catalog  
  
|열 이름|데이터 형식|  
|----------|------------|  
|CATALOG\_NAME|문자열|  
|DESCRIPTION|문자열|  
  
### Indexes  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_CATALOG|문자열|  
|TABLE\_SCHEMA|문자열|  
|TABLE\_NAME|문자열|  
|INDEX\_CATALOG|문자열|  
|INDEX\_SCHEMA|문자열|  
|INDEX\_NAME|문자열|  
|PRIMARY\_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL\_FACTOR|Int32|  
|INITIAL\_SIZE|Int32|  
|NULLS|Int32|  
|SORT\_BOOKMARKS|Boolean|  
|AUTO\_UPDATE|Boolean|  
|NULL\_COLLATION|Int32|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_NAME|문자열|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER\_CONDITION|문자열|  
|INTEGRATED|Boolean|  
  
## Microsoft Oracle OLE DB  
 Microsoft Oracle OLE DB Driver                                             .  
  
-   Tables  
  
-   Columns  
  
-   절차  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   뷰  
  
-   Indexes  
  
### Tables  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_CATALOG|문자열|  
|TABLE\_SCHEMA|문자열|  
|TABLE\_NAME|문자열|  
|TABLE\_TYPE|문자열|  
|TABLE\_GUID|Guid|  
|DESCRIPTION|문자열|  
|TABLE\_PROPID|Int64|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Columns  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_CATALOG|문자열|  
|TABLE\_SCHEMA|문자열|  
|TABLE\_NAME|문자열|  
|COLUMN\_NAME|문자열|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_HASDEFAULT|Boolean|  
|COLUMN\_DEFAULT|문자열|  
|COLUMN\_FLAGS|Int64|  
|IS\_NULLABLE|Boolean|  
|DATA\_TYPE|Int32|  
|TYPE\_GUID|Guid|  
|CHARACTER\_MAXIMUM\_LENGTH|Int64|  
|CHARACTER\_OCTET\_LENGTH|Int64|  
|NUMERIC\_PRECISION|Int32|  
|NUMERIC\_SCALE|Int16|  
|DATETIME\_PRECISION|Int64|  
|CHARACTER\_SET\_CATALOG|문자열|  
|CHARACTER\_SET\_SCHEMA|문자열|  
|CHARACTER\_SET\_NAME|문자열|  
|COLLATION\_CATALOG|문자열|  
|COLLATION\_SCHEMA|문자열|  
|COLLATION\_NAME|문자열|  
|DOMAIN\_CATALOG|문자열|  
|DOMAIN\_SCHEMA|문자열|  
|DOMAIN\_NAME|문자열|  
|DESCRIPTION|문자열|  
  
### 절차  
  
|열 이름|데이터 형식|  
|----------|------------|  
|PROCEDURE\_CATALOG|문자열|  
|PROCEDURE\_SCHEMA|문자열|  
|PROCEDURE\_NAME|문자열|  
|PROCEDURE\_TYPE|Int16|  
|PROCEDURE\_DEFINITION|문자열|  
|DESCRIPTION|문자열|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### ProcedureColumns  
  
|열 이름|데이터 형식|  
|----------|------------|  
|PROCEDURE\_CATALOG|문자열|  
|PROCEDURE\_SCHEMA|문자열|  
|PROCEDURE\_NAME|문자열|  
|COLUMN\_NAME|문자열|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|ROWSET\_NUMBER|Int64|  
|ORDINAL\_POSITION|Int64|  
|IS\_NULLABLE|Boolean|  
|DATA\_TYPE|Int32|  
|TYPE\_GUID|Guid|  
|CHARACTER\_MAXIMUM\_LENGTH|Int64|  
|CHARACTER\_OCTET\_LENGTH|Int64|  
|NUMERIC\_PRECISION|Int32|  
|NUMERIC\_SCALE|Int16|  
|DESCRIPTION|문자열|  
|OVERLOAD|Int16|  
  
### 뷰  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_CATALOG|문자열|  
|TABLE\_SCHEMA|문자열|  
|TABLE\_NAME|문자열|  
|VIEW\_DEFINITION|문자열|  
|CHECK\_OPTION|Boolean|  
|IS\_UPDATABLE|Boolean|  
|DESCRIPTION|문자열|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Indexes  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_CATALOG|문자열|  
|TABLE\_SCHEMA|문자열|  
|TABLE\_NAME|문자열|  
|INDEX\_CATALOG|문자열|  
|INDEX\_SCHEMA|문자열|  
|INDEX\_NAME|문자열|  
|PRIMARY\_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL\_FACTOR|Int32|  
|INITIAL\_SIZE|Int32|  
|NULLS|Int32|  
|SORT\_BOOKMARKS|Boolean|  
|AUTO\_UPDATE|Boolean|  
|NULL\_COLLATION|Int32|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_NAME|문자열|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER\_CONDITION|문자열|  
|INTEGRATED|Boolean|  
  
## Microsoft Jet OLE DB  
 Microsoft Jet OLE DB Driver                                             .  
  
-   Tables  
  
-   Columns  
  
-   절차  
  
-   뷰  
  
-   Indexes  
  
### Tables  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_CATALOG|문자열|  
|TABLE\_SCHEMA|문자열|  
|TABLE\_NAME|문자열|  
|TABLE\_TYPE|문자열|  
|TABLE\_GUID|Guid|  
|DESCRIPTION|문자열|  
|TABLE\_PROPID|Int64|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Columns  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_CATALOG|문자열|  
|TABLE\_SCHEMA|문자열|  
|TABLE\_NAME|문자열|  
|COLUMN\_NAME|문자열|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_HASDEFAULT|Boolean|  
|COLUMN\_DEFAULT|문자열|  
|COLUMN\_FLAGS|Int64|  
|IS\_NULLABLE|Boolean|  
|DATA\_TYPE|Int32|  
|TYPE\_GUID|Guid|  
|CHARACTER\_MAXIMUM\_LENGTH|Int64|  
|CHARACTER\_OCTET\_LENGTH|Int64|  
|NUMERIC\_PRECISION|Int32|  
|NUMERIC\_SCALE|Int16|  
|DATETIME\_PRECISION|Int64|  
|CHARACTER\_SET\_CATALOG|문자열|  
|CHARACTER\_SET\_SCHEMA|문자열|  
|CHARACTER\_SET\_NAME|문자열|  
|COLLATION\_CATALOG|문자열|  
|COLLATION\_SCHEMA|문자열|  
|COLLATION\_NAME|문자열|  
|DOMAIN\_CATALOG|문자열|  
|DOMAIN\_SCHEMA|문자열|  
|DOMAIN\_NAME|문자열|  
|DESCRIPTION|문자열|  
  
### 절차  
  
|열 이름|데이터 형식|  
|----------|------------|  
|PROCEDURE\_CATALOG|문자열|  
|PROCEDURE\_SCHEMA|문자열|  
|PROCEDURE\_NAME|문자열|  
|PROCEDURE\_TYPE|Int16|  
|PROCEDURE\_DEFINITION|문자열|  
|DESCRIPTION|문자열|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### 뷰  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_CATALOG|문자열|  
|TABLE\_SCHEMA|문자열|  
|TABLE\_NAME|문자열|  
|VIEW\_DEFINITION|문자열|  
|CHECK\_OPTION|Boolean|  
|IS\_UPDATABLE|Boolean|  
|DESCRIPTION|문자열|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Indexes  
  
|열 이름|데이터 형식|  
|----------|------------|  
|TABLE\_CATALOG|문자열|  
|TABLE\_SCHEMA|문자열|  
|TABLE\_NAME|문자열|  
|INDEX\_CATALOG|문자열|  
|INDEX\_SCHEMA|문자열|  
|INDEX\_NAME|문자열|  
|PRIMARY\_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL\_FACTOR|Int32|  
|INITIAL\_SIZE|Int32|  
|NULLS|Int32|  
|SORT\_BOOKMARKS|Boolean|  
|AUTO\_UPDATE|Boolean|  
|NULL\_COLLATION|Int32|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_NAME|문자열|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER\_CONDITION|문자열|  
|INTEGRATED|Boolean|  
  
## 참고 항목  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)