---
title: "Null 의미 체계"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8d32f73c8c2095c23ec164ad40fd1ab27ef1153a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="null-semantics"></a><span data-ttu-id="a49c5-102">Null 의미 체계</span><span class="sxs-lookup"><span data-stu-id="a49c5-102">Null Semantics</span></span>
<span data-ttu-id="a49c5-103">다음 표에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ( `null` 의`Nothing` ) 문제에 대해 설명하는 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]설명서의 여러 부분에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a49c5-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) issues are discussed.</span></span>  
  
|<span data-ttu-id="a49c5-104">항목</span><span class="sxs-lookup"><span data-stu-id="a49c5-104">Topic</span></span>|<span data-ttu-id="a49c5-105">설명</span><span class="sxs-lookup"><span data-stu-id="a49c5-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a49c5-106">SQL-CLR 형식 불일치</span><span class="sxs-lookup"><span data-stu-id="a49c5-106">SQL-CLR Type Mismatches</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|<span data-ttu-id="a49c5-107">이 항목의 "Null 의미 체계" 단원에서는 세 개의 SQL 부울 상태와 두 개의 CLR(공용 언어 런타임) <xref:System.Boolean>상태인 리터럴 `Nothing` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)])과 `null` (C#)을 비교 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a49c5-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="a49c5-108">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="a49c5-108">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|<span data-ttu-id="a49c5-109">이 항목의 "Null 의미 체계" 단원에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 null을 의미론적으로 비교 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a49c5-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="a49c5-110">System.String 메서드</span><span class="sxs-lookup"><span data-stu-id="a49c5-110">System.String Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|<span data-ttu-id="a49c5-111">이 항목의 ".NET과의 차이점" 단원에서는 문자열이 null인 것을 의미할 수도 있고 찾은 위치가 0인 것을 의미할 수도 있는 <xref:System.String.LastIndexOf%2A> 의 반환 값 0에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a49c5-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="a49c5-112">숫자 시퀀스에서 값의 합계 계산</span><span class="sxs-lookup"><span data-stu-id="a49c5-112">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="a49c5-113"><xref:System.Linq.Enumerable.Sum%2A> 연산자가 null만 있는 시퀀스 또는 빈 시퀀스의 0 대신 `null` (`Nothing` 의 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)])로 계산되는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a49c5-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a49c5-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a49c5-114">See Also</span></span>  
 [<span data-ttu-id="a49c5-115">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="a49c5-115">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
