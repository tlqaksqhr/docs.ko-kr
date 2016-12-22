---
title: "How to: Create a Property (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "Visual Basic code, properties"
  - "properties [Visual Basic]"
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Create a Property (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

속성 정의는 `Property` 문과 `End Property` 문 사이에 포함되어야 합니다.  이 정의 안에서 `Get` 프로시저나 `Set` 프로시저 또는 둘 다를 정의합니다.  모든 속성의 코드가 이 두 프로시저 안에 있습니다.  
  
 `Get` 프로시저는 속성 값을 가져오고, `Set` 프로시저는 값을 저장합니다.  속성에 읽기\/쓰기 권한을 부여하려면 두 가지 프로시저를 모두 정의해야 합니다.  읽기 전용 속성에는 `Get` 프로시저만 정의하고, 쓰기 전용 속성에는 `Set` 프로시저만 정의합니다.  
  
### 속성을 만들려면  
  
1.  속성이나 프로시저 밖에서 [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) 뒤에 `End Property` 문을 사용합니다.  
  
2.  속성에 매개 변수가 사용되면 `Property` 키워드 다음에 프로시저 이름을 지정한 다음 매개 변수 목록을 괄호 안에 지정합니다.  
  
3.  괄호 다음에 `As` 절을 사용하여 속성 값의 데이터 형식을 지정합니다.  쓰기 전용 속성의 경우에도 데이터 형식을 지정해야 합니다.  
  
4.  `Get` 프로시저와 `Set` 프로시저를 적절히 추가합니다.  다음 지침을 참조하십시오.  
  
### 속성 값을 가져오는 Get 프로시저를 만들려면  
  
1.  `Property` 문과 `End Property` 문 사이에 [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)을 쓴 다음 `End Get` 문을 지정합니다.  `Get` 프로시저에 대한 매개 변수는 정의할 필요가 없습니다.  
  
2.  속성 값을 가져오는 코드 문을 `Get` 문과 `End Get` 문 사이에 삽입합니다.  이 코드에는 속성 값 생성과 반환 외에도 그 밖의 계산 및 데이터 조작 과정이 포함될 수 있습니다.  
  
3.  `Return` 문을 사용하여 속성 값을 호출 코드로 반환합니다.  
  
 읽기\/쓰기 속성과 읽기 전용 속성에 대한 `Get` 프로시저를 작성해야 합니다.  쓰기 전용 속성에 대한 `Get` 프로시저는 정의할 수 없습니다.  
  
### 속성 값을 저장하는 Set 프로시저를 만들려면  
  
1.  `Property` 문과 `End Property` 문 사이에 [Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)을 쓴 다음 `End Set` 문을 지정합니다.  
  
2.  `Set` 문에서 `Set` 키워드 다음에 매개 변수 목록을 괄호로 묶어 지정합니다.  이 매개 변수 목록에는 호출 코드에서 전달한 값에 대한 값 매개 변수가 하나 이상 포함되어야 합니다.  이 값 매개 변수의 기본 이름은 `Value`이지만 필요에 따라 다른 이름을 사용할 수 있습니다.  값 매개 변수의 데이터 형식은 속성 자체의 데이터 형식과 동일해야 합니다.  
  
3.  속성에 값을 저장하는 코드 문을 `Set` 문과 `End Set` 문 사이에 삽입합니다.  이 코드에는 속성 값의 유효성 검사와 저장 외에도 그 밖의 계산 및 데이터 조작 과정이 포함될 수 있습니다.  
  
4.  값 매개 변수를 사용하여 호출 코드에서 제공된 값을 적용합니다.  이 값을 대입문으로 직접 저장하거나, 저장할 내부 값을 계산하는 식에 사용할 수 있습니다.  
  
 읽기\/쓰기 속성과 쓰기 전용 속성에 대한 `Set` 프로시저를 작성해야 합니다.  읽기 전용 속성에 대한 `Set` 프로시저는 정의할 수 없습니다.  
  
## 예제  
 다음 예제에서는 전체 이름\(fullname\)을 두 부분, 즉 이름\(firstname\)과 성\(lastname\)으로 저장하는 읽기\/쓰기 속성을 만듭니다.  호출 코드에서 `fullName`을 만나면 `Get` 프로시저는 두 부분으로 된 이름을 결합하여 전체 이름\(fullname\)을 반환합니다.  호출 코드에서 전체 이름\(fullname\)을 새로 지정하면 `Set` 프로시저가 이 이름을 두 부분으로 나눕니다.  공백이 없으면 전체 이름\(fullname\)이 이름\(firstname\)으로 저장됩니다.  
  
 [!code-vb[VbVbcnProcedures#8](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-create-a-property_1.vb)]  
  
 다음 예제에서는 `fullName`의 property 프로시저를 호출하는 일반적인 방법을 보여 줍니다.  첫 번째 호출에서는 속성 값을 설정하고 두 번째 호출에서는 해당 값을 가져옵니다.  
  
 [!code-vb[VbVbcnProcedures#9](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-create-a-property_2.vb)]  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [How to: Declare a Property with Mixed Access Levels](../Topic/How%20to:%20Declare%20a%20Property%20with%20Mixed%20Access%20Levels%20\(Visual%20Basic\).md)   
 [How to: Call a Property Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [How to: Put a Value in a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [How to: Get a Value from a Property](../Topic/How%20to:%20Get%20a%20Value%20from%20a%20Property%20\(Visual%20Basic\).md)