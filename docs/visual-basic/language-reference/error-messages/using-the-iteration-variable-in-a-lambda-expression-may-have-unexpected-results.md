---
title: "Using the iteration variable in a lambda expression may have unexpected results | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc42324"
  - "bc42324"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42324"
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Using the iteration variable in a lambda expression may have unexpected results
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

람다 식에 반복 변수를 사용하면 예기치 않은 결과가 발생할 수 있습니다.대신 루프 내에 지역 변수를 만든 다음 여기에 반복 변수 값을 할당하십시오.  
  
 루프 내에 선언한 루프 반복 변수를 람다 식에 사용할 경우 이 경고가 나타납니다.  예를 들어 다음 예제는 이 경고 메시지를 표시합니다.  
  
```vb#  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 다음 예제에서는 이 경우 발생할 수 있는 예기치 않은 결과를 보여 줍니다.  
  
```vb#  
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
  
 `For` 루프는 각각 루프 반복 변수 `i`의 값을 반환하는 람다 식의 배열을 만듭니다.  `For Each` 루프에서 람다 식을 계산하면 `For` 루프에 있는 `i`의 순차적인 값인 0, 1, 2, 3, 4가 표시되어야 하지만  마지막 `i` 값만 다섯 번 표시됩니다.  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC42324  
  
### 이 오류를 해결하려면  
  
-   반복 변수 값을 지역 변수에 할당하고 람다 식에 이 지역 변수를 사용합니다.  
  
    ```vb#  
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
  
## 참고 항목  
 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)