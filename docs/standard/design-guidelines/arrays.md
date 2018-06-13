---
title: 배열
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], arrays
- arrays [.NET Framework], usage guidelines
- empty arrays
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2945ead7c22b759ce88f6585e2254e9bc540a7ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570405"
---
# <a name="arrays"></a><span data-ttu-id="28615-102">배열</span><span class="sxs-lookup"><span data-stu-id="28615-102">Arrays</span></span>
<span data-ttu-id="28615-103">**✓ 않습니다** 공용 Api에서 배열을 통해 컬렉션을 사용 하는 것을 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="28615-103">**✓ DO** prefer using collections over arrays in public APIs.</span></span> <span data-ttu-id="28615-104">[컬렉션](../../../docs/standard/design-guidelines/guidelines-for-collections.md) 섹션에서는 컬렉션 및 배열 중 하나를 선택 하는 방법에 대 한 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="28615-104">The [Collections](../../../docs/standard/design-guidelines/guidelines-for-collections.md) section provides details about how to choose between collections and arrays.</span></span>  
  
 <span data-ttu-id="28615-105">**X 하지 않으면** 읽기 전용 배열 필드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="28615-105">**X DO NOT** use read-only array fields.</span></span> <span data-ttu-id="28615-106">필드 자체가 읽기 전용 이므로 변경할 수 없으며, 하지만 배열의 요소를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28615-106">The field itself is read-only and can't be changed, but elements in the array can be changed.</span></span>  
  
 <span data-ttu-id="28615-107">**✓ 고려** 다차원 배열 대신 가변된 배열을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="28615-107">**✓ CONSIDER** using jagged arrays instead of multidimensional arrays.</span></span>  
  
 <span data-ttu-id="28615-108">가변된 배열에는 또한 배열 요소가 있는 배열이입니다.</span><span class="sxs-lookup"><span data-stu-id="28615-108">A jagged array is an array with elements that are also arrays.</span></span> <span data-ttu-id="28615-109">다차원 배열에 비해 일부 (예: 스파스 행렬) 데이터 집합에 대 한 절약할 공간 앞에 다양 한 크기의 요소를 구성 하는 배열의 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28615-109">The arrays that make up the elements can be of different sizes, leading to less wasted space for some sets of data (e.g., sparse matrix) compared to multidimensional arrays.</span></span> <span data-ttu-id="28615-110">또한 CLR 일부 시나리오에서는 런타임 성능이 향상를 나타낼 수 있도록 가변된 배열에서 인덱스 작업을 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="28615-110">Furthermore, the CLR optimizes index operations on jagged arrays, so they might exhibit better runtime performance in some scenarios.</span></span>  
  
 <span data-ttu-id="28615-111">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="28615-111">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="28615-112">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="28615-112">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28615-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28615-113">See Also</span></span>  
 <xref:System.Array>  
 [<span data-ttu-id="28615-114">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="28615-114">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="28615-115">사용 지침</span><span class="sxs-lookup"><span data-stu-id="28615-115">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
