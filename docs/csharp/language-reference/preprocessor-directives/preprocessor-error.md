---
title: '#error(C# 참조)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 23528ae81e4ddca23c67c937ca2588ab4c982e98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="error-c-reference"></a><span data-ttu-id="c5806-102">#error(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="c5806-102">#error (C# Reference)</span></span>
<span data-ttu-id="c5806-103">`#error`를 사용하면 코드의 특정 위치에서 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5806-103">`#error` lets you generate an error from a specific location in your code.</span></span> <span data-ttu-id="c5806-104">예:</span><span class="sxs-lookup"><span data-stu-id="c5806-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="c5806-105">설명</span><span class="sxs-lookup"><span data-stu-id="c5806-105">Remarks</span></span>  
 <span data-ttu-id="c5806-106">`#error`은 일반적으로 조건부 지시문에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5806-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="c5806-107">[#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)을 사용하여 사용자 정의 경고를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5806-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5806-108">예제</span><span class="sxs-lookup"><span data-stu-id="c5806-108">Example</span></span>  
  
```csharp
// preprocessor_error.cs  
// CS1029 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#error DEBUG is defined  
#endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5806-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5806-109">See Also</span></span>  
 [<span data-ttu-id="c5806-110">C# 참조</span><span class="sxs-lookup"><span data-stu-id="c5806-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c5806-111">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="c5806-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c5806-112">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="c5806-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
