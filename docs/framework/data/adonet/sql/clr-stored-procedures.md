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
# <a name="clr-stored-procedures"></a><span data-ttu-id="1bb67-102">CLR 저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="1bb67-102">CLR Stored Procedures</span></span>
<span data-ttu-id="1bb67-103">저장 프로시저는 스칼라 식에 사용할 수 없는 루틴입니다.</span><span class="sxs-lookup"><span data-stu-id="1bb67-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="1bb67-104">또한 클라이언트에 테이블 형식 결과와 메시지를 반환하고 DDL(데이터 정의 언어) 및 DML(데이터 조작 언어) 문을 호출하며 출력 매개 변수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb67-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bb67-105">Microsoft Visual Basic에서는 Microsoft Visual C#과 다른 방식으로 출력 매개 변수를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1bb67-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="1bb67-106">참조로 매개 변수를 전달 하 고 적용을 지정 해야 합니다는 \<out () > 특성을 다음과 같이 출력 매개 변수를 나타내는:</span><span class="sxs-lookup"><span data-stu-id="1bb67-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```  
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```  
  
 <span data-ttu-id="1bb67-107">자세한 내용을 보려면 현재 사용하고 있는 SQL Server 버전에 해당하는 SQL Server 온라인 설명서 버전을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bb67-107">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="1bb67-108">**SQL Server 온라인 설명서**</span><span class="sxs-lookup"><span data-stu-id="1bb67-108">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="1bb67-109">CLR 저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="1bb67-109">CLR Stored Procedures</span></span>](http://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="1bb67-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1bb67-110">See Also</span></span>  
 [<span data-ttu-id="1bb67-111">관리 코드에서 SQL Server 2005 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="1bb67-111">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="1bb67-112">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="1bb67-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
