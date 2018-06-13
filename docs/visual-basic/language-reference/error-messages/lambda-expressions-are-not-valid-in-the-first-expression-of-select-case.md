---
title: 람다 식의 첫 번째 식에 유효 하지 않은 한 &#39;Select Case&#39; 문
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: c492615850ec089fe35c1ae4eaba90a741e30f42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588923"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-39select-case39-statement"></a><span data-ttu-id="3c582-102">람다 식의 첫 번째 식에 유효 하지 않은 한 &#39;Select Case&#39; 문</span><span class="sxs-lookup"><span data-stu-id="3c582-102">Lambda expressions are not valid in the first expression of a &#39;Select Case&#39; statement</span></span>
<span data-ttu-id="3c582-103">테스트 식에 람다 식을 사용할 수 없습니다는 `Select Case` 문.</span><span class="sxs-lookup"><span data-stu-id="3c582-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="3c582-104">람다 식 정의는 함수를 테스트 식의 반환을 `Select Case` 문은 기본 데이터 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c582-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>  
  
 <span data-ttu-id="3c582-105">다음 코드에이 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="3c582-105">The following code causes this error:</span></span>  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 <span data-ttu-id="3c582-106">**오류 ID:** BC36635</span><span class="sxs-lookup"><span data-stu-id="3c582-106">**Error ID:** BC36635</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3c582-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3c582-107">To correct this error</span></span>  
  
-   <span data-ttu-id="3c582-108">코드를 검사하여 `If...Then...Else` 문과 같은 다른 조건부 생성이 적합한지 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="3c582-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>  
  
-   <span data-ttu-id="3c582-109">계획 했던 함수를 호출 하려면 다음 코드에 나와 있는 것 처럼:</span><span class="sxs-lookup"><span data-stu-id="3c582-109">You may have intended to call the function, as shown in the following code:</span></span>  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c582-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c582-110">See Also</span></span>  
 [<span data-ttu-id="3c582-111">람다 식</span><span class="sxs-lookup"><span data-stu-id="3c582-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="3c582-112">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="3c582-112">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="3c582-113">Select...Case 문</span><span class="sxs-lookup"><span data-stu-id="3c582-113">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
