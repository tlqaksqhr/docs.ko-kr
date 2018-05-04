---
title: OLE DB 스키마 컬렉션
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: f1cb5e1fe967088b44fa4045dfe50c1c57d963eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ole-db-schema-collections"></a>OLE DB 스키마 컬렉션
이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 OLE DB 공급자에서 지원하는 스키마 컬렉션에 대해 설명합니다.  
  
## <a name="microsoft-sql-server-ole-db-provider"></a>Microsoft SQL Server OLE DB 공급자  
 Microsoft SQL Server OLE DB Driver에서는 공통 스키마 컬렉션을 비롯 하 여 다음과 같은 특정 스키마 컬렉션을 지원합니다.  
  
-   Tables  
  
-   Columns  
  
-   절차  
  
-   ProcedureParameters  
  
-   Catalog  
  
-   Indexes  
  
### <a name="tables"></a>Tables  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_CATALOG|문자열|  
|TABLE_SCHEMA|문자열|  
|TABLE_NAME|문자열|  
|TABLE_TYPE|문자열|  
|TABLE_GUID|Guid|  
|DESCRIPTION|문자열|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Columns  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_CATALOG|문자열|  
|TABLE_SCHEMA|문자열|  
|TABLE_NAME|문자열|  
|COLUMN_NAME|문자열|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|문자열|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|문자열|  
|CHARACTER_SET_SCHEMA|문자열|  
|CHARACTER_SET_NAME|문자열|  
|COLLATION_CATALOG|문자열|  
|COLLATION_SCHEMA|문자열|  
|COLLATION_NAME|문자열|  
|DOMAIN_CATALOG|문자열|  
|DOMAIN_SCHEMA|문자열|  
|DOMAIN_NAME|문자열|  
|DESCRIPTION|문자열|  
|COLUMN_LCID|Int32|  
|COLUMN_COMPFLAGS|Int32|  
|COLUMN_SORTID|Int32|  
|COLUMN_TDSCOLLATION|Byte[]|  
|IS_COMPUTED|Boolean|  
  
### <a name="procedures"></a>절차  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|PROCEDURE_CATALOG|문자열|  
|PROCEDURE_SCHEMA|문자열|  
|PROCEDURE_NAME|문자열|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|문자열|  
|DESCRIPTION|문자열|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|PROCEDURE_CATALOG|문자열|  
|PROCEDURE_SCHEMA|문자열|  
|PROCEDURE_NAME|문자열|  
|PARAMETER_NAME|문자열|  
|ORDINAL_POSITION|Int32|  
|PARAMETER_TYPE|Int32|  
|PARAMETER_HASDEFAULT|Boolean|  
|PARAMETER_DEFAULT|문자열|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DESCRIPTION|문자열|  
|TYPE_NAME|문자열|  
|LOCAL_TYPE_NAME|문자열|  
  
### <a name="catalog"></a>Catalog  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|CATALOG_NAME|문자열|  
|DESCRIPTION|문자열|  
  
### <a name="indexes"></a>Indexes  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_CATALOG|문자열|  
|TABLE_SCHEMA|문자열|  
|TABLE_NAME|문자열|  
|INDEX_CATALOG|문자열|  
|INDEX_SCHEMA|문자열|  
|INDEX_NAME|문자열|  
|PRIMARY_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|문자열|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|문자열|  
|INTEGRATED|Boolean|  
  
## <a name="microsoft-oracle-ole-db-provider"></a>Microsoft Oracle OLE DB      
 Microsoft Oracle OLE DB Driver                                             .  
  
-   Tables  
  
-   Columns  
  
-   절차  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   뷰  
  
-   Indexes  
  
### <a name="tables"></a>Tables  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_CATALOG|문자열|  
|TABLE_SCHEMA|문자열|  
|TABLE_NAME|문자열|  
|TABLE_TYPE|문자열|  
|TABLE_GUID|Guid|  
|DESCRIPTION|문자열|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Columns  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_CATALOG|문자열|  
|TABLE_SCHEMA|문자열|  
|TABLE_NAME|문자열|  
|COLUMN_NAME|문자열|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|문자열|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|문자열|  
|CHARACTER_SET_SCHEMA|문자열|  
|CHARACTER_SET_NAME|문자열|  
|COLLATION_CATALOG|문자열|  
|COLLATION_SCHEMA|문자열|  
|COLLATION_NAME|문자열|  
|DOMAIN_CATALOG|문자열|  
|DOMAIN_SCHEMA|문자열|  
|DOMAIN_NAME|문자열|  
|DESCRIPTION|문자열|  
  
### <a name="procedures"></a>절차  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|PROCEDURE_CATALOG|문자열|  
|PROCEDURE_SCHEMA|문자열|  
|PROCEDURE_NAME|문자열|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|문자열|  
|DESCRIPTION|문자열|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|PROCEDURE_CATALOG|문자열|  
|PROCEDURE_SCHEMA|문자열|  
|PROCEDURE_NAME|문자열|  
|COLUMN_NAME|문자열|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ROWSET_NUMBER|Int64|  
|ORDINAL_POSITION|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DESCRIPTION|문자열|  
|OVERLOAD|Int16|  
  
### <a name="views"></a>뷰  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_CATALOG|문자열|  
|TABLE_SCHEMA|문자열|  
|TABLE_NAME|문자열|  
|VIEW_DEFINITION|문자열|  
|CHECK_OPTION|Boolean|  
|IS_UPDATABLE|Boolean|  
|DESCRIPTION|문자열|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Indexes  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_CATALOG|문자열|  
|TABLE_SCHEMA|문자열|  
|TABLE_NAME|문자열|  
|INDEX_CATALOG|문자열|  
|INDEX_SCHEMA|문자열|  
|INDEX_NAME|문자열|  
|PRIMARY_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|문자열|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|문자열|  
|INTEGRATED|Boolean|  
  
## <a name="microsoft-jet-ole-db-provider"></a>Microsoft Jet OLE DB      
 Microsoft Jet OLE DB Driver                                             .  
  
-   Tables  
  
-   Columns  
  
-   절차  
  
-   뷰  
  
-   Indexes  
  
### <a name="tables"></a>Tables  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_CATALOG|문자열|  
|TABLE_SCHEMA|문자열|  
|TABLE_NAME|문자열|  
|TABLE_TYPE|문자열|  
|TABLE_GUID|Guid|  
|DESCRIPTION|문자열|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Columns  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_CATALOG|문자열|  
|TABLE_SCHEMA|문자열|  
|TABLE_NAME|문자열|  
|COLUMN_NAME|문자열|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|문자열|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|문자열|  
|CHARACTER_SET_SCHEMA|문자열|  
|CHARACTER_SET_NAME|문자열|  
|COLLATION_CATALOG|문자열|  
|COLLATION_SCHEMA|문자열|  
|COLLATION_NAME|문자열|  
|DOMAIN_CATALOG|문자열|  
|DOMAIN_SCHEMA|문자열|  
|DOMAIN_NAME|문자열|  
|DESCRIPTION|문자열|  
  
### <a name="procedures"></a>절차  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|PROCEDURE_CATALOG|문자열|  
|PROCEDURE_SCHEMA|문자열|  
|PROCEDURE_NAME|문자열|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|문자열|  
|DESCRIPTION|문자열|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="views"></a>뷰  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_CATALOG|문자열|  
|TABLE_SCHEMA|문자열|  
|TABLE_NAME|문자열|  
|VIEW_DEFINITION|문자열|  
|CHECK_OPTION|Boolean|  
|IS_UPDATABLE|Boolean|  
|DESCRIPTION|문자열|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Indexes  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_CATALOG|문자열|  
|TABLE_SCHEMA|문자열|  
|TABLE_NAME|문자열|  
|INDEX_CATALOG|문자열|  
|INDEX_SCHEMA|문자열|  
|INDEX_NAME|문자열|  
|PRIMARY_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|문자열|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimal|  
|PAGES|Int32|  
|FILTER_CONDITION|문자열|  
|INTEGRATED|부울|  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
