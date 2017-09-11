---
title: "방법: 파생 클래스에서 기본 클래스 이벤트 발생(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 13501f51a1e99eb6fb792a1c6abe5c7029cc020a
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a><span data-ttu-id="d5340-102">방법: 파생 클래스에서 기본 클래스 이벤트 발생(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="d5340-102">How to: Raise Base Class Events in Derived Classes (C# Programming Guide)</span></span>
<span data-ttu-id="d5340-103">다음 간단한 예제에서는 파생 클래스에서도 발생할 수 있도록 기본 클래스에서 이벤트를 선언하는 표준 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5340-103">The following simple example shows the standard way to declare events in a base class so that they can also be raised from derived classes.</span></span> <span data-ttu-id="d5340-104">이 패턴은 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 클래스 라이브러리의 Windows Forms 클래스에서 광범위하게 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5340-104">This pattern is used extensively in Windows Forms classes in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library.</span></span>  
  
 <span data-ttu-id="d5340-105">다른 클래스의 기본 클래스로 사용할 수 있는 클래스를 만드는 경우 이벤트가 해당 이벤트를 선언한 클래스 내에서만 호출할 수 있는 특수 유형의 대리자라는 사실을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5340-105">When you create a class that can be used as a base class for other classes, you should consider the fact that events are a special type of delegate that can only be invoked from within the class that declared them.</span></span> <span data-ttu-id="d5340-106">파생 클래스는 기본 클래스 내에서 선언된 이벤트를 직접 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5340-106">Derived classes cannot directly invoke events that are declared within the base class.</span></span> <span data-ttu-id="d5340-107">기본 클래스에서만 발생할 수 있는 이벤트를 원하는 경우도 있지만 대부분의 경우 파생 클래스가 기본 클래스 이벤트를 호출할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5340-107">Although sometimes you may want an event that can only be raised by the base class, most of the time, you should enable the derived class to invoke base class events.</span></span> <span data-ttu-id="d5340-108">이렇게 하려면 이벤트를 래핑하는 기본 클래스에서 보호된 호출 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d5340-108">To do this, you can create a protected invoking method in the base class that wraps the event.</span></span> <span data-ttu-id="d5340-109">이 호출 메서드를 호출하거나 재정의하면 파생 클래스에서 간접적으로 이벤트를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5340-109">By calling or overriding this invoking method, derived classes can invoke the event indirectly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5340-110">기본 클래스에서 가상 이벤트를 선언하지 말고 파생 클래스에서 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d5340-110">Do not declare virtual events in a base class and override them in a derived class.</span></span> <span data-ttu-id="d5340-111">C# 컴파일러는 이러한 이벤트를 올바르게 처리하지 않으며, 파생 이벤트의 구독자가 실제로 기본 클래스 이벤트를 구독할지 여부를 예측할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5340-111">The C# compiler does not handle these correctly and it is unpredictable whether a subscriber to the derived event will actually be subscribing to the base class event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5340-112">예제</span><span class="sxs-lookup"><span data-stu-id="d5340-112">Example</span></span>  
 <span data-ttu-id="d5340-113">[!code-cs[csProgGuideEvents#1](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-raise-base-class-events-in-derived-classes_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d5340-113">[!code-cs[csProgGuideEvents#1](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-raise-base-class-events-in-derived-classes_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5340-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5340-114">See Also</span></span>  
 <span data-ttu-id="d5340-115">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5340-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d5340-116">[이벤트](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5340-116">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 <span data-ttu-id="d5340-117">[대리자](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="d5340-117">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="d5340-118">[액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="d5340-118">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 [<span data-ttu-id="d5340-119">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="d5340-119">Creating Event Handlers in Windows Forms</span></span>](https://msdn.microsoft.com/library/dacysss4.aspx)

