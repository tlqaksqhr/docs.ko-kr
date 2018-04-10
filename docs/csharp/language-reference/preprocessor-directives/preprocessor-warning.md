---
title: '#warning(C# 참조)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
caps.latest.revision: 9
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8145c4a62d5179d6fa46e27186d83fc0108939d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="warning-c-reference"></a><span data-ttu-id="91088-102">#warning(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="91088-102">#warning (C# Reference)</span></span>
<span data-ttu-id="91088-103">`#warning`을 사용하면 코드의 특정 위치에서 수준 1 경고를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91088-103">`#warning` lets you generate a level one warning from a specific location in your code.</span></span> <span data-ttu-id="91088-104">예:</span><span class="sxs-lookup"><span data-stu-id="91088-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="91088-105">설명</span><span class="sxs-lookup"><span data-stu-id="91088-105">Remarks</span></span>  
 <span data-ttu-id="91088-106">`#warning`은 일반적으로 조건부 지시문에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="91088-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="91088-107">[#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)를 사용하여 사용자 정의 오류를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91088-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="91088-108">예제</span><span class="sxs-lookup"><span data-stu-id="91088-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="91088-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91088-109">See Also</span></span>  
 [<span data-ttu-id="91088-110">C# 참조</span><span class="sxs-lookup"><span data-stu-id="91088-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="91088-111">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="91088-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="91088-112">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="91088-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
