---
title: "맺은 람다 식에 반복 변수를 사용 하 여 예기치 않은 결과가 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42324
- bc42324
dev_langs:
- VB
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1c2e0e322ff46b9e215a169cd4cf3805c7dc3943
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="f6e0e-102">람다 식에 반복 변수를 사용하면 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e0e-102">Using the iteration variable in a lambda expression may have unexpected results</span></span>
<span data-ttu-id="f6e0e-103">람다 식에 반복 변수를 사용하면 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e0e-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="f6e0e-104">대신, 루프 내에서 로컬 변수를 만들고 반복 변수의 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e0e-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>  
  
 <span data-ttu-id="f6e0e-105">이 경고는 루프 내에서 선언 되는 람다 식에 루프 반복 변수를 사용 하는 경우에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f6e0e-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="f6e0e-106">예를 들어, 다음 예제에서는 경고를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e0e-106">For example, the following example causes the warning to appear.</span></span>  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 <span data-ttu-id="f6e0e-107">다음 예제에서는 발생할 수 있는 예기치 않은 결과 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6e0e-107">The following example shows the unexpected results that might occur.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            array1(i) = Function() i  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="f6e0e-108">`For` 루프는 각 루프 반복 변수의 값을 반환 람다 식의 배열을 만듭니다 `i`합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e0e-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="f6e0e-109">람다 식의 평가 하는 경우는 `For Each` 루프를 짐작할 수 있겠지만 0, 1, 2, 3 및 4가 표시의 연속 값을 보려면 `i` 에 `For` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="f6e0e-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="f6e0e-110">최종 값을 확인 하는 대신, `i` 다섯 번 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6e0e-110">Instead, you see the final value of `i` displayed five times:</span></span>  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 <span data-ttu-id="f6e0e-111">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="f6e0e-111">By default, this message is a warning.</span></span> <span data-ttu-id="f6e0e-112">경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e0e-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="f6e0e-113">**오류 ID:** BC42324</span><span class="sxs-lookup"><span data-stu-id="f6e0e-113">**Error ID:** BC42324</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f6e0e-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f6e0e-114">To correct this error</span></span>  
  
-   <span data-ttu-id="f6e0e-115">반복 변수 값을 지역 변수에 할당 하 고 람다 식의 지역 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e0e-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            Dim j = i  
            array1(i) = Function() j  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6e0e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6e0e-116">See Also</span></span>  
 [<span data-ttu-id="f6e0e-117">람다 식</span><span class="sxs-lookup"><span data-stu-id="f6e0e-117">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
