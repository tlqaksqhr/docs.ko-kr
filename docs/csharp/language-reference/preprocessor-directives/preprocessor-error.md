---
title: "#<a name=\"error-c-reference\"></a>error(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#error'
dev_langs:
- CSharp
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
caps.latest.revision: 10
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
ms.openlocfilehash: d2d497d7b8345b94dfc77176bf2b0ca79674e9be
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="error-c-reference"></a><span data-ttu-id="a6041-102">#error(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a6041-102">#error (C# Reference)</span></span>
<span data-ttu-id="a6041-103">`#error`를 사용하면 코드의 특정 위치에서 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6041-103">`#error` lets you generate an error from a specific location in your code.</span></span> <span data-ttu-id="a6041-104">예:</span><span class="sxs-lookup"><span data-stu-id="a6041-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="a6041-105">설명</span><span class="sxs-lookup"><span data-stu-id="a6041-105">Remarks</span></span>  
 <span data-ttu-id="a6041-106">`#error`는 일반적으로 조건부 지시문에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6041-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="a6041-107">[#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md)을 사용하여 사용자 정의 경고를 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6041-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6041-108">예제</span><span class="sxs-lookup"><span data-stu-id="a6041-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a6041-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6041-109">See Also</span></span>  
 <span data-ttu-id="a6041-110">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a6041-110">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a6041-111">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a6041-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="a6041-112">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="a6041-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

