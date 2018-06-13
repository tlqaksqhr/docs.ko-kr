---
title: 시퀀스 연산자
ms.date: 03/30/2017
ms.assetid: 4d332d32-3806-4451-b7af-25af269194ae
ms.openlocfilehash: 01807e48c06bce1d451961bb6204d1f8e49d53f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33360289"
---
# <a name="sequence-operators"></a><span data-ttu-id="3ca8c-102">시퀀스 연산자</span><span class="sxs-lookup"><span data-stu-id="3ca8c-102">Sequence Operators</span></span>
<span data-ttu-id="3ca8c-103">일반적으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 다음과 같은 하나 이상의 품질을 갖는 시퀀스 연산자를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca8c-103">Generally speaking, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not support sequence operators that have one or more of the following qualities:</span></span>  
  
-   <span data-ttu-id="3ca8c-104">인덱스 매개 변수로 람다를 사용하는 연산자</span><span class="sxs-lookup"><span data-stu-id="3ca8c-104">Take a lambda with an index parameter.</span></span>  
  
-   <span data-ttu-id="3ca8c-105"><xref:System.Linq.Queryable.TakeWhile%2A>과 같이 연속적인 행의 속성을 사용하는 시퀀스 연산자</span><span class="sxs-lookup"><span data-stu-id="3ca8c-105">Rely on the properties of sequential rows, such as <xref:System.Linq.Queryable.TakeWhile%2A>.</span></span>  
  
-   <span data-ttu-id="3ca8c-106"><xref:System.Collections.Generic.IComparer%601>과 같이 임의의 CLR 구현을 사용하는 연산자</span><span class="sxs-lookup"><span data-stu-id="3ca8c-106">Rely on an arbitrary CLR implementation, such as <xref:System.Collections.Generic.IComparer%601>.</span></span>  
  
|<span data-ttu-id="3ca8c-107">지원되지 않는 예제</span><span class="sxs-lookup"><span data-stu-id="3ca8c-107">Examples of Unsupported</span></span>|  
|-----------------------------|  
|<xref:System.Linq.Enumerable.Where%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Boolean%7D%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.TakeWhile%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Boolean%7D%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.TakeWhile%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Boolean%7D%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.SkipWhile%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Boolean%7D%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.SkipWhile%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2CSystem.Int32%2CSystem.Boolean%7D%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.GroupBy%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%601%7D%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.GroupBy%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2CSystem.Collections.Generic.IEnumerable%7B%60%602%7D%2C%60%603%7D%2CSystem.Collections.Generic.IEqualityComparer%7B%60%601%7D%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.Reverse%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.DefaultIfEmpty%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2C%60%600%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.ElementAt%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.ElementAtOrDefault%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.Range%28System.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.Repeat%60%601%28%60%600%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.Contains%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2C%60%600%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.Aggregate%60%601%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%600%2C%60%600%7D%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.Aggregate%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2C%60%601%2CSystem.Func%7B%60%601%2C%60%600%2C%60%601%7D%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.Aggregate%60%603%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2C%60%601%2CSystem.Func%7B%60%601%2C%60%600%2C%60%601%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%29?displayProperty=nameWithType>|  
|<xref:System.Linq.Enumerable.SequenceEqual%2A?displayProperty=nameWithType>|  
  
## <a name="differences-from-net"></a><span data-ttu-id="3ca8c-108">.NET과의 차이점</span><span class="sxs-lookup"><span data-stu-id="3ca8c-108">Differences from .NET</span></span>  
 <span data-ttu-id="3ca8c-109">`Average`에 대해 지원되는 모든 시퀀스 연산자는 CLR(공용 언어 런타임) 예외에서 예상대로 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca8c-109">All supported sequence operators work as expected in the common language runtime (CLR) except for `Average`.</span></span> <span data-ttu-id="3ca8c-110">CLR에서 `Average`가 항상 `Average` 또는 <xref:System.Double>을 반환하는 것에 반해 <xref:System.Decimal>에서는 평균화하는 형식과 동일한 형식의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3ca8c-110">`Average` returns a value of the same type as the type being averaged, whereas in the CLR `Average` always returns either a <xref:System.Double> or a <xref:System.Decimal>.</span></span> <span data-ttu-id="3ca8c-111">소스 인수를 명시적으로 double/decimal로 캐스팅하거나 선택기를 double/decimal로 캐스팅하면 결과 SQL에서는 이러한 변환을 갖게 되고 예상한대로 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3ca8c-111">If the source argument is explicitly cast to double / decimal or the selector casts to double / decimal, the resulting SQL will also have such a conversion and the result will be as expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ca8c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ca8c-112">See Also</span></span>  
 [<span data-ttu-id="3ca8c-113">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="3ca8c-113">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
