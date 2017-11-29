---
title: "지원되지 않는 기능"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6dd8ccebd278fdc36c536c49f7f1d4262b2de8c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="unsupported-functionality"></a><span data-ttu-id="e6b94-102">지원되지 않는 기능</span><span class="sxs-lookup"><span data-stu-id="e6b94-102">Unsupported Functionality</span></span>
<span data-ttu-id="e6b94-103">LINQ to SQL에서 다음 SQL 기능은 기존 CLR(공용 언어 런타임) 및 .NET Framework 구문의 트랜잭션을 통해 노출될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6b94-103">In LINQ to SQL, the following SQL functionality cannot be exposed through translation of existing common language runtime (CLR) and .NET Framework constructs:</span></span>  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     <span data-ttu-id="e6b94-104">`LIKE`는 직접 변환을 통해 지원되지 않지만 유사한 기능이 <xref:System.Data.Linq.SqlClient.SqlMethods> 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6b94-104">Although `LIKE` is not supported through direct translation, similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span> <span data-ttu-id="e6b94-105">자세한 내용은 <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6b94-105">For more information, see <xref:System.Data.Linq.SqlClient.SqlMethods.Like%2A?displayProperty=nameWithType>.</span></span>  
  
-   `DATEDIFF`  
  
     <span data-ttu-id="e6b94-106">LINQ to SQL에서는 `DATEDIFF`를 제한적으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e6b94-106">LINQ to SQL has limited support for `DATEDIFF`.</span></span> <span data-ttu-id="e6b94-107">유사한 기능은 <xref:System.Data.Linq.SqlClient.SqlMethods> 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6b94-107">Similar functionality exists in the <xref:System.Data.Linq.SqlClient.SqlMethods> class.</span></span>  
  
-   `ROUND`  
  
     <span data-ttu-id="e6b94-108">LINQ to SQL에서는 `ROUND`를 제한적으로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e6b94-108">LINQ to SQL has limited support for `ROUND`.</span></span> <span data-ttu-id="e6b94-109">자세한 내용은 참조 [System.Math 메서드](system-math-methods.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e6b94-109">For more information, see [System.Math Methods](system-math-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6b94-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6b94-110">See Also</span></span>  
 [<span data-ttu-id="e6b94-111">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="e6b94-111">Data Types and Functions</span></span>](data-types-and-functions.md)
