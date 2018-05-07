---
title: SQL Server 이진 및 큰 값 데이터
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: c0202f6dc17d36fafb28206e17b71fc6d68d88c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="sql-server-binary-and-large-value-data"></a>SQL Server 이진 및 큰 값 데이터
SQL Server에서는 `max`, `varchar` 및 `nvarchar` 데이터 형식의 저장소 용량을 확장하는 `varbinary` 지정자를 지원합니다. `varchar(max)``nvarchar(max)`, 및 `varbinary(max)` 이라고 *큰 값 데이터 형식*합니다. 큰 값 데이터 형식을 사용하면 데이터를 최대 2^31-1바이트까지 저장할 수 있습니다.  
  
 SQL Server 2008에서는 데이터 형식은 아니고 열에 정의할 수 있는 특성인 FILESTREAM 특성을 지원합니다. 이 특성을 사용하면 큰 값 데이터를 데이터베이스가 아니라 파일 시스템에 저장할 수 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [ADO.NET에서 큰 값(최대값) 데이터 수정](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 큰 값 데이터 형식을 사용하는 방법을 설명합니다.  
  
 [FILESTREAM 데이터](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 FILESTREAM 특성을 사용하여 SQL Server 2008에 저장된 큰 값 데이터로 작업하는 방법에 대해 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SQL Server 데이터 형식 및 ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [ADO.NET에서 SQL Server 데이터 작업](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [ADO.NET에서 데이터 검색 및 수정](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
