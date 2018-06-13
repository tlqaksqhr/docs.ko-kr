---
title: '#error(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 9ea4c24dcc3c0a4d39499bee5900cb9c6cc768c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269401"
---
# <a name="error-c-reference"></a><span data-ttu-id="23fd4-102">#error(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="23fd4-102">#error (C# Reference)</span></span>
<span data-ttu-id="23fd4-103">`#error`를 사용하면 코드의 특정 위치에서 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23fd4-103">`#error` lets you generate an error from a specific location in your code.</span></span> <span data-ttu-id="23fd4-104">예:</span><span class="sxs-lookup"><span data-stu-id="23fd4-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="23fd4-105">설명</span><span class="sxs-lookup"><span data-stu-id="23fd4-105">Remarks</span></span>  
 <span data-ttu-id="23fd4-106">`#error`은 일반적으로 조건부 지시문에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="23fd4-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="23fd4-107">[#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)을 사용하여 사용자 정의 경고를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23fd4-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="23fd4-108">예</span><span class="sxs-lookup"><span data-stu-id="23fd4-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="23fd4-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23fd4-109">See Also</span></span>  
 [<span data-ttu-id="23fd4-110">C# 참조</span><span class="sxs-lookup"><span data-stu-id="23fd4-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="23fd4-111">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="23fd4-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="23fd4-112">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="23fd4-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
