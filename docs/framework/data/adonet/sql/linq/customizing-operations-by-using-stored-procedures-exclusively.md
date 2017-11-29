---
title: "단독으로 저장 프로시저를 사용하여 작업 사용자 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 075565570d8dccc9ebd41d4a8d56014f8bb0f039
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a><span data-ttu-id="1ac40-102">단독으로 저장 프로시저를 사용하여 작업 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="1ac40-102">Customizing Operations by Using Stored Procedures Exclusively</span></span>
<span data-ttu-id="1ac40-103">저장 프로시저만을 사용한 데이터 액세스는 일반적인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="1ac40-103">Access to data by using only stored procedures is a common scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ac40-104">예제</span><span class="sxs-lookup"><span data-stu-id="1ac40-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="1ac40-105">설명</span><span class="sxs-lookup"><span data-stu-id="1ac40-105">Description</span></span>  
 <span data-ttu-id="1ac40-106">제공 되는 예제를 수정할 수 있습니다 [사용자 지정 작업에서 사용 하 여 저장 프로시저](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) (함 동적 SQL에서 실행) 첫 번째 쿼리도 저장된 프로시저를 래핑하는 메서드 호출으로 대체 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac40-106">You can modify the example provided in [Customizing Operations By Using Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md) by replacing even the first query (which causes dynamic SQL execution) with a method call that wraps a stored procedure.</span></span>  
  
 <span data-ttu-id="1ac40-107">다음 예제와 같이 `CustomersByCity`는 메서드로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="1ac40-107">Assume `CustomersByCity` is the method, as in the following example.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1ac40-108">코드</span><span class="sxs-lookup"><span data-stu-id="1ac40-108">Code</span></span>  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 <span data-ttu-id="1ac40-109">다음 코드는 동적 SQL 없이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ac40-109">The following code executes without any dynamic SQL.</span></span>  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="1ac40-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ac40-110">See Also</span></span>  
 [<span data-ttu-id="1ac40-111">기본 동작 재정의에서 개발자의 책임</span><span class="sxs-lookup"><span data-stu-id="1ac40-111">Responsibilities of the Developer In Overriding Default Behavior</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)
