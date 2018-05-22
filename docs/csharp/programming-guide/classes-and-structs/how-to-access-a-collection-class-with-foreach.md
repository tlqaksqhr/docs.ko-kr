---
title: '방법: foreach를 사용하여 컬렉션 클래스 액세스(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- collection classes [C#], foreach statement
ms.assetid: a6b9cf5c-6c8d-4223-b12c-288949434493
ms.openlocfilehash: b02b9f4508984e3248cfd8e0cde0c994e1b871ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-a-collection-class-with-foreach-c-programming-guide"></a><span data-ttu-id="3072e-102">방법: foreach를 사용하여 컬렉션 클래스 액세스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="3072e-102">How to: Access a Collection Class with foreach (C# Programming Guide)</span></span>
<span data-ttu-id="3072e-103">다음 코드 예제에서는 [foreach](../../../csharp/language-reference/keywords/foreach-in.md)와 함께 사용할 수 있는 제네릭이 아닌 컬렉션 클래스를 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3072e-103">The following code example illustrates how to write a non-generic collection class that can be used with [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span></span> <span data-ttu-id="3072e-104">예제에서는 문자열 토크나이저 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3072e-104">The example defines a string tokenizer class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3072e-105">이 예제는 제네릭 컬렉션 클래스를 사용할 수 없는 경우에만 권장되는 방식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3072e-105">This example represents recommended practice only when you cannot use a generic collection class.</span></span> <span data-ttu-id="3072e-106"><xref:System.Collections.Generic.IEnumerable%601>을 지원하는 형식이 안전한 제네릭 컬렉션 클래스를 구현하는 방법의 예는 [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3072e-106">For an example of how to implement a type-safe generic collection class that supports <xref:System.Collections.Generic.IEnumerable%601>, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
 <span data-ttu-id="3072e-107">예제에서 다음 코드 세그먼트는 `Tokens` 클래스를 사용하여 "This is a sample sentence."라는 문장을</span><span class="sxs-lookup"><span data-stu-id="3072e-107">In the example, the following code segment uses the `Tokens` class to break the sentence "This is a sample sentence."</span></span> <span data-ttu-id="3072e-108">' ' 및 '-' 구분 기호로 토큰으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="3072e-108">into tokens by using ' ' and '-' as separators.</span></span> <span data-ttu-id="3072e-109">그런 다음 코드에서 `foreach` 문을 사용하여 해당 토큰을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="3072e-109">The code then displays those tokens by using a `foreach` statement.</span></span>  
  
 [!code-csharp[csProgGuideCollections#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="3072e-110">예</span><span class="sxs-lookup"><span data-stu-id="3072e-110">Example</span></span>  
 <span data-ttu-id="3072e-111">내부적으로 `Tokens` 클래스는 배열을 사용하여 토큰을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3072e-111">Internally, the `Tokens` class uses an array to store the tokens.</span></span> <span data-ttu-id="3072e-112">배열은 <xref:System.Collections.IEnumerator> 및 <xref:System.Collections.IEnumerable>을 구현하기 때문에 이 코드 예제에서는 `Tokens` 클래스에서 메서드를 정의하는 대신 배열의 열거형 메서드(<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A>, <xref:System.Collections.IEnumerator.Current%2A>)가 사용될 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="3072e-112">Because arrays implement <xref:System.Collections.IEnumerator> and <xref:System.Collections.IEnumerable>, the code example could have used the array's enumeration methods (<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A>, and <xref:System.Collections.IEnumerator.Current%2A>) instead of defining them in the `Tokens` class.</span></span> <span data-ttu-id="3072e-113">메서드 정의는 메서드가 정의된 방식과 각 메서드의 기능을 설명하기 위해 예제에 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3072e-113">The method definitions are included in the example to clarify how they are defined and what each does.</span></span>  
  
 [!code-csharp[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_2.cs)]  
  
 <span data-ttu-id="3072e-114">C#에서는 컬렉션 클래스가 `foreach`와의 호환을 위해 <xref:System.Collections.IEnumerable> 및 <xref:System.Collections.IEnumerator>를 구현할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3072e-114">In C#, it is not necessary for a collection class to implement <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> to be compatible with `foreach`.</span></span> <span data-ttu-id="3072e-115">필수 요소인 <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A>, <xref:System.Collections.IEnumerator.Current%2A> 멤버가 클래스에 있기만 하면 `foreach`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3072e-115">If the class has the required <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A>, and <xref:System.Collections.IEnumerator.Current%2A> members, it will work with `foreach`.</span></span> <span data-ttu-id="3072e-116">인터페이스를 생략하면 `Current`의 반환 형식을 <xref:System.Object>보다 더 구체적으로 정의할 수 있는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3072e-116">Omitting the interfaces has the advantage of enabling you to define a return type for `Current` that is more specific than <xref:System.Object>.</span></span> <span data-ttu-id="3072e-117">이 경우 형식 안전성이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="3072e-117">This provides type safety.</span></span>  
  
 <span data-ttu-id="3072e-118">예를 들어 앞의 예제에서 다음 줄을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3072e-118">For example, change the following lines in the previous example.</span></span>  
  
```csharp  
// Change the Tokens class so that it no longer implements IEnumerable.  
public class Tokens  
{  
    // . . .  
  
    // Change the return type for the GetEnumerator method.  
    public TokenEnumerator GetEnumerator()  
    {   }  
  
    // Change TokenEnumerator so that it no longer implements IEnumerator.  
    public class TokenEnumerator  
    {  
        // . . .  
  
        // Change the return type of method Current to string.  
        public string Current  
        {   }  
    }  
 }  
```  
  
 <span data-ttu-id="3072e-119">`Current`는 문자열을 반환하기 때문에 컴파일러가 다음 코드와 같이 `foreach` 문에서 호환되지 않는 형식이 사용된 경우를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3072e-119">Because `Current` returns a string, the compiler can detect when an incompatible type is used in a `foreach` statement, as shown in the following code.</span></span>  
  
```csharp  
// Error: Cannot convert type string to int.  
foreach (int item in f)    
```  
  
 <span data-ttu-id="3072e-120"><xref:System.Collections.IEnumerable> 및 <xref:System.Collections.IEnumerator>를 생략할 경우의 단점은 컬렉션 클래스가 기타 공용 언어 런타임 언어의 `foreach` 문이나 그에 상응하는 문과 상호 운용되지 않는다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="3072e-120">The disadvantage of omitting <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> is that the collection class is no longer interoperable with the `foreach` statements, or equivalent statements, of other common language runtime languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3072e-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3072e-121">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="3072e-122">C# 참조</span><span class="sxs-lookup"><span data-stu-id="3072e-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="3072e-123">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="3072e-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3072e-124">배열</span><span class="sxs-lookup"><span data-stu-id="3072e-124">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="3072e-125">컬렉션</span><span class="sxs-lookup"><span data-stu-id="3072e-125">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)
