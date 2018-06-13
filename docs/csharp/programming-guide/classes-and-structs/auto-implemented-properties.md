---
title: 자동으로 구현된 속성(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 756e235dacc3fcb2bf741d1d426e8dfcb53bf19b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33313802"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="398b7-102">자동으로 구현된 속성(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="398b7-102">Auto-Implemented Properties (C# Programming Guide)</span></span>
<span data-ttu-id="398b7-103">C# 3.0 이상에서는 속성 접근자에 추가적인 논리가 필요하지 않을 경우 자동 구현 속성을 통해 속성 선언이 더 간결해집니다.</span><span class="sxs-lookup"><span data-stu-id="398b7-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="398b7-104">이를 통해 클라이언트 코드에서 개체를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="398b7-104">They also enable client code to create objects.</span></span> <span data-ttu-id="398b7-105">다음 예제와 같이 속성을 선언할 때 컴파일러는 속성의 `get` 및 `set` 접근자를 통해서만 액세스할 수 있는 전용 익명 지원 필드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="398b7-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="398b7-106">예</span><span class="sxs-lookup"><span data-stu-id="398b7-106">Example</span></span>  
 <span data-ttu-id="398b7-107">다음 예제에서는 일부 자동 구현 속성이 있는 간단한 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="398b7-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/auto-implemented-properties_1.cs)]  
  
 <span data-ttu-id="398b7-108">C# 6 이상 버전에서는 필드와 유사하게 자동 구현 속성을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="398b7-108">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 <span data-ttu-id="398b7-109">앞의 예제에 표시된 클래스는 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="398b7-109">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="398b7-110">클라이언트 코드에서는 개체가 만들어진 후 개체의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="398b7-110">Client code can change the values in objects after they are created.</span></span> <span data-ttu-id="398b7-111">데이터 및 중요 동작(메서드)을 포함하는 복잡한 클래스에는 공용 속성을 포함해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="398b7-111">In complex classes that contain significant behavior (methods) as well as data, it is often necessary to have public properties.</span></span> <span data-ttu-id="398b7-112">그러나 값 집합(데이터)만 캡슐화하고 동작이 적거나 없는 작은 클래스나 구조체의 경우 set 접근자를 [private](../../../csharp/language-reference/keywords/private.md)로 선언하거나(소비자에 대한 변경 불가능) get 접근자만 선언하여(생성자를 제외한 모든 위치에서 변경 불가능) 개체를 변경 불가능으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="398b7-112">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../../csharp/language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="398b7-113">자세한 내용은 [방법: 자동으로 구현된 속성을 사용하여 간단한 클래스 구현](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="398b7-113">For more information, see [How to: Implement a Lightweight Class with Auto-Implemented Properties](../../../csharp/programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="398b7-114">특성은 자동 구현 속성에서 허용되지만, 소스 코드에서 액세스할 수 없으므로 지원 필드에서는 분명히 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="398b7-114">Attributes are permitted on auto-implemented properties but obviously not on the backing fields since those are not accessible from your source code.</span></span> <span data-ttu-id="398b7-115">속성의 지원 필드에서 특성을 사용해야 할 경우 일반 속성만 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="398b7-115">If you must use an attribute on the backing field of a property, just create a regular property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="398b7-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="398b7-116">See Also</span></span>  
 [<span data-ttu-id="398b7-117">속성</span><span class="sxs-lookup"><span data-stu-id="398b7-117">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [<span data-ttu-id="398b7-118">한정자</span><span class="sxs-lookup"><span data-stu-id="398b7-118">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
