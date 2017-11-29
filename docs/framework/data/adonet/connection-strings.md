---
title: "ADO.NET의 연결 문자열"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: bd787373b869c31727cfc0d027b6b98774b0d630
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="connection-strings-in-adonet"></a>ADO.NET의 연결 문자열
.NET Framework 2.0에서는 연결 문자열 작성기 클래스에 새로운 키워드를 추가하는 기능을 비롯하여 연결 문자열로 작업하는 데 사용할 수 있는 새로운 기능을 지원합니다. 이러한 기능을 사용하여 런타임에 유효한 연결 문자열을 작성할 수 있습니다.  
  
 연결 문자열에는 데이터 공급자에서 데이터 소스에 매개 변수로 전달되는 초기화 정보가 있습니다. 연결 문자열 구문은 데이터 공급자에 따라 다르며 연결을 여는 동안 연결 문자열이 구문 분석됩니다. 구문 오류가 있으면 런타임 예외가 발생하지만, 다른 오류는 데이터 소스에서 연결 정보를 받은 후에만 발생합니다. 유효성을 검사한 후 데이터 소스에서 연결 문자열에 지정된 옵션을 적용하고 연결을 엽니다.  
  
 연결 문자열 형식은 키/값 매개 변수 쌍의 세미콜론으로 구분된 목록입니다.  
  
 `keyword1=value; keyword2=value;`  
  
 키워드는 대/소문자를 구분하지 않으며 키/값 쌍 간의 공백은 무시됩니다. 하지만 값은 데이터 소스에 따라 대/소문자를 구분해야 하는 경우도 있습니다. 세미콜론, 작은따옴표 또는 큰따옴표가 포함된 값은 큰따옴표로 묶어야 합니다.  
  
 유효한 연결 문자열 구문은 공급자에 따라 다르며 ODBC와 유사한 초기 API에서부터 수년에 걸쳐 발전해 왔습니다. .NET Framework Data Provider for SQL Server(SqlClient)는 이전 구문의 많은 요소를 통합하므로 대개 일반적인 연결 문자열 구문보다 융통성이 뛰어납니다. 연결 문자열 구문 요소에는 유효하게 사용할 수 있는 동의어가 많지만 구문과 맞춤법을 잘못 입력하는 일부 경우에는 문제가 발생할 수 있습니다. 예를 들어 "`Integrated Security=true`"는 유효하지만 "`IntegratedSecurity=true`"는 오류를 일으킵니다. 또한 유효성이 검증되지 않은 사용자 입력을 통해 런타임에 구성된 연결 문자열은 문자열 삽입 공격으로 이어져 데이터 소스의 보안을 위협할 수 있습니다.  
  
 이러한 문제를 해결하기 위해 ADO.NET 2.0에서는 각 .NET Framework 데이터 공급자에 사용할 수 있는 새로운 연결 문자열 작성기가 도입되었습니다. 키워드는 속성으로 노출되므로 데이터 소스에 제출하기 전에 연결 문자열 구문의 유효성을 검사할 수 있습니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [연결 문자열 작성기](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 `ConnectionStringBuilder` 클래스를 사용하여 런타임에 유효한 연결 문자열을 구성하는 방법을 보여 줍니다.  
  
 [연결 문자열 및 구성 파일](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)  
 구성 파일에서 연결 문자열을 저장하고 검색하는 방법을 보여 줍니다.  
  
 [연결 문자열 구문](../../../../docs/framework/data/adonet/connection-string-syntax.md)  
 `SqlClient`, `OracleClient`, `OleDb` 및 `Odbc`에 대한 공급자별 연결 문자열을 구성하는 방법을 설명합니다.  
  
 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 데이터 소스 연결에 사용되는 정보를 보호하는 기법을 보여 줍니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 소스에 연결](/cpp/data/odbc/connecting-to-a-data-source)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
