---
title: 첫 번째 피연산자에는 이진 &#39; 경우 &#39; 식이 null을 허용 해야 합니다. 또는 참조 형식
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f66b110c02076120c55a3bff28c3d7614bf8be26
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="first-operand-in-a-binary-39if39-expression-must-be-nullable-or-a-reference-type"></a><span data-ttu-id="9f918-102">첫 번째 피연산자에는 이진 &#39; 경우 &#39; 식이 null을 허용 해야 합니다. 또는 참조 형식</span><span class="sxs-lookup"><span data-stu-id="9f918-102">First operand in a binary &#39;If&#39; expression must be nullable or a reference type</span></span>
<span data-ttu-id="9f918-103">`If` 식은 두 개 또는 세 개의 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f918-103">An `If` expression can take either two or three arguments.</span></span> <span data-ttu-id="9f918-104">두 개의 인수를 보낼 때 첫 번째 인수는 참조 형식 또는 nullable 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f918-104">When you send only two arguments, the first argument must be a reference type or a nullable type.</span></span> <span data-ttu-id="9f918-105">첫 번째 인수 이외의 값으로 계산 하는 경우 `Nothing`, 해당 값이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f918-105">If the first argument evaluates to anything other than `Nothing`, its value is returned.</span></span> <span data-ttu-id="9f918-106">첫 번째 인수를 평가 하는 경우 `Nothing`, 두 번째 인수가 계산 되 고 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f918-106">If the first argument evaluates to `Nothing`, the second argument is evaluated and returned.</span></span>  
  
 <span data-ttu-id="9f918-107">예를 들어 다음 코드에는 두 개의 `If` 식, 하나는 세 인수 및 두 개의 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f918-107">For example, the following code contains two `If` expressions, one with three arguments and one with two arguments.</span></span> <span data-ttu-id="9f918-108">식을 계산 하 고 동일한 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f918-108">The expressions calculate and return the same value.</span></span>  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 <span data-ttu-id="9f918-109">다음 식에서는이 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="9f918-109">The following expressions cause this error:</span></span>  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 <span data-ttu-id="9f918-110">**오류 ID:** BC33107</span><span class="sxs-lookup"><span data-stu-id="9f918-110">**Error ID:** BC33107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9f918-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="9f918-111">To correct this error</span></span>  
  
-   <span data-ttu-id="9f918-112">첫 번째 인수가 null 허용 형식 또는 참조 형식이 되도록 코드를 변경할 수 없는 경우, 3 개의 인수를 변환할 고려 `If` 식 또는 `If...Then...Else` 문.</span><span class="sxs-lookup"><span data-stu-id="9f918-112">If you cannot change the code so that the first argument is a nullable type or reference type, consider converting to a three-argument `If` expression, or to an `If...Then...Else` statement.</span></span>  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a><span data-ttu-id="9f918-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f918-113">See Also</span></span>  
 [<span data-ttu-id="9f918-114">If 연산자</span><span class="sxs-lookup"><span data-stu-id="9f918-114">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)  
 [<span data-ttu-id="9f918-115">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="9f918-115">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="9f918-116">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="9f918-116">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
