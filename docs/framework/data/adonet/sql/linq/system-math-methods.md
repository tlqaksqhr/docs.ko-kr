---
title: "System.Math 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 8c5f19918ca1c80daffab482436ab6ce018321f5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="systemmath-methods"></a><span data-ttu-id="9dc1b-102">System.Math 메서드</span><span class="sxs-lookup"><span data-stu-id="9dc1b-102">System.Math Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="9dc1b-103">에서는 다음 <xref:System.Math> 메서드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc1b-103"> does not support the following <xref:System.Math> methods.</span></span>  
  
-   <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=nameWithType>  
  
-   <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=nameWithType>  
  
## <a name="differences-from-net"></a><span data-ttu-id="9dc1b-104">.NET과의 차이점</span><span class="sxs-lookup"><span data-stu-id="9dc1b-104">Differences from .NET</span></span>  
 <span data-ttu-id="9dc1b-105">.NET Framework의 반올림 구문은 SQL Server와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9dc1b-105">The .NET Framework has different rounding semantics from SQL Server.</span></span> <span data-ttu-id="9dc1b-106"><xref:System.Math.Round%2A> .NET Framework의 메서드가 *Banker rounding*.5 끝나는 숫자를 반올림할 여기서는 가장 가까운 짝수 대신 다음 높은 자리에 합니다.</span><span class="sxs-lookup"><span data-stu-id="9dc1b-106">The <xref:System.Math.Round%2A> method in the .NET Framework performs *Banker's rounding*, where numbers that ends in .5 round to the nearest even digit instead of to the next higher digit.</span></span> <span data-ttu-id="9dc1b-107">예를 들어 2.5는 2가 되고 3.5는 4가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc1b-107">For example, 2.5 rounds to 2, while 3.5 rounds to 4.</span></span> <span data-ttu-id="9dc1b-108">이 방법은 많은 데이터 트랜잭션에서 값이 높아질수록 발생할 수 있는 체계적 오차를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc1b-108">(This technique helps avoid systematic bias toward higher values in large data transactions.)</span></span>  
  
 <span data-ttu-id="9dc1b-109">SQL에서 `ROUND` 함수는 항상 0 이상의 정수 값으로 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc1b-109">In SQL, the `ROUND` function instead always rounds away from 0.</span></span> <span data-ttu-id="9dc1b-110">따라서 2.5의 경우 .NET Framework에서는 2가 되는데 반해 SQL에서는 3이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9dc1b-110">Therefore 2.5 rounds to 3, contrasted with its rounding to 2 in the .NET Framework.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="9dc1b-111">은 SQL `ROUND` 구문을 따르며 은행원의 반올림을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9dc1b-111"> passes through to the SQL `ROUND` semantics and does not try to implement Banker's rounding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dc1b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9dc1b-112">See Also</span></span>  
 [<span data-ttu-id="9dc1b-113">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="9dc1b-113">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
