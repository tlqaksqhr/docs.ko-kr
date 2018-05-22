---
title: '방법: 읽기/쓰기 속성 선언 및 사용(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: d6a7083e1c0cf0dc5c076a69dee15fc39e234d53
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a><span data-ttu-id="4e52e-102">방법: 읽기/쓰기 속성 선언 및 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4e52e-102">How to: Declare and Use Read Write Properties (C# Programming Guide)</span></span>
<span data-ttu-id="4e52e-103">속성은 개체 데이터에 대한 액세스가 보호, 제어, 확인되지 않을 위험 없이 공용 데이터 멤버의 편리함을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-103">Properties provide the convenience of public data members without the risks that come with unprotected, uncontrolled, and unverified access to an object's data.</span></span> <span data-ttu-id="4e52e-104">이를 위해 기본 데이터 멤버의 값을 할당하고 검색하는 특수 메서드인 *접근자*가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-104">This is accomplished through *accessors*: special methods that assign and retrieve values from the underlying data member.</span></span> <span data-ttu-id="4e52e-105">[set](../../../csharp/language-reference/keywords/set.md) 접근자를 통해 데이터 멤버를 할당할 수 있으며, [get](../../../csharp/language-reference/keywords/get.md) 접근자는 데이터 멤버 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-105">The [set](../../../csharp/language-reference/keywords/set.md) accessor enables data members to be assigned, and the [get](../../../csharp/language-reference/keywords/get.md) accessor retrieves data member values.</span></span>  
  
 <span data-ttu-id="4e52e-106">이 샘플에서는 `Name`(string) 및 `Age`(int)의 두 속성이 있는 `Person` 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-106">This sample shows a `Person` class that has two properties: `Name` (string) and `Age` (int).</span></span> <span data-ttu-id="4e52e-107">두 속성 모두 `get` 및 `set` 접근자를 제공하므로 읽기/쓰기 속성으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-107">Both properties provide `get` and `set` accessors, so they are considered read/write properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e52e-108">예</span><span class="sxs-lookup"><span data-stu-id="4e52e-108">Example</span></span>  
 [!code-csharp[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="4e52e-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="4e52e-109">Robust Programming</span></span>  
 <span data-ttu-id="4e52e-110">이전 예제에서 `Name` 및 `Age` 속성은 [public](../../../csharp/language-reference/keywords/public.md)이며, `get` 및 `set` 접근자를 모두 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-110">In the previous example, the `Name` and `Age` properties are [public](../../../csharp/language-reference/keywords/public.md) and include both a `get` and a `set` accessor.</span></span> <span data-ttu-id="4e52e-111">이 경우 모든 개체가 이러한 속성을 읽고 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-111">This allows any object to read and write these properties.</span></span> <span data-ttu-id="4e52e-112">그러나 때로는 접근자 중 하나를 제외하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-112">It is sometimes desirable, however, to exclude one of the accessors.</span></span> <span data-ttu-id="4e52e-113">예를 들어 `set` 접근자를 생략하면 속성은 읽기 전용이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-113">Omitting the `set` accessor, for example, makes the property read-only:</span></span>  
  
 [!code-csharp[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]  
  
 <span data-ttu-id="4e52e-114">또는 하나의 접근자를 공개적으로 노출하고 다른 접근자를 private 또는 protected로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-114">Alternatively, you can expose one accessor publicly but make the other private or protected.</span></span> <span data-ttu-id="4e52e-115">자세한 내용은 [비대칭 접근자 접근성](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e52e-115">For more information, see [Asymmetric Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
 <span data-ttu-id="4e52e-116">속성이 선언되면 클래스의 필드처럼 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-116">Once the properties are declared, they can be used as if they were fields of the class.</span></span> <span data-ttu-id="4e52e-117">이 경우 다음 문과 같이 속성의 값을 가져오고 설정할 때 자연스러운 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-117">This allows for a very natural syntax when both getting and setting the value of a property, as in the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]  
  
 <span data-ttu-id="4e52e-118">속성 `set` 메서드에 특수 `value` 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-118">Note that in a property `set` method a special `value` variable is available.</span></span> <span data-ttu-id="4e52e-119">이 변수에는 사용자가 지정한 값이 포함됩니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-119">This variable contains the value that the user specified, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]  
  
 <span data-ttu-id="4e52e-120">`Person` 개체의 `Age` 속성을 증가하기 위한 정리된 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-120">Notice the clean syntax for incrementing the `Age` property on a `Person` object:</span></span>  
  
 [!code-csharp[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]  
  
 <span data-ttu-id="4e52e-121">개별 `set` 및 `get` 메서드를 사용하여 속성을 모델링한 경우 동등한 코드가 다음과 같이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-121">If separate `set` and `get` methods were used to model properties, the equivalent code might look like this:</span></span>  
  
```csharp  
person.SetAge(person.GetAge() + 1);   
```  
  
 <span data-ttu-id="4e52e-122">다음 예제에서는 `ToString` 메서드가 재정의되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-122">The `ToString` method is overridden in this example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]  
  
 <span data-ttu-id="4e52e-123">`ToString`이 프로그램에서 명시적으로 사용되지 않고</span><span class="sxs-lookup"><span data-stu-id="4e52e-123">Notice that `ToString` is not explicitly used in the program.</span></span> <span data-ttu-id="4e52e-124">기본적으로 `WriteLine` 호출에 의해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e52e-124">It is invoked by default by the `WriteLine` calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e52e-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e52e-125">See Also</span></span>  
 [<span data-ttu-id="4e52e-126">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4e52e-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4e52e-127">속성</span><span class="sxs-lookup"><span data-stu-id="4e52e-127">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [<span data-ttu-id="4e52e-128">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="4e52e-128">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
