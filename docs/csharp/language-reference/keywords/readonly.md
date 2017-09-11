---
title: "readonly(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- readonly_CSharpKeyword
- readonly
dev_langs:
- CSharp
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
caps.latest.revision: 16
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
ms.openlocfilehash: 2660aa56721815cbbeb668328863956473cce8f1
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="readonly-c-reference"></a><span data-ttu-id="d28ea-102">readonly(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d28ea-102">readonly (C# Reference)</span></span>
<span data-ttu-id="d28ea-103">`readonly` 키워드는 필드에 사용할 수 있는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="d28ea-103">The `readonly` keyword is a modifier that you can use on fields.</span></span> <span data-ttu-id="d28ea-104">필드 선언에 `readonly` 한정자가 포함되어 있는 경우 선언에 의해 추가된 필드에 대한 할당은 선언의 일부로서 또는 같은 클래스의 생성자에서만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d28ea-104">When a field declaration includes a `readonly` modifier, assignments to the fields introduced by the declaration can only occur as part of the declaration or in a constructor in the same class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d28ea-105">예제</span><span class="sxs-lookup"><span data-stu-id="d28ea-105">Example</span></span>  
 <span data-ttu-id="d28ea-106">이 예제에서는 클래스 생성자에서 값이 할당되지만, `year` 필드의 값을 `ChangeYear` 메서드에서 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d28ea-106">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>  
  
 <span data-ttu-id="d28ea-107">[!code-cs[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d28ea-107">[!code-cs[csrefKeywordsModifiers#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_1.cs)]</span></span>  
  
 <span data-ttu-id="d28ea-108">다음 컨텍스트에서만 `readonly` 필드에 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d28ea-108">You can assign a value to a `readonly` field only in the following contexts:</span></span>  
  
-   <span data-ttu-id="d28ea-109">변수가 선언에서 초기화될 때. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d28ea-109">When the variable is initialized in the declaration, for example:</span></span>  
  
    ```  
    public readonly int y = 5;  
    ```  
  
-   <span data-ttu-id="d28ea-110">인스턴스 필드의 경우 필드 선언이 포함된 클래스의 인스턴스 생성자에서, 또는 정적 필드의 경우 필드 선언이 포함된 클래스의 정적 생성자에서.</span><span class="sxs-lookup"><span data-stu-id="d28ea-110">For an instance field, in the instance constructors of the class that contains the field declaration, or for a static field, in the static constructor of the class that contains the field declaration.</span></span> <span data-ttu-id="d28ea-111">`readonly` 필드를 [out](../../../csharp/language-reference/keywords/out.md) 또는 [ref](../../../csharp/language-reference/keywords/ref.md)로 전달하는 것이 유효한 컨텍스트는 이러한 경우뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="d28ea-111">These are also the only contexts in which it is valid to pass a `readonly` field as an [out](../../../csharp/language-reference/keywords/out.md) or [ref](../../../csharp/language-reference/keywords/ref.md) parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d28ea-112">`readonly` 키워드와 [const](../../../csharp/language-reference/keywords/const.md) 키워드와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d28ea-112">The `readonly` keyword is different from the [const](../../../csharp/language-reference/keywords/const.md) keyword.</span></span> <span data-ttu-id="d28ea-113">`const` 필드는 필드 선언에서만 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d28ea-113">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="d28ea-114">`readonly` 필드는 선언이나 생성자에서 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d28ea-114">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="d28ea-115">따라서 `readonly` 필드는 사용된 생성자에 따라 다른 값을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d28ea-115">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="d28ea-116">또한 `const` 필드는 컴파일 시간 상수인 반면, `readonly` 필드는 다음 예제와 같이 런타임 상수에 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d28ea-116">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>  
  
```  
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;  
```  
  
## <a name="example"></a><span data-ttu-id="d28ea-117">예제</span><span class="sxs-lookup"><span data-stu-id="d28ea-117">Example</span></span>  
 <span data-ttu-id="d28ea-118">[!code-cs[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d28ea-118">[!code-cs[csrefKeywordsModifiers#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/readonly_2.cs)]</span></span>  
  
 <span data-ttu-id="d28ea-119">위의 예제에서 다음과 같은 문을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="d28ea-119">In the preceding example, if you use a statement like this:</span></span>  
  
 `p2.y = 66;        // Error`  
  
 <span data-ttu-id="d28ea-120">컴파일러 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d28ea-120">you will get the compiler error message:</span></span>  
  
 `The left-hand side of an assignment must be an l-value`  
  
 <span data-ttu-id="d28ea-121">상수에 값을 할당하려고 할 때 표시되는 것과 같은 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="d28ea-121">which is the same error you get when you attempt to assign a value to a constant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d28ea-122">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="d28ea-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d28ea-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d28ea-123">See Also</span></span>  
 <span data-ttu-id="d28ea-124">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d28ea-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d28ea-125">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d28ea-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d28ea-126">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d28ea-126">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d28ea-127">[한정자](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="d28ea-127">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="d28ea-128">[const](../../../csharp/language-reference/keywords/const.md) </span><span class="sxs-lookup"><span data-stu-id="d28ea-128">[const](../../../csharp/language-reference/keywords/const.md) </span></span>  
 [<span data-ttu-id="d28ea-129">필드</span><span class="sxs-lookup"><span data-stu-id="d28ea-129">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)

