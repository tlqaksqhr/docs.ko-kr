---
title: "#<a name=\"undef-c-reference\"></a>undef(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#undef'
dev_langs:
- CSharp
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
caps.latest.revision: 12
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
ms.openlocfilehash: acdd043535ef319f2af40c809e7fe4af612cb17d
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="undef-c-reference"></a><span data-ttu-id="a4dfb-102">#undef(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a4dfb-102">#undef (C# Reference)</span></span>
<span data-ttu-id="a4dfb-103">`#undef`를 사용하면 기호의 정의를 해제할 수 있습니다. 그러면 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 지시문에서 해당 기호를 식으로 사용하여 식이 `false`로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4dfb-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="a4dfb-104">[#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) 지시문 또는 [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) 컴파일러 옵션을 사용하여 기호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4dfb-104">A symbol can be defined either with the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) directive or the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="a4dfb-105">`#undef` 지시문은 지시문이 아닌 문을 사용하기 전에 파일에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4dfb-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4dfb-106">예제</span><span class="sxs-lookup"><span data-stu-id="a4dfb-106">Example</span></span>  
  
```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass   
{  
    static void Main()   
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```  
  
 <span data-ttu-id="a4dfb-107">**디버그가 정의되어 있지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="a4dfb-107">**DEBUG is not defined**</span></span>   
## <a name="see-also"></a><span data-ttu-id="a4dfb-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4dfb-108">See Also</span></span>  
 <span data-ttu-id="a4dfb-109">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a4dfb-109">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a4dfb-110">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a4dfb-110">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="a4dfb-111">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="a4dfb-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

