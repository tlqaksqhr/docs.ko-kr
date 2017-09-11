---
title: "방법: ToString 메서드 재정의(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
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
ms.openlocfilehash: 60cec855286a3bb572a0bacd08c0f7920a1fc912
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="8a6c2-102">방법: ToString 메서드 재정의(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="8a6c2-102">How to: Override the ToString Method (C# Programming Guide)</span></span>
<span data-ttu-id="8a6c2-103">C#의 모든 클래스 또는 구조체는 <xref:System.Object> 클래스를 암시적으로 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6c2-103">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="8a6c2-104">따라서 C#의 모든 개체는 해당 개체의 문자열 표현을 반환하는 <xref:System.Object.ToString%2A> 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8a6c2-104">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="8a6c2-105">예를 들어 `int` 형식의 모든 변수에는 해당 내용을 문자열로 반환할 수 있도록 하는 `ToString` 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a6c2-105">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 <span data-ttu-id="8a6c2-106">[!code-cs[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8a6c2-106">[!code-cs[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]</span></span>  
  
 <span data-ttu-id="8a6c2-107">사용자 지정 클래스 또는 구조체를 만들 때 해당 형식에 대한 정보를 클라이언트 코드에 제공하려면 <xref:System.Object.ToString%2A> 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6c2-107">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="8a6c2-108">`ToString` 메서드와 함께 형식 문자열 및 다른 형식의 사용자 지정 서식을 사용하는 방법에 대한 자세한 내용은 [형식 서식 지정](../../../standard/base-types/formatting-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a6c2-108">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8a6c2-109">이 메서드를 통해 제공할 정보를 결정하는 경우 신뢰할 수 없는 코드에서 클래스 또는 구조체가 사용될지 여부를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6c2-109">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="8a6c2-110">악성 코드에서 악용될 수 있는 정보를 제공하지 않으면 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6c2-110">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
### <a name="to-override-the-tostring-method-in-your-class-or-struct"></a><span data-ttu-id="8a6c2-111">클래스 또는 구조체의 ToString 메서드를 재정의하려면</span><span class="sxs-lookup"><span data-stu-id="8a6c2-111">To override the ToString method in your class or struct</span></span>  
  
1.  <span data-ttu-id="8a6c2-112">다음 한정자 및 반환 형식으로 `ToString` 메서드를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6c2-112">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2.  <span data-ttu-id="8a6c2-113">문자열을 반환하도록 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6c2-113">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="8a6c2-114">다음 예제에서는 클래스의 특정 인스턴스와 관련된 데이터뿐 아니라 클래스의 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8a6c2-114">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     <span data-ttu-id="8a6c2-115">[!code-cs[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8a6c2-115">[!code-cs[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]</span></span>  
  
     <span data-ttu-id="8a6c2-116">다음 코드 예제와 같이 `ToString` 메서드를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a6c2-116">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     <span data-ttu-id="8a6c2-117">[!code-cs[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8a6c2-117">[!code-cs[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a6c2-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a6c2-118">See Also</span></span>  
 <span data-ttu-id="8a6c2-119"><xref:System.IFormattable></span><span class="sxs-lookup"><span data-stu-id="8a6c2-119"><xref:System.IFormattable></span></span>   
 <span data-ttu-id="8a6c2-120">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8a6c2-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8a6c2-121">[클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="8a6c2-121">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="8a6c2-122">[문자열](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="8a6c2-122">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 <span data-ttu-id="8a6c2-123">[string](../../../csharp/language-reference/keywords/string.md) </span><span class="sxs-lookup"><span data-stu-id="8a6c2-123">[string](../../../csharp/language-reference/keywords/string.md) </span></span>  
 <span data-ttu-id="8a6c2-124">[new](../../../csharp/language-reference/keywords/new.md) </span><span class="sxs-lookup"><span data-stu-id="8a6c2-124">[new](../../../csharp/language-reference/keywords/new.md) </span></span>  
 <span data-ttu-id="8a6c2-125">[override](../../../csharp/language-reference/keywords/override.md) </span><span class="sxs-lookup"><span data-stu-id="8a6c2-125">[override](../../../csharp/language-reference/keywords/override.md) </span></span>  
 <span data-ttu-id="8a6c2-126">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span><span class="sxs-lookup"><span data-stu-id="8a6c2-126">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span></span>  
 [<span data-ttu-id="8a6c2-127">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="8a6c2-127">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)

