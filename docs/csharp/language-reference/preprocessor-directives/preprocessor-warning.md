---
title: "#<a name=\"warning-c-reference\"></a>warning(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#warning'
dev_langs:
- CSharp
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
caps.latest.revision: 9
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
ms.openlocfilehash: 8630101a90bd6d4ed2036b495b254c9475531dc0
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="warning-c-reference"></a><span data-ttu-id="58e3e-102">#warning(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="58e3e-102">#warning (C# Reference)</span></span>
<span data-ttu-id="58e3e-103">`#warning`을 사용하면 코드의 특정 위치에서 수준 1 경고를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58e3e-103">`#warning` lets you generate a level one warning from a specific location in your code.</span></span> <span data-ttu-id="58e3e-104">예:</span><span class="sxs-lookup"><span data-stu-id="58e3e-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="58e3e-105">설명</span><span class="sxs-lookup"><span data-stu-id="58e3e-105">Remarks</span></span>  
 <span data-ttu-id="58e3e-106">`#warning`은 일반적으로 조건부 지시문에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="58e3e-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="58e3e-107">[#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)를 사용하여 사용자 정의 오류를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58e3e-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="58e3e-108">예제</span><span class="sxs-lookup"><span data-stu-id="58e3e-108">Example</span></span>  
  
```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="58e3e-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58e3e-109">See Also</span></span>  
 <span data-ttu-id="58e3e-110">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="58e3e-110">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="58e3e-111">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="58e3e-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="58e3e-112">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="58e3e-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

