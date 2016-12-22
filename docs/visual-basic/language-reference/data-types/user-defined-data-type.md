---
title: "User-Defined Data Type | Microsoft Docs"
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
  - "UserDefined"
  - "UDT"
  - "vb.UDT"
  - "User-Defined"
  - "vb.UserDefined"
  - "vb.User-Defined"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "user-defined data types, Visual Basic"
  - "user-defined types"
  - "structures, as user-defined data types"
  - "user-defined types, Visual Basic"
  - "user-defined types, structure declaration"
  - "user-defined types, structures in Visual Basic"
  - "user-defined data types, structure declaration"
  - "data types [Visual Basic], assigning"
  - "Structure statement"
  - "data types [Visual Basic], user-defined"
  - "user-defined data types, structures in Visual Basic"
  - "user-defined data types"
  - "types [Visual Basic], user-defined"
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# User-Defined Data Type
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

사용자가 정의한 형식으로 데이터를 저장합니다.  `Structure` 문으로 형식을 정의합니다.  
  
 이전 버전의 Visual Basic에서는 UDT\(사용자 정의 형식\)가 지원됩니다.  현재 버전에서는 UDT가 *구조체*로 확장됩니다.  구조체는 다양한 데이터 형식을 가진 하나 이상의 *멤버*를 연결한 것입니다.  구조체의 각 멤버에 개별적으로 액세스할 수도 있지만 Visual Basic에서 구조체는 하나의 단위로 취급됩니다.  
  
## 설명  
 다양한 데이터 형식을 하나의 단위로 결합하거나 기본 데이터 형식 중 원하는 형식이 없는 경우 구조체 데이터 형식을 정의하고 사용합니다.  
  
 구조체 데이터 형식의 기본값은 각 멤버의 기본값 조합으로 구성됩니다.  
  
## 선언 형식  
 구조체 선언은 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)으로 시작되고 `End` `Structure` 문으로 끝납니다.  `Structure` 문은 구조체의 이름을 제공하며 이 이름은 해당 구조체가 정의하는 데이터 형식의 식별자로도 사용됩니다.  코드의 다른 부분에서 이 식별자를 사용하여 변수, 매개 변수 및 함수 반환 값을 이 구조체의 데이터 형식으로 선언할 수 있습니다.  
  
 `Structure` 문과 `End` `Structure` 문 사이의 선언 부분에서는 구조체 멤버를 정의합니다.  
  
## 멤버 액세스 수준  
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) 또는 액세스 수준을 지정하는 문\(예: [Public](../../../visual-basic/language-reference/modifiers/public.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 또는 [Private](../../../visual-basic/language-reference/modifiers/private.md)\)을 사용하여 모든 멤버를 선언해야 합니다.  `Dim` 문을 사용할 경우 액세스 수준은 기본적으로 public입니다.  
  
## 프로그래밍 팁  
  
-   **메모리 사용.** 모든 복합 데이터 형식과 마찬가지로 해당 멤버의 일반 저장소 할당량을 모두 더하는 것만으로 구조체의 총 메모리 사용량을 정확히 계산할 수는 없습니다.  또한 메모리에서 저장소의 순서가 사용자의 선언 순서와 동일하다고 가정할 수도 없습니다.  구조체의 저장소 레이아웃을 제어해야 할 경우 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성을 `Structure` 문에 적용할 수 있습니다.  
  
-   **Interop 고려 사항.** Automation 또는 COM 개체와 같이 .NET Framework용으로 작성되지 않은 구성 요소를 사용하는 경우 다른 환경에서는 사용자 정의 형식이 Visual Basic 구조체 형식과 호환되지 않는다는 것을 염두에 두고 있어야 합니다.  
  
-   **확대 변환.** 구조체 데이터 형식 간에 자동 변환이 수행되지 않습니다.  [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)을 사용하여 구조체에서 변환 연산자를 정의할 수 있으며 각 변환 연산자가 `Widening` 또는 `Narrowing`이 되도록 선언할 수 있습니다.  
  
-   **형식 문자.** 구조체 데이터 형식에는 리터럴 형식 문자나 식별자 형식 문자가 없습니다.  
  
-   **Framework 형식.** .NET Framework에서는 해당 형식이 없습니다.  모든 구조체가 .NET Framework 클래스 <xref:System.ValueType?displayProperty=fullName>에서 상속되지만 <xref:System.ValueType?displayProperty=fullName>에 해당하는 개별 구조체는 없습니다.  
  
## 예제  
 다음 형태는 구조체 선언의 개요를 보여 줍니다.  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## 참고 항목  
 <xref:System.ValueType>   
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [변환 요약](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)   
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)