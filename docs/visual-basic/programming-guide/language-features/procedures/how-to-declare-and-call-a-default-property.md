---
title: "How to: Declare and Call a Default Property in Visual Basic | Microsoft Docs"
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
  - "defaults, properties"
  - "properties [Visual Basic], default"
  - "procedures, defining"
  - "default properties, in Visual Basic"
  - "Visual Basic code, procedures"
  - "Visual Basic code, properties"
  - "default properties"
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# How to: Declare and Call a Default Property in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

*기본 속성*은 지정하지 않은 상태에서 코드에서 액세스할 수 있는 클래스 또는 구조체 속성입니다.  호출 코드에서 클래스나 구조체의 이름을 지정하지만 속성의 이름이 지정되지 않았으며 컨텍스트에서 속성에 대한 액세스가 허용할 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]은 해당 클래스나 구조체의 기본 속성\(있을 경우\)에 대한 액세스를 확인합니다.  
  
 클래스나 구조체는 하나의 기본 속성만 가질 수 있습니다.  그러나 기본 속성을 오버로드할 수 있으며 여러 버전의 기본 속성을 가질 수 있습니다.  
  
 자세한 내용은 [Default](../../../../visual-basic/language-reference/modifiers/default.md)을 참조하십시오.  
  
### 기본 속성을 선언하려면  
  
1.  일반적인 방법으로 속성을 선언합니다.  `Shared` 또는 `Private` 키워드를 지정하지 마십시오.  
  
2.  속성 선언에 `Default` 키워드를 포함합니다.  
  
3.  속성에 대한 매개 변수를 적어도 하나 이상 지정합니다.  적어도 하나 이상의 인수를 갖지 않는 기본 속성은 정의할 수 없습니다.  
  
     [!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### 기본 속성을 호출하려면  
  
1.  포함하는 클래스 또는 구조체 형식의 변수를 선언합니다.  
  
     [!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  일반적으로 속성 이름을 포함하는 식에는 변수 이름만 사용합니다.  
  
     [!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  변수 이름 다음에 인수 목록을 괄호로 묶어 지정합니다.  기본 속성은 적어도 하나 이상의 인수를 가져야 합니다.  
  
     [!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  기본 속성 값을 검색하려면 식에서 인수 목록과 함께 변수 이름을 사용하거나 대입문에서 등호\(`=`\) 기호 다음에 변수 이름을 사용합니다.  
  
     [!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  기본 속성 값을 설정하려면 대입문의 왼쪽에서 변수 이름과 함께 인수 목록을 사용합니다.  
  
     [!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  다른 속성에 액세스할 때와 마찬가지로 항상 기본 속성 이름을 변수 이름과 함께 지정할 수 있습니다.  
  
     [!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## 예제  
 다음 예제에서는 클래스에서 기본 속성을 선언합니다.  
  
 [!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## 예제  
 다음 예제에서는 기본 속성 `myProperty`를 `class1` 클래스에서 호출하는 방법을 보여 줍니다.  세 개의 대입문은 값을 `myProperty`에 저장하고 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 호출은 이러한 값을 읽습니다.  
  
 [!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 기본 속성이 사용되는 가장 일반적인 경우는 다양한 컬렉션 클래스의 <xref:Microsoft.VisualBasic.Collection.Item%2A> 속성입니다.  
  
## 강력한 프로그래밍  
 기본 속성을 사용하면 소스 코드 문자 수가 약간 줄어들 수 있지만 코드를 읽기가 더 어려워질 수 있습니다.  호출하는 코드에서 사용자의 클래스나 구조체를 잘 모르는 데 클래스나 구조체 이름을 참조하는 경우 해당 참조가 클래스나 구조체 자체를 참조하는지, 아니면 기본 속성을 참조하는지 확실히 알 수 없습니다.  이 경우에는 컴파일러 오류나 모호한 런타임 논리 오류가 발생할 수 있습니다.  
  
 항상 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)을 사용하여 컴파일러 형식 검사를 `On`으로 설정하면 기본 속성 오류가 발생할 가능성을 다소 줄일 수 있습니다.  
  
 코드에서 미리 정의된 클래스나 구조체를 사용할 계획이라면 기본 속성을 갖고 있는지, 갖고 있다면 이름이 무엇인지 확인해야 합니다.  
  
 이러한 단점으로 인해서 기본 속성을 정의하지 않는 것을 고려할 필요가 있습니다.  또한 코드 가독성을 위해 모든 속성, 심지어 기본 속성까지도 항상 명시적으로 참조하는 것을 고려해야 합니다.  
  
## 참고 항목  
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Default](../../../../visual-basic/language-reference/modifiers/default.md)   
 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [How to: Create a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [How to: Declare a Property with Mixed Access Levels](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [How to: Call a Property Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [How to: Put a Value in a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [How to: Get a Value from a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)