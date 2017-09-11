---
title: "중첩 그룹 만들기"
description: "중첩 그룹을 만드는 방법입니다."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 361ac1f224c6eef292fcf8434c7e465c9448b19c
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="create-a-nested-group"></a><span data-ttu-id="abf1f-104">중첩 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="abf1f-104">Create a nested group</span></span>

<span data-ttu-id="abf1f-105">다음 예제에서는 LINQ 쿼리 식에서 중첩 그룹을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abf1f-105">The following example shows how to create nested groups in a LINQ query expression.</span></span> <span data-ttu-id="abf1f-106">학년 또는 성적 수준에 따라 만들어진 각 그룹은 개인의 이름에 따라 하위 그룹으로 추가로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="abf1f-106">Each group that is created according to student year or grade level is then further subdivided into groups based on the individuals' names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="abf1f-107">예제</span><span class="sxs-lookup"><span data-stu-id="abf1f-107">Example</span></span>

 > [!NOTE]
 > <span data-ttu-id="abf1f-108">이 예제에는 [개체의 컬렉션 쿼리](query-a-collection-of-objects.md)에서 샘플 코드에 정의된 개체에 대한 참조가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="abf1f-108">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span> 

 <span data-ttu-id="abf1f-109">[!code-cs[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="abf1f-109">[!code-cs[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]</span></span>  
  
 <span data-ttu-id="abf1f-110">중첩 그룹의 내부 요소를 반복하려면 세 개의 중첩 `foreach` 루프가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="abf1f-110">Note that three nested `foreach` loops are required to iterate over the inner elements of a nested group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf1f-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abf1f-111">See also</span></span>  
 [<span data-ttu-id="abf1f-112">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="abf1f-112">LINQ Query Expressions</span></span>](index.md)

