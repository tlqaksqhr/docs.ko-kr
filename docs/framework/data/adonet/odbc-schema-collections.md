---
title: "ODBC 스키마 컬렉션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 889e84db39af1257d709ef049e18d4397ea700d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="odbc-schema-collections"></a>ODBC 스키마 컬렉션
이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 ODBC 드라이버에서 지원하는 스키마 컬렉션에 대해 설명합니다.  
  
## <a name="microsoft-sql-server-odbc-driver"></a>Microsoft SQL Server ODBC Driver  
 Microsoft SQL Server ODBC Driver에서는 공통 스키마 컬렉션을 비롯 하 여 다음과 같은 특정 스키마 컬렉션을 지원합니다.  
  
-   Tables  
  
-   Indexes  
  
-   Columns  
  
-   절차  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   뷰  
  
### <a name="tables-and-views"></a>Tables 및 Views  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_CAT|문자열|  
|TABLE_SCHEM|문자열|  
|TABLE_NAME|문자열|  
|TABLE_TYPE|문자열|  
|REMARKS|문자열|  
  
### <a name="indexes"></a>Indexes  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_CAT|문자열|  
|TABLE_SCHEM|문자열|  
|TABLE_NAME|문자열|  
|NON_UNIQUE|Int16|  
|INDEX_QUALIFIER|문자열|  
|INDEX_NAME|문자열|  
|TYPE|Int16|  
|ORDINAL_POSITION|Int16|  
|COLUMN_NAME|문자열|  
|ASC_OR_DESC|문자열|  
|CARDINATLITY|Int32|  
|PAGES|Int32|  
|FILTER_CONDITION|문자열|  
|SS_TYPE_SCHEMA|문자열|  
|SS_DATA_TYPE|Byte|  
  
### <a name="columns"></a>Columns  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_CAT|문자열|  
|TABLE_SCHEM|문자열|  
|TABLE_NAME|문자열|  
|COLUMN_NAME|문자열|  
|DATA_TYPE|Int16|  
|TYPE_NAME|문자열|  
|COLUMN_SIZE|Int32|  
|BUFFER_LENGTH|Int32|  
|DECIMAL_DIGITS|Int16|  
|NUM_PREC_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|문자열|  
|COLUMN_DEF|문자열|  
|SQL_DATA_TYPE|Int16|  
|SQL_DATETIME_SUB|Int16|  
|CHAR_OCTET_LENGTH|Int32|  
|ORDINAL_POSITION|Int32|  
|IS_NULLABLE|문자열|  
|SS_TYPE_CATALOG|문자열|  
|SS_TYPE_SCHEMA|문자열|  
|SS_DATA_TYPE|Byte|  
  
### <a name="procedures"></a>절차  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|PROCEDURE_CAT|문자열|  
|PROCEDURE_SCHEM|문자열|  
|PROCEDURE_NAME|문자열|  
|NUM_INPUT_PARAMS|Int32|  
|NUM_OUTPUT_PARAMS|Int32|  
|NUM_RESULT_SETS|Int32|  
|REMARKS|문자열|  
|PROCEDURE_TYPE|Int16|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|PROCEDURE_CAT|문자열|  
|PROCEDURE_SCHEM|문자열|  
|PROCEDURE_NAME|문자열|  
|COLUMN_NAME|문자열|  
|COLUMN_TYPE|Int16|  
|DATA_TYPE|Int16|  
|TYPE_NAME|문자열|  
|COLUMN_SIZE|Int32|  
|BUFFER_LENGTH|Int32|  
|DECIMAL_DIGITS|Int16|  
|NUM_PREC_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|문자열|  
|COLUMN_DEF|문자열|  
|SQL_DATA_TYPE|Int16|  
|SQL_DATETIME_SUB|Int16|  
|CHAR_OCTET_LENGTH|Int32|  
|ORDINAL_POSITION|Int32|  
|IS_NULLABLE|문자열|  
|SS_TYPE_CATALOG|문자열|  
|SS_TYPE_SCHEMA|문자열|  
|SS_DATA_TYPE|Byte|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|PROCEDURE_CAT|문자열|  
|PROCEDURE_SCHEM|문자열|  
|PROCEDURE_NAME|문자열|  
|COLUMN_NAME|문자열|  
|COLUMN_TYPE|Int16|  
|DATA_TYPE|Int16|  
|TYPE_NAME|문자열|  
|COLUMN_SIZE|Int32|  
|BUFFER_LENGTH|Int32|  
|DECIMAL_DIGITS|Int16|  
|NUM_PREC_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|문자열|  
|COLUMN_DEF|문자열|  
|SQL_DATA_TYPE|Int16|  
|SQL_DATETIME_SUB|Int16|  
|CHAR_OCTET_LENGTH|Int32|  
|ORDINAL_POSITION|Int32|  
|IS_NULLABLE|문자열|  
|SS_TYPE_CATALOG|문자열|  
|SS_TYPE_SCHEMA|문자열|  
|SS_DATA_TYPE|Byte|  
  
## <a name="microsoft-oracle-odbc-driver"></a>Microsoft Oracle ODBC Driver  
 Microsoft SQL Server Oracle ODBC Driver에서는 공통 스키마 컬렉션을 비롯 하 여 다음과 같은 특정 스키마 컬렉션을 지원합니다.  
  
-   Tables  
  
-   Columns  
  
-   절차  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   뷰  
  
-   Indexes  
  
### <a name="tables-and-views"></a>Tables 및 Views  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_QUALIFIER|문자열|  
|TABLE_OWNER|문자열|  
|TABLE_NAME|문자열|  
|TABLE_TYPE|문자열|  
|REMARKS|문자열|  
  
### <a name="columns"></a>Columns  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_QUALIFIER|문자열|  
|TABLE_OWNER|문자열|  
|TABLE_NAME|문자열|  
|COLUMN_NAME|문자열|  
|DATA_TYPE|Int16|  
|TYPE_NAME|문자열|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|문자열|  
|ORDINAL_POSITION|Int32|  
  
### <a name="procedures"></a>절차  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|PROCEDURE_QUALIFIER|문자열|  
|PROCEDURE_OWNER|문자열|  
|PROCEDURE_NAME|문자열|  
|NUM_INPUT_PARAMS|Int16|  
|NUM_OUTPUT_PARAMS|Int16|  
|NUM_RESULT_SETS|Int16|  
|REMARKS|문자열|  
|PROCEDURE_TYPE|Int16|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|PROCEDURE_QUALIFIER|문자열|  
|PROCEDURE_OWNER|문자열|  
|PROCEDURE_NAME|문자열|  
|COLUMN_NAME|문자열|  
|COLUMN_TYPE|Int16|  
|DATA_TYPE|Int16|  
|TYPE_NAME|문자열|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|문자열|  
|OVERLOAD|Int32|  
|ORDINAL_POSITION|Int32|  
  
## <a name="microsoft-jet-odbc-driver"></a>Microsoft Jet ODBC Driver  
 Microsoft Jet ODBC Driver                                             .  
  
-   Tables  
  
-   Indexes  
  
-   Columns  
  
-   절차  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   뷰  
  
### <a name="tables-and-views"></a>Tables 및 Views  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_QUALIFIER|문자열|  
|TABLE_OWNER|문자열|  
|TABLE_NAME|문자열|  
|TABLE_TYPE|문자열|  
|REMARKS|문자열|  
  
### <a name="columns"></a>Columns  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|TABLE_QUALIFIER|문자열|  
|TABLE_OWNER|문자열|  
|TABLE_NAME|문자열|  
|COLUMN_NAME|문자열|  
|DATA_TYPE|Int16|  
|TYPE_NAME|문자열|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|문자열|  
|ORDINAL_POSITION|Int32|  
  
### <a name="procedures"></a>절차  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|PROCEDURE_QUALIFIER|문자열|  
|PROCEDURE_OWNER|문자열|  
|PROCEDURE_NAME|문자열|  
|NUM_INPUT_PARAMS|Int16|  
|NUM_OUTPUT_PARAMS|Int16|  
|NUM_RESULT_SETS|Int16|  
|REMARKS|문자열|  
|PROCEDURE_TYPE|Int16|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|PROCEDURE_QUALIFIER|문자열|  
|PROCEDURE_OWNER|문자열|  
|PROCEDURE_NAME|문자열|  
|COLUMN_NAME|문자열|  
|COLUMN_TYPE|Int16|  
|DATA_TYPE|Int16|  
|TYPE_NAME|문자열|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|문자열|  
|OVERLOAD|Int32|  
|ORDINAL_POSITION|Int32|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|열 이름|데이터 형식|  
|----------------|--------------|  
|PROCEDURE_CAT|문자열|  
|PROCEDURE_SCHEM|문자열|  
|PROCEDURE_NAME|문자열|  
|COLUMN_NAME|문자열|  
|COLUMN_TYPE|Int16|  
|DATA_TYPE|Int16|  
|TYPE_NAME|문자열|  
|COLUMN_SIZE|Int32|  
|BUFFER_LENGTH|Int32|  
|DECIMAL_DIGITS|Int16|  
|NUM_PREC_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|문자열|  
|COLUMN_DEF|문자열|  
|SQL_DATA_TYPE|Int16|  
|SQL_DATETIME_SUB|Int16|  
|CHAR_OCTET_LENGTH|Int32|  
|ORDINAL_POSITION|Int32|  
|IS_NULLABLE|문자열|  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
