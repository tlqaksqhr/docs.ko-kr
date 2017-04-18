---
title: "CLR 저장 프로시저 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# CLR 저장 프로시저
저장 프로시저는 스칼라 식에 사용할 수 없는 루틴입니다.  또한 클라이언트에 테이블 형식 결과와 메시지를 반환하고 DDL\(데이터 정의 언어\) 및 DML\(데이터 조작 언어\) 문을 호출하며 출력 매개 변수를 반환합니다.  
  
> [!NOTE]
>  Microsoft Visual Basic에서는 Microsoft Visual C\#과 다른 방식으로 출력 매개 변수를 지원합니다.  따라서 다음과 같이 참조로 매개 변수를 전달하도록 지정하고 출력 매개 변수를 나타내도록 \<Out\(\)\> 특성을 적용해야 합니다.  
  
```  
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```  
  
 자세한 내용을 보려면 현재 사용하고 있는 SQL Server 버전에 해당하는 SQL Server 온라인 설명서 버전을 참조하세요.  
  
 **SQL Server 온라인 설명서**  
  
1.  [CLR 저장 프로시저](http://go.microsoft.com/fwlink/?LinkId=115400)  
  
## 참고 항목  
 [Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/ko-kr/5358a825-e19b-49aa-8214-674ce5fed1da)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)