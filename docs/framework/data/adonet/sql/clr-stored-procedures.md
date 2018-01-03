---
title: "CLR 저장 프로시저"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: dfed0124c33c90427c9b888f5aa7bb191aea0400
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="clr-stored-procedures"></a>CLR 저장 프로시저
저장 프로시저는 스칼라 식에 사용할 수 없는 루틴입니다. 또한 클라이언트에 테이블 형식 결과와 메시지를 반환하고 DDL(데이터 정의 언어) 및 DML(데이터 조작 언어) 문을 호출하며 출력 매개 변수를 반환합니다.  
  
> [!NOTE]
>  Microsoft Visual Basic에서는 Microsoft Visual C#과 다른 방식으로 출력 매개 변수를 지원합니다. 참조로 매개 변수를 전달 하 고 적용을 지정 해야 합니다는 \<out () > 특성을 다음과 같이 출력 매개 변수를 나타내는:  
  
```  
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```  
  
 자세한 내용을 보려면 현재 사용하고 있는 SQL Server 버전에 해당하는 SQL Server 온라인 설명서 버전을 참조하세요.  
  
 **SQL Server 온라인 설명서**  
  
1.  [CLR 저장 프로시저](http://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a>참고 항목  
 [관리 코드에서 SQL Server 2005 개체 만들기](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
