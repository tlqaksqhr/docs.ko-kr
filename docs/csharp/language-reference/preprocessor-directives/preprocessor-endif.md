---
title: '#endif(C# 참조)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
caps.latest.revision: 9
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d7e68dd20d914052c3fe5cabcb83abdae100465c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="endif-c-reference"></a><span data-ttu-id="28040-102">#endif(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="28040-102">#endif (C# Reference)</span></span>
<span data-ttu-id="28040-103">`#endif`는 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 지시문으로 시작한 조건부 지시문의 끝을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="28040-103">`#endif` specifies the end of a conditional directive, which began with the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive.</span></span> <span data-ttu-id="28040-104">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="28040-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="28040-105">설명</span><span class="sxs-lookup"><span data-stu-id="28040-105">Remarks</span></span>  
 <span data-ttu-id="28040-106">`#if` 지시문으로 시작되는 조건부 지시문은 `#endif` 지시문을 사용하여 명시적으로 종료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="28040-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="28040-107">`#endif`를 사용하는 방법에 대한 예제는 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="28040-107">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28040-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28040-108">See Also</span></span>  
 [<span data-ttu-id="28040-109">C# 참조</span><span class="sxs-lookup"><span data-stu-id="28040-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="28040-110">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="28040-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="28040-111">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="28040-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
