---
title: Null 의미 체계
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 3c4daa5fd37158f1af31f33ba743a56cf76670d8
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="null-semantics"></a><span data-ttu-id="28ba3-102">Null 의미 체계</span><span class="sxs-lookup"><span data-stu-id="28ba3-102">Null Semantics</span></span>
<span data-ttu-id="28ba3-103">다음 표에서는 다양 한 부분에 대 한 링크를 제공는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 설명서 여기서 `null` (`Nothing` Visual basic에서) 문제에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="28ba3-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in Visual Basic) issues are discussed.</span></span>  
  
|<span data-ttu-id="28ba3-104">항목</span><span class="sxs-lookup"><span data-stu-id="28ba3-104">Topic</span></span>|<span data-ttu-id="28ba3-105">설명</span><span class="sxs-lookup"><span data-stu-id="28ba3-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="28ba3-106">SQL-CLR 형식 불일치</span><span class="sxs-lookup"><span data-stu-id="28ba3-106">SQL-CLR Type Mismatches</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)|<span data-ttu-id="28ba3-107">이 항목의 "Null 의미 체계" 섹션에는 3 SQL 부울 상태와 두 가지 상태 공용 언어 런타임 (CLR)에 대 한 설명은 <xref:System.Boolean>, 리터럴 `Nothing` (Visual Basic) 및 `null` (C#) 및 기타 유사한 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="28ba3-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` (Visual Basic) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="28ba3-108">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="28ba3-108">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)|<span data-ttu-id="28ba3-109">이 항목의 "Null 의미 체계" 단원에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 null을 의미론적으로 비교 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28ba3-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="28ba3-110">System.String 메서드</span><span class="sxs-lookup"><span data-stu-id="28ba3-110">System.String Methods</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|<span data-ttu-id="28ba3-111">이 항목의 ".NET과의 차이점" 단원에서는 문자열이 null인 것을 의미할 수도 있고 찾은 위치가 0인 것을 의미할 수도 있는 <xref:System.String.LastIndexOf%2A> 의 반환 값 0에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="28ba3-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="28ba3-112">숫자 시퀀스에서 값의 합계 계산</span><span class="sxs-lookup"><span data-stu-id="28ba3-112">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="28ba3-113">설명 방법을 <xref:System.Linq.Enumerable.Sum%2A> 연산자를 계산 하 고 `null` (`Nothing` Visual basic에서) null만 들어 있는 시퀀스 또는 빈 시퀀스에 대해 0이 아닌 합니다.</span><span class="sxs-lookup"><span data-stu-id="28ba3-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in Visual Basic) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28ba3-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28ba3-114">See Also</span></span>  
 [<span data-ttu-id="28ba3-115">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="28ba3-115">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
