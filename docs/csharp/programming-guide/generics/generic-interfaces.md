---
title: 제네릭 인터페이스(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic interfaces
- generics [C#], interfaces
ms.assetid: a8fa49a1-6e78-4a09-87e5-84a0b9f5ffbe
ms.openlocfilehash: 72f48aa1d70e6cf81b20adc547e2d418c4497256
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="generic-interfaces-c-programming-guide"></a><span data-ttu-id="a6a76-102">제네릭 인터페이스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="a6a76-102">Generic Interfaces (C# Programming Guide)</span></span>
<span data-ttu-id="a6a76-103">제네릭 컬렉션 클래스에 대한 인터페이스 또는 컬렉션의 항목을 나타내는 제네릭 클래스에 대한 인터페이스를 정의하는 것이 대개 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a76-103">It is often useful to define interfaces either for generic collection classes, or for the generic classes that represent items in the collection.</span></span> <span data-ttu-id="a6a76-104">값 형식에 대해 boxing 및 unboxing 연산을 하지 않으려면 제네릭 클래스에서 <xref:System.IComparable> 대신 <xref:System.IComparable%601>과 같은 제네릭 인터페이스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a76-104">The preference for generic classes is to use generic interfaces, such as <xref:System.IComparable%601> rather than <xref:System.IComparable>, in order to avoid boxing and unboxing operations on value types.</span></span> <span data-ttu-id="a6a76-105">.NET Framework 클래스 라이브러리에는 <xref:System.Collections.Generic> 네임스페이스의 컬렉션 클래스에 사용할 제네릭 인터페이스가 여러 개 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a76-105">The .NET Framework class library defines several generic interfaces for use with the collection classes in the <xref:System.Collections.Generic> namespace.</span></span>  
  
 <span data-ttu-id="a6a76-106">인터페이스를 형식 매개 변수에 대한 제약 조건으로 지정한 경우 이 인터페이스를 구현하는 형식만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a76-106">When an interface is specified as a constraint on a type parameter, only types that implement the interface can be used.</span></span> <span data-ttu-id="a6a76-107">다음 코드 예제는 `GenericList<T>` 클래스에서 파생되는 `SortedList<T>` 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a6a76-107">The following code example shows a `SortedList<T>` class that derives from the `GenericList<T>` class.</span></span> <span data-ttu-id="a6a76-108">자세한 내용은 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6a76-108">For more information, see [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md).</span></span> <span data-ttu-id="a6a76-109">`SortedList<T>`는 `where T : IComparable<T>` 제약 조건을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a76-109">`SortedList<T>` adds the constraint `where T : IComparable<T>`.</span></span> <span data-ttu-id="a6a76-110">이렇게 하면 `SortedList<T>`의 `BubbleSort` 메서드가 목록 요소에서 제네릭 <xref:System.IComparable%601.CompareTo%2A> 메서드를 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6a76-110">This enables the `BubbleSort` method in `SortedList<T>` to use the generic <xref:System.IComparable%601.CompareTo%2A> method on list elements.</span></span> <span data-ttu-id="a6a76-111">이 예제에서 목록 요소는 `IComparable<Person>`을 구현하는 단순 클래스인 `Person`입니다.</span><span class="sxs-lookup"><span data-stu-id="a6a76-111">In this example, list elements are a simple class, `Person`, that implements `IComparable<Person>`.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#29](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_1.cs)]  
  
 <span data-ttu-id="a6a76-112">단일 형식에 다음과 같이 여러 인터페이스를 제약 조건으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a76-112">Multiple interfaces can be specified as constraints on a single type, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#30](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_2.cs)]  
  
 <span data-ttu-id="a6a76-113">하나의 인터페이스는 다음과 같은 두 개 이상의 형식 매개 변수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a76-113">An interface can define more than one type parameter, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#31](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_3.cs)]  
  
 <span data-ttu-id="a6a76-114">클래스에 적용되는 상속 규칙은 인터페이스에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6a76-114">The rules of inheritance that apply to classes also apply to interfaces:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#32](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_4.cs)]  
  
 <span data-ttu-id="a6a76-115">제네릭 인터페이스에 반공변성(Contravariance)이 있는 경우, 즉 형식 매개 변수만 반환 값으로 사용하는 경우 제네릭 인터페이스는 제네릭이 아닌 인터페이스에서 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a76-115">Generic interfaces can inherit from non-generic interfaces if the generic interface is contra-variant, which means it only uses its type parameter as a return value.</span></span> <span data-ttu-id="a6a76-116">.NET Framework 클래스 라이브러리에서 <xref:System.Collections.Generic.IEnumerable%601>은 <xref:System.Collections.IEnumerable>에서 상속하는데, 이는 <xref:System.Collections.Generic.IEnumerable%601>이 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>의 반환 값과 <xref:System.Collections.Generic.IEnumerator%601.Current%2A> 속성 getter에 `T`만 사용하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a6a76-116">In the .NET Framework class library, <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable> because <xref:System.Collections.Generic.IEnumerable%601> only uses `T` in the return value of <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> and in the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property getter.</span></span>  
  
 <span data-ttu-id="a6a76-117">구체적인 클래스는 다음과 같이 폐쇄형으로 생성된 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a76-117">Concrete classes can implement closed constructed interfaces, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#33](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_5.cs)]  
  
 <span data-ttu-id="a6a76-118">클래스 매개 변수 목록이 다음과 같이 인터페이스에 필요한 모든 인수를 제공하는 경우에 한해 제네릭 클래스는 제네릭 인터페이스 또는 폐쇄형으로 생성된 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a76-118">Generic classes can implement generic interfaces or closed constructed interfaces as long as the class parameter list supplies all arguments required by the interface, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#34](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-interfaces_6.cs)]  
  
 <span data-ttu-id="a6a76-119">제네릭 클래스, 제네릭 구조체 또는 제네릭 인터페이스 내의 메서드에는 메서드 오버로드를 제어하는 규칙이 동일하게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6a76-119">The rules that control method overloading are the same for methods within generic classes, generic structs, or generic interfaces.</span></span> <span data-ttu-id="a6a76-120">자세한 내용은 [제네릭 메서드](../../../csharp/programming-guide/generics/generic-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6a76-120">For more information, see [Generic Methods](../../../csharp/programming-guide/generics/generic-methods.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6a76-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6a76-121">See Also</span></span>  
 [<span data-ttu-id="a6a76-122">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a6a76-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a6a76-123">제네릭 소개</span><span class="sxs-lookup"><span data-stu-id="a6a76-123">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [<span data-ttu-id="a6a76-124">interface</span><span class="sxs-lookup"><span data-stu-id="a6a76-124">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
 [<span data-ttu-id="a6a76-125">제네릭</span><span class="sxs-lookup"><span data-stu-id="a6a76-125">Generics</span></span>](~/docs/standard/generics/index.md)
