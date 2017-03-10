---
title: "How to: Assign One Array to Another Array (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "covariance, arrays"
  - "arrays [Visual Basic], assigning"
  - "arrays [Visual Basic], covariance"
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# How to: Assign One Array to Another Array (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

배열은 개체이기 때문에 다른 개체 형식처럼 대입문에서 사용할 수 있습니다.  배열 변수에는 배열 요소를 구성하는 데이터와 차수 및 길이 정보의 포인터가 저장되며 배열을 할당할 때는 이 포인터만 복사됩니다.  
  
### 한 배열에 다른 배열을 할당하려면  
  
1.  두 배열의 차수\(차원의 수\)가 같고 요소 데이터 형식이 호환되는지 확인합니다.  
  
2.  표준 대입문을 사용하여 대상 배열에 소스 배열을 할당합니다.  배열 이름 뒤에 괄호를 넣을 수 없습니다.  
  
    ```  
    Dim formArray() As System.Windows.Forms.Form  
    Dim controlArray() As System.Windows.Forms.Control  
    controlArray = formArray  
    ```  
  
 한 배열을 다른 배열에 할당할 때 적용되는 규칙은 다음과 같습니다.  
  
-   **동일한 차수.** 대상 배열의 차수\(차원의 수\)는 소스 배열의 차수와 같아야 합니다.  
  
     두 배열의 차수가 같은 경우 차원은 같지 않아도 됩니다.  특정 차원의 요소 개수는 할당 중에 변경할 수 있습니다.  
  
-   **요소 형식.** 두 배열이 모두 *참조 형식* 요소를 갖든지 모두 *값 형식* 요소를 가져야 합니다.  자세한 내용은 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)를 참조하십시오.  
  
    -   두 배열이 모두가 값 형식 요소를 가지는 경우 요소 데이터 형식이 정확히 같아야 합니다.  유일한 예외는 `Enum` 요소의 배열을 해당 `Enum` 기본 형식 배열에 할당할 수 있다는 점입니다.  
  
    -   두 배열이 모드 참조 형식 요소를 가지는 경우 소스 요소 형식은 대상 요소 형식에서 파생되어야 합니다.  이 경우 두 배열은 배열 요소와 동일한 상속 관계를 가집니다.  이러한 관계를 *배열 공 분산*이라고 합니다.  
  
 위의 규칙을 위반하면\(예: 데이터 형식이 호환되지 않거나 차수가 다른 경우\) 컴파일러에서 오류를 보고합니다.  코드에 오류 처리를 추가하면 배열을 할당하기 전에 배열이 할당 가능한지 확인할 수 있습니다.  [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md) 키워드를 사용하여 예외가 발생하지 않도록 할 수도 있습니다.  
  
## 참고 항목  
 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Troubleshooting Arrays](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)   
 [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)