---
title: "방법: 인터페이스 이벤트 구현(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
caps.latest.revision: 21
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
ms.openlocfilehash: 8f8460674aa59170cf75eb2fa93e9d232df07e5e
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-implement-interface-events-c-programming-guide"></a><span data-ttu-id="9f79c-102">방법: 인터페이스 이벤트 구현(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="9f79c-102">How to: Implement Interface Events (C# Programming Guide)</span></span>
<span data-ttu-id="9f79c-103">[인터페이스](../../../csharp/language-reference/keywords/interface.md)는 [이벤트](../../../csharp/language-reference/keywords/event.md)를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f79c-103">An [interface](../../../csharp/language-reference/keywords/interface.md) can declare an [event](../../../csharp/language-reference/keywords/event.md).</span></span> <span data-ttu-id="9f79c-104">다음 예제에서는 클래스에서 인터페이스 이벤트를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f79c-104">The following example shows how to implement interface events in a class.</span></span> <span data-ttu-id="9f79c-105">기본적인 규칙은 다른 모든 인터페이스 메서드나 속성을 구현할 때의 규칙과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9f79c-105">Basically the rules are the same as when you implement any interface method or property.</span></span>  
  
### <a name="to-implement-interface-events-in-a-class"></a><span data-ttu-id="9f79c-106">클래스에서 인터페이스 이벤트를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="9f79c-106">To implement interface events in a class</span></span>  
  
-   <span data-ttu-id="9f79c-107">클래스에서 이벤트를 선언한 다음 적절한 영역에서 이벤트를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="9f79c-107">Declare the event in your class and then invoke it in the appropriate areas.</span></span>  
  
    ```  
    namespace ImplementInterfaceEvents  
    {  
        public interface IDrawingObject  
        {  
            event EventHandler ShapeChanged;  
        }  
        public class MyEventArgs : EventArgs   
        {  
            // class members  
        }  
        public class Shape : IDrawingObject  
        {  
            public event EventHandler ShapeChanged;  
            void ChangeShape()  
            {  
                // Do something here before the event…  
  
                OnShapeChanged(new MyEventArgs(/*arguments*/));  
  
                // or do something here after the event.   
            }  
            protected virtual void OnShapeChanged(MyEventArgs e)  
            {  
                if(ShapeChanged != null)  
                {  
                   ShapeChanged(this, e);  
                }  
            }  
        }  
  
    }  
    ```  
  
## <a name="example"></a><span data-ttu-id="9f79c-108">예제</span><span class="sxs-lookup"><span data-stu-id="9f79c-108">Example</span></span>  
 <span data-ttu-id="9f79c-109">다음 예제에서는 클래스가 둘 이상의 인터페이스에서 상속을 받으며 각 인터페이스에는 이름이 같은 이벤트가 있는 드문 상황을 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f79c-109">The following example shows how to handle the less-common situation in which your class inherits from two or more interfaces and each interface has an event with the same name.</span></span> <span data-ttu-id="9f79c-110">이러한 상황에서는 이벤트 하나 이상에 대해 명시적 인터페이스 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f79c-110">In this situation, you must provide an explicit interface implementation for at least one of the events.</span></span> <span data-ttu-id="9f79c-111">이벤트에 대한 명시적 인터페이스 구현을 쓸 때는 `add` 및 `remove` 이벤트 접근자도 써야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f79c-111">When you write an explicit interface implementation for an event, you must also write the `add` and `remove` event accessors.</span></span> <span data-ttu-id="9f79c-112">일반적으로는 컴파일러가 이러한 접근자를 제공하지만 이 예제의 경우에는 컴파일러가 접근자를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f79c-112">Normally these are provided by the compiler, but in this case the compiler cannot provide them.</span></span>  
  
 <span data-ttu-id="9f79c-113">고유한 접근자를 제공하면 클래스에서 두 이벤트를 같은 이벤트로 표시할지 아니면 다른 이벤트로 표시할지를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f79c-113">By providing your own accessors, you can specify whether the two events are represented by the same event in your class, or by different events.</span></span> <span data-ttu-id="9f79c-114">예를 들어 인터페이스 사양에 따라 이벤트가 서로 다른 시간에 발생해야 하는 경우에는 각 이벤트를 클래스의 개별 구현과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f79c-114">For example, if the events should be raised at different times according to the interface specifications, you can associate each event with a separate implementation in your class.</span></span> <span data-ttu-id="9f79c-115">다음 예제에서는 구독자가 `IShape` 또는 `IDrawingObject`에 셰이프 참조를 캐스팅하여 수신할 `OnDraw` 이벤트를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f79c-115">In the following example, subscribers determine which `OnDraw` event they will receive by casting the shape reference to either an `IShape` or an `IDrawingObject`.</span></span>  
  
 <span data-ttu-id="9f79c-116">[!code-cs[csProgGuideEvents#10](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-implement-interface-events_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9f79c-116">[!code-cs[csProgGuideEvents#10](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-implement-interface-events_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f79c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f79c-117">See Also</span></span>  
 <span data-ttu-id="9f79c-118">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9f79c-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9f79c-119">[이벤트](../../../csharp/programming-guide/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="9f79c-119">[Events](../../../csharp/programming-guide/events/index.md) </span></span>  
 <span data-ttu-id="9f79c-120">[대리자](../../../csharp/programming-guide/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="9f79c-120">[Delegates](../../../csharp/programming-guide/delegates/index.md) </span></span>  
 <span data-ttu-id="9f79c-121">[명시적 인터페이스 구현](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md) </span><span class="sxs-lookup"><span data-stu-id="9f79c-121">[Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md) </span></span>  
 [<span data-ttu-id="9f79c-122">방법: 파생 클래스에서 기본 클래스 이벤트 발생</span><span class="sxs-lookup"><span data-stu-id="9f79c-122">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)

