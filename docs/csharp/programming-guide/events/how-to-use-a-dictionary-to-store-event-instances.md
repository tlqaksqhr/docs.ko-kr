---
title: "방법: 사전을 사용하여 이벤트 인스턴스 저장(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0304f04233151d35c8ee18fe09feac91fbd0879b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="ae410-102">방법: 사전을 사용하여 이벤트 인스턴스 저장(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="ae410-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="ae410-103">`accessor-declarations`는 각 이벤트에 대한 필드를 할당하지 않고 사전을 통해 이벤트 인스턴스를 저장하여 많은 이벤트를 공개하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae410-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="ae410-104">이 기능은 많은 이벤트가 있지만 대부분의 이벤트가 구현되지 않을 것으로 예상하는 경우에만 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae410-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae410-105">예제</span><span class="sxs-lookup"><span data-stu-id="ae410-105">Example</span></span>  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ae410-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae410-106">See Also</span></span>  
 [<span data-ttu-id="ae410-107">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ae410-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ae410-108">이벤트</span><span class="sxs-lookup"><span data-stu-id="ae410-108">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="ae410-109">대리자</span><span class="sxs-lookup"><span data-stu-id="ae410-109">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
