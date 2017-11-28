---
title: "System.String 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce307f14-87e6-4816-8694-8a4147f6b784
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3cfddba1bfa7bf7cefba917be0026b1c366f3513
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="systemstring-methods"></a><span data-ttu-id="a38d6-102">System.String 메서드</span><span class="sxs-lookup"><span data-stu-id="a38d6-102">System.String Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a38d6-103">에서는 다음 <xref:System.String> 메서드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a38d6-103"> does not support the following <xref:System.String> methods.</span></span>  
  
## <a name="unsupported-systemstring-methods-in-general"></a><span data-ttu-id="a38d6-104">일반적으로 지원되지 않는 System.String 메서드</span><span class="sxs-lookup"><span data-stu-id="a38d6-104">Unsupported System.String Methods in General</span></span>  
 <span data-ttu-id="a38d6-105">일반적으로 지원되지 않는 <xref:System.String> 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="a38d6-105">Unsupported <xref:System.String> methods in general:</span></span>  
  
-   <span data-ttu-id="a38d6-106">문화권 인식 오버 로드 (사용 하는 메서드는 `CultureInfo`  /  `StringComparison`  /  `IFormatProvider`).</span><span class="sxs-lookup"><span data-stu-id="a38d6-106">Culture-aware overloads (methods that take a `CultureInfo` / `StringComparison` / `IFormatProvider`).</span></span>  
  
-   <span data-ttu-id="a38d6-107">`char` 배열을 사용하거나 생성하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="a38d6-107">Methods that take or produce a `char` array.</span></span>  
  
## <a name="unsupported-systemstring-static-methods"></a><span data-ttu-id="a38d6-108">지원되지 않는 System.String 정적 메서드</span><span class="sxs-lookup"><span data-stu-id="a38d6-108">Unsupported System.String Static Methods</span></span>  
  
|<span data-ttu-id="a38d6-109">지원되지 않는 System.String 정적 메서드</span><span class="sxs-lookup"><span data-stu-id="a38d6-109">Unsupported System.String Static Methods</span></span>|  
|----------------------------------------------|  
|<xref:System.String.Copy%28System.String%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.String%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|  
  
## <a name="unsupported-systemstring-non-static-methods"></a><span data-ttu-id="a38d6-110">지원되지 않는 System.String 비정적 메서드</span><span class="sxs-lookup"><span data-stu-id="a38d6-110">Unsupported System.String Non-static Methods</span></span>  
  
|<span data-ttu-id="a38d6-111">지원되지 않는 System.String 비정적 메서드</span><span class="sxs-lookup"><span data-stu-id="a38d6-111">Unsupported System.String Non-static Methods</span></span>|  
|---------------------------------------------------|  
|<xref:System.String.IndexOfAny%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.Split%2A?displayProperty=nameWithType>|  
|<xref:System.String.ToCharArray?displayProperty=nameWithType>|  
|<xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimEnd%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimStart%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
  
## <a name="differences-from-net"></a><span data-ttu-id="a38d6-112">.NET과의 차이점</span><span class="sxs-lookup"><span data-stu-id="a38d6-112">Differences from .NET</span></span>  
  
-   <span data-ttu-id="a38d6-113">쿼리에서는 서버에 적용되는 SQL Server 데이터 정렬에 대해 설명하지 않으므로 기본적으로 문화권 구분 및 대/소문자를 구분하지 않는 비교를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a38d6-113">Queries do not account for SQL Server collations that might be in effect on the server, and therefore will provide culture-sensitive, case-insensitive comparisons by default.</span></span> <span data-ttu-id="a38d6-114">이 동작은 .NET Framework의 대/소문자를 구분하는 의미와 기본적으로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a38d6-114">This behavior differs from the default, case-sensitive semantics of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="a38d6-115">때 `LastIndexOf` 0 일은 문자열이 반환 `NULL` 또는 찾은 위치가 0입니다.</span><span class="sxs-lookup"><span data-stu-id="a38d6-115">When `LastIndexOf` returns 0, either the string is `NULL` or the found position is 0.</span></span>  
  
-   <span data-ttu-id="a38d6-116">연결 또는 고정 길이 문자열인 `CHAR`, `NCHAR`로부터 예기치 않은 결과가 반환될 수 있습니다. 왜냐하면 이러한 형식은 데이터베이스에서 안쪽 여백이 자동으로 적용되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a38d6-116">Unexpected results might be returned from concatenation or other operations on fixed-length strings (`CHAR`, `NCHAR`), because these types automatically have padding applied in the database.</span></span>  
  
-   <span data-ttu-id="a38d6-117">`Replace`, `ToLower`, `ToUpper`와 같은 여러 가지 메서드와 문자 인덱서는 `TEXT` 또는 `NTEXT` 열과 XML에 대한 유효한 변환을 갖지 않으므로 정상적으로 변환되는 경우에 `SqlExceptions`가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a38d6-117">Because many methods, such as `Replace`, `ToLower`, `ToUpper`, and the character indexer, have no valid translation for `TEXT` or `NTEXT` columns and XML, `SqlExceptions` occur if translated normally.</span></span> <span data-ttu-id="a38d6-118">이러한 동작은 이 형식을 허용하는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="a38d6-118">This behavior is considered acceptable for these types.</span></span> <span data-ttu-id="a38d6-119">그러나 모든 문자열 작업은 `VARCHAR`, `NVARCHAR`, `VARCHAR(max)` 및 `NVARCHAR(max)`에 대한 CLR(공용 언어 런타임) 의미와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a38d6-119">However, all string operations must match common language runtime (CLR) semantics for `VARCHAR`, `NVARCHAR`, `VARCHAR(max)`, and `NVARCHAR(max)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a38d6-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a38d6-120">See Also</span></span>  
 [<span data-ttu-id="a38d6-121">데이터 형식 및 함수</span><span class="sxs-lookup"><span data-stu-id="a38d6-121">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
