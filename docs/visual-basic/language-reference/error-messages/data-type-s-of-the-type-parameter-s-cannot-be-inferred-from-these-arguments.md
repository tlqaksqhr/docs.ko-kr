---
title: "Data type(s) of the type parameter(s) cannot be inferred from these arguments | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc36644"
  - "bc36647"
  - "vbc36647"
  - "vbc36644"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36644"
  - "BC36647"
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Data type(s) of the type parameter(s) cannot be inferred from these arguments
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다.데이터 형식을 명시적으로 지정하면 이 오류를 해결할 수 있습니다.  
  
 이 오류는 오버로드 확인에 실패한 경우에 발생합니다.  이 오류가 발생하면 특정 오버로드 후보가 제거된 이유를 알려주는 메시지가 표시됩니다.  이 오류 메시지는 컴파일러에서 형식 유추를 사용하여 형식 매개 변수의 데이터 형식을 찾을 수 없음을 알려줍니다.  
  
> [!NOTE]
>  쿼리 식의 쿼리 연산자와 같이 인수를 반드시 지정해야 할 경우에는 두 번째 문장 없이 오류 메시지가 나타납니다.  
  
 다음 코드에서는 이 오류를 보여 줍니다.  
  
```vb#  
Module Module1  
  
    Sub Main()  
  
        '' Not Valid.  
        'OverloadedGenericMethod("Hello", "World")  
  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T)(ByVal x As String,   
                                      ByVal y As InterfaceExample(Of T))  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,   
                                         ByVal y As InterfaceExample(Of R))  
    End Sub  
  
End Module  
  
Interface InterfaceExample(Of T)  
End Interface  
```  
  
 **오류 ID:** BC36647 및 BC36644  
  
### 이 오류를 해결하려면  
  
-   형식 유추를 사용하는 대신 형식 매개 변수의 데이터 형식을 지정할 수 있습니다.  
  
## 참고 항목  
 [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [Generic Procedures in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)   
 [Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)