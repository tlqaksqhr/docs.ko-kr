---
title: "try-catch-finally(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
dev_langs:
- CSharp
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
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
ms.openlocfilehash: 05b2e0075aae79f85fba26d64690eefadaa166cd
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="340bb-102">try-catch-finally(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="340bb-102">try-catch-finally (C# Reference)</span></span>
<span data-ttu-id="340bb-103">`catch` 및 `finally`를 함께 사용하는 일반적인 경우는 `try` 블록에서 리소스를 얻어 사용하고, `catch` 블록에서 예외 상황을 처리하고, `finally` 블록에서 리소스를 해제하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="340bb-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>  
  
 <span data-ttu-id="340bb-104">예외를 다시 throw하는 방법에 대한 자세한 내용과 예제는 [try-catch](../../../csharp/language-reference/keywords/try-catch.md) 및 [예외 throw](https://msdn.microsoft.com/library/xhcbs8fz)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="340bb-104">For more information and examples on re-throwing exceptions, see [try-catch](../../../csharp/language-reference/keywords/try-catch.md) and [Throwing Exceptions](https://msdn.microsoft.com/library/xhcbs8fz).</span></span> <span data-ttu-id="340bb-105">`finally` 블록에 대한 자세한 내용은 [try-finally](../../../csharp/language-reference/keywords/try-finally.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="340bb-105">For more information about the `finally` block, see [try-finally](../../../csharp/language-reference/keywords/try-finally.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="340bb-106">예제</span><span class="sxs-lookup"><span data-stu-id="340bb-106">Example</span></span>  
 <span data-ttu-id="340bb-107">[!code-cs[csrefKeywordsExceptions#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch-finally_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="340bb-107">[!code-cs[csrefKeywordsExceptions#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch-finally_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="340bb-108">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="340bb-108">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="340bb-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="340bb-109">See Also</span></span>  
 <span data-ttu-id="340bb-110">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="340bb-110">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="340bb-111">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="340bb-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="340bb-112">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="340bb-112">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="340bb-113">[try, throw 및 catch 문(C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span><span class="sxs-lookup"><span data-stu-id="340bb-113">[try, throw, and catch Statements (C++)](/cpp/cpp/try-throw-and-catch-statements-cpp) </span></span>  
 <span data-ttu-id="340bb-114">[예외 처리 문](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span><span class="sxs-lookup"><span data-stu-id="340bb-114">[Exception Handling Statements](../../../csharp/language-reference/keywords/exception-handling-statements.md) </span></span>  
 <span data-ttu-id="340bb-115">[throw](../../../csharp/language-reference/keywords/throw.md) </span><span class="sxs-lookup"><span data-stu-id="340bb-115">[throw](../../../csharp/language-reference/keywords/throw.md) </span></span>  
 <span data-ttu-id="340bb-116">[방법: 명시적으로 예외 Throw](https://msdn.microsoft.com/library/xhcbs8fz) </span><span class="sxs-lookup"><span data-stu-id="340bb-116">[How to: Explicitly Throw Exceptions](https://msdn.microsoft.com/library/xhcbs8fz) </span></span>  
 [<span data-ttu-id="340bb-117">using 문</span><span class="sxs-lookup"><span data-stu-id="340bb-117">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)

