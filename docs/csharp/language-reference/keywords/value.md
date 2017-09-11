---
title: "value(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- value_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
caps.latest.revision: 14
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
ms.openlocfilehash: 012cf622091687996fec477a8b5b821b190bbc29
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="value-c-reference"></a><span data-ttu-id="6ebd3-102">value(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="6ebd3-102">value (C# Reference)</span></span>
<span data-ttu-id="6ebd3-103">상황별 키워드 `value`는 일반 속성 선언의 set 접근자에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ebd3-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="6ebd3-104">메서드의 입력 매개 변수와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebd3-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="6ebd3-105">`value` 단어는 클라이언트 코드가 속성에 할당하려고 시도하는 값을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebd3-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="6ebd3-106">다음 예에서 `MyDerivedClass`에는 `Name`이라는 속성이 있습니다. 이 속성은 `value` 매개 변수를 사용하여 지원 필드 `name`에 새 문자열을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6ebd3-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="6ebd3-107">클라이언트 코드의 관점에서 이 작업은 단순한 할당으로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ebd3-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>  
  
 <span data-ttu-id="6ebd3-108">[!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6ebd3-108">[!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]</span></span>  
  
 <span data-ttu-id="6ebd3-109">`value` 사용에 대한 자세한 내용은 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6ebd3-109">For more information about the use of `value`, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6ebd3-110">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="6ebd3-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6ebd3-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ebd3-111">See Also</span></span>  
 <span data-ttu-id="6ebd3-112">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6ebd3-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6ebd3-113">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6ebd3-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="6ebd3-114">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="6ebd3-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

