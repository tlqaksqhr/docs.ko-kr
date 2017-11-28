---
title: "중첩 그룹 만들기"
description: "중첩 그룹을 만드는 방법입니다."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: 232aa46d975d7c338bbc776e3867f2e566601fde
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2017
---
# <a name="create-a-nested-group"></a><span data-ttu-id="6c05a-104">중첩 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="6c05a-104">Create a nested group</span></span>

<span data-ttu-id="6c05a-105">다음 예제에서는 LINQ 쿼리 식에서 중첩 그룹을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c05a-105">The following example shows how to create nested groups in a LINQ query expression.</span></span> <span data-ttu-id="6c05a-106">학년 또는 성적 수준에 따라 만들어진 각 그룹은 개인의 이름에 따라 하위 그룹으로 추가로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c05a-106">Each group that is created according to student year or grade level is then further subdivided into groups based on the individuals' names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c05a-107">예제</span><span class="sxs-lookup"><span data-stu-id="6c05a-107">Example</span></span>

 > [!NOTE]
 > <span data-ttu-id="6c05a-108">이 예제에는 [개체의 컬렉션 쿼리](query-a-collection-of-objects.md)에서 샘플 코드에 정의된 개체에 대한 참조가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c05a-108">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span> 

 [!code-csharp[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]  
  
 <span data-ttu-id="6c05a-109">중첩 그룹의 내부 요소를 반복하려면 세 개의 중첩 `foreach` 루프가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6c05a-109">Note that three nested `foreach` loops are required to iterate over the inner elements of a nested group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c05a-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c05a-110">See also</span></span>  
 [<span data-ttu-id="6c05a-111">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="6c05a-111">LINQ Query Expressions</span></span>](index.md)
