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
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5b293ec344d816e40d369757fa4d11710b7ecd8d
ms.lasthandoff: 03/13/2017

---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a>람다 식에 반복 변수를 사용하면 예기치 않은 결과가 발생할 수 있습니다.
람다 식에 반복 변수를 사용하면 예기치 않은 결과가 발생할 수 있습니다. 대신, 루프 내에서 로컬 변수를 만들고 반복 변수의 값을 할당 합니다.  
  
 이 경고는 루프 내에서 선언 되는 람다 식에 루프 반복 변수를 사용 하는 경우에 나타납니다. 예를 들어, 다음 예제에서는 경고를 표시 합니다.  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 다음 예제에서는 발생할 수 있는 예기치 않은 결과 보여 줍니다.  
  
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
  
 `For` 루프는 각 루프 반복 변수의 값을 반환 람다 식의 배열을 만듭니다 `i`합니다. 람다 식의 평가 하는 경우는 `For Each` 루프를 짐작할 수 있겠지만 0, 1, 2, 3 및 4가 표시의 연속 값을 보려면 `i` 에 `For` 루프입니다. 최종 값을 확인 하는 대신, `i` 다섯 번 표시 됩니다.  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** BC42324  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   반복 변수 값을 지역 변수에 할당 하 고 람다 식의 지역 변수를 사용 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
