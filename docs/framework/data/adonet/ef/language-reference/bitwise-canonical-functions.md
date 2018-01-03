---
title: "비트 정식 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 993868ca-16e3-47b6-9915-c29cd63b0a21
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a4311b610859b36f1587e5e3f85e2a5f06503e1d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bitwise-canonical-functions"></a><span data-ttu-id="5c4a3-102">비트 정식 함수</span><span class="sxs-lookup"><span data-stu-id="5c4a3-102">Bitwise Canonical Functions</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="5c4a3-103">에는 비트 정식 함수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c4a3-103"> includes bitwise canonical functions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c4a3-104">설명</span><span class="sxs-lookup"><span data-stu-id="5c4a3-104">Remarks</span></span>  
 <span data-ttu-id="5c4a3-105">다음 표에서는 비트 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 정식 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c4a3-105">The following table shows the bitwise [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span> <span data-ttu-id="5c4a3-106">이러한 함수는 `Null`이 입력되면 `Null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5c4a3-106">These functions will return `Null` if `Null` input is provided.</span></span> <span data-ttu-id="5c4a3-107">함수의 반환 형식은 인수 형식과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5c4a3-107">The return type of the functions is the same as the argument type(s).</span></span> <span data-ttu-id="5c4a3-108">함수가 둘 이상의 인수를 사용하는 경우 인수는 같은 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c4a3-108">Arguments must be of the same type, if the function takes more than one argument.</span></span> <span data-ttu-id="5c4a3-109">서로 다른 형식에서 비트 작업을 수행 하려면 명시적으로 같은 형식으로 캐스팅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c4a3-109">To perform bitwise operations across different types, you need to cast to the same type explicitly.</span></span>  
  
|<span data-ttu-id="5c4a3-110">함수</span><span class="sxs-lookup"><span data-stu-id="5c4a3-110">Function</span></span>|<span data-ttu-id="5c4a3-111">설명</span><span class="sxs-lookup"><span data-stu-id="5c4a3-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="5c4a3-112">`BitWiseAnd (` `value1` `,`  `value2` `)`</span><span class="sxs-lookup"><span data-stu-id="5c4a3-112">`BitWiseAnd (` `value1` `,`  `value2` `)`</span></span>|<span data-ttu-id="5c4a3-113">`value1` 및 `value2`의 비트 결합을 `value1` 및 `value2`의 형식으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5c4a3-113">Returns the bitwise conjunction of `value1` and `value2` as the type of `value1` and `value2`.</span></span><br /><br /> <span data-ttu-id="5c4a3-114">**인수**</span><span class="sxs-lookup"><span data-stu-id="5c4a3-114">**Arguments**</span></span><br /><br /> <span data-ttu-id="5c4a3-115">A `Byte`, `Int16`, `Int32`, 및 `Int64`합니다.</span><span class="sxs-lookup"><span data-stu-id="5c4a3-115">A `Byte`, `Int16`, `Int32`, and `Int64`.</span></span><br /><br /> <span data-ttu-id="5c4a3-116">**예제**</span><span class="sxs-lookup"><span data-stu-id="5c4a3-116">**Example**</span></span><br /><br /> `-- The following example returns 1.`<br /><br /> `BitWiseAnd(1,3)`|  
|<span data-ttu-id="5c4a3-117">`BitWiseNot (` `value` `)`</span><span class="sxs-lookup"><span data-stu-id="5c4a3-117">`BitWiseNot (` `value` `)`</span></span>|<span data-ttu-id="5c4a3-118">`value`의 비트 부정을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5c4a3-118">Returns the bitwise negation of `value`.</span></span><br /><br /> <span data-ttu-id="5c4a3-119">**인수**</span><span class="sxs-lookup"><span data-stu-id="5c4a3-119">**Arguments**</span></span><br /><br /> <span data-ttu-id="5c4a3-120">A `Byte`, `Int16`, `Int32`, 및 `Int64`합니다.</span><span class="sxs-lookup"><span data-stu-id="5c4a3-120">A `Byte`, `Int16`, `Int32`, and `Int64`.</span></span><br /><br /> <span data-ttu-id="5c4a3-121">**예제**</span><span class="sxs-lookup"><span data-stu-id="5c4a3-121">**Example**</span></span><br /><br /> `-- The following example returns -4.`<br /><br /> `BitWiseNot(3)`|  
|<span data-ttu-id="5c4a3-122">`BitWiseOr (` `value1` `,`  `value2` `)`</span><span class="sxs-lookup"><span data-stu-id="5c4a3-122">`BitWiseOr (` `value1` `,`  `value2` `)`</span></span>|<span data-ttu-id="5c4a3-123">`value1` 및 `value2`의 비트 분리를 `value1` 및 `value2`의 형식으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5c4a3-123">Returns the bitwise disjunction of `value1` and `value2` as the type of `value1` and `value2`.</span></span><br /><br /> <span data-ttu-id="5c4a3-124">**인수**</span><span class="sxs-lookup"><span data-stu-id="5c4a3-124">**Arguments**</span></span><br /><br /> <span data-ttu-id="5c4a3-125">`Byte`, `Int16`, `Int32` 및 `Int64`입니다.</span><span class="sxs-lookup"><span data-stu-id="5c4a3-125">A `Byte`, `Int16`, `Int32` and `Int64`.</span></span><br /><br /> <span data-ttu-id="5c4a3-126">**예제**</span><span class="sxs-lookup"><span data-stu-id="5c4a3-126">**Example**</span></span><br /><br /> `-- The following example returns 3.`<br /><br /> `BitWiseOr(1,3)`|  
|<span data-ttu-id="5c4a3-127">`BitWiseXor (` `value1` `,`  `value2` `)`</span><span class="sxs-lookup"><span data-stu-id="5c4a3-127">`BitWiseXor (` `value1` `,`  `value2` `)`</span></span>|<span data-ttu-id="5c4a3-128">`value1` 및 `value2`의 배타적 비트 분리를 `value1` 및 `value2`의 형식으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5c4a3-128">Returns the bitwise exclusive disjunction of `value1` and `value2` as the type of `value1` and `value2`.</span></span><br /><br /> <span data-ttu-id="5c4a3-129">**인수**</span><span class="sxs-lookup"><span data-stu-id="5c4a3-129">**Arguments**</span></span><br /><br /> <span data-ttu-id="5c4a3-130">`Byte`, `Int16`, `Int32` 및 `Int64`입니다.</span><span class="sxs-lookup"><span data-stu-id="5c4a3-130">A `Byte`, `Int16`, `Int32` and `Int64`.</span></span><br /><br /> <span data-ttu-id="5c4a3-131">**예제**</span><span class="sxs-lookup"><span data-stu-id="5c4a3-131">**Example**</span></span><br /><br /> `-- The following example returns 2.`<br /><br /> `BitWiseXor (1,3)`|  
  
## <a name="see-also"></a><span data-ttu-id="5c4a3-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c4a3-132">See Also</span></span>  
 [<span data-ttu-id="5c4a3-133">정식 함수</span><span class="sxs-lookup"><span data-stu-id="5c4a3-133">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
