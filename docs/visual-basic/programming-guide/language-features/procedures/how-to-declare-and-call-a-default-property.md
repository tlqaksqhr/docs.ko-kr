---
title: "방법: 선언 하 고 Visual Basic의 기본 속성을 호출 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- procedures, defining
- default properties, in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
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
ms.openlocfilehash: ce98e7fe72a395f6c4cde481feaa60be28c6fcc3
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>방법: Visual Basic에서 기본 속성 선언 및 호출
A *기본 속성* 지정 하지 않고 코드에 액세스할 수 있는 클래스 또는 구조체 속성입니다. 클래스 또는 구조 있지만 속성이 아닌 이름을 지정 코드를 호출 하 고는 컨텍스트 속성에 대 한 액세스를 통해 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 있을 경우 해당 클래스 또는 구조체의 기본 속성에 대 한 액세스를 확인 합니다.  
  
 클래스 또는 구조체 개뿐입니다 최대 하나의 기본 속성. 그러나 기본 속성을 오버 로드할 수 있으며의 버전이 여러 개 있을 수 있습니다.  
  
 자세한 내용은 참조 [기본](../../../../visual-basic/language-reference/modifiers/default.md)합니다.  
  
### <a name="to-declare-a-default-property"></a>기본 속성을 선언 하려면  
  
1.  일반적인 방법으로 속성을 선언 합니다. 지정 하지 않으면는 `Shared` 또는 `Private` 키워드입니다.  
  
2.  포함 된 `Default` 속성 선언에는 키워드입니다.  
  
3.  속성에 대 한 하나 이상의 매개 변수를 지정 합니다. 하나 이상의 인수를 사용 하지 않는 기본 속성을 정의할 수 없습니다.  
  
     [!code-vb[VbVbcnProcedures #&17;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### <a name="to-call-a-default-property"></a>기본 속성을 호출 하려면  
  
1.  포함 하는 클래스 또는 구조체 형식의 변수를 선언 합니다.  
  
     [!code-vb[VbVbcnProcedures #&16;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  속성 이름은 일반적으로 포함 위치는 식에 변수 이름만을 사용 합니다.  
  
     [!code-vb[VbVbcnProcedures #&21;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  괄호 안에 인수 목록과 함께 변수 이름을 뒤에 있습니다. 기본 속성을 하나 이상의 인수를 사용 해야 합니다.  
  
     [!code-vb[VbVbcnProcedures #&20;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  기본 속성 값을 검색 하려면 변수 이름으로 인수 목록과 식에서 또는 등호 다음 함께 사용 하 여 (`=`) 대입문에 로그인 합니다.  
  
     [!code-vb[VbVbcnProcedures #&15;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  기본 속성 값을 설정 하려면 대입문의 왼쪽에는 인수 목록을 가진 변수 이름으로 사용 합니다.  
  
     [!code-vb[VbVbcnProcedures #&14;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  방금와 같은 다른 속성에 액세스 하려면 항상 기본 속성 이름은 변수 이름과 함께 지정할 수 있습니다.  
  
     [!code-vb[VbVbcnProcedures #&19;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 클래스에는 기본 속성을 선언합니다.  
  
 [!code-vb[VbVbcnProcedures #&12;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 기본 속성을 호출 하는 방법을 `myProperty` 클래스에 `class1`합니다. 값을 저장 하는 세 개의 대입문 `myProperty`, 및 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>통화 값을 읽습니다.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
  
 [!code-vb[VbVbcnProcedures #&13;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 기본 속성의 가장 일반적인 사용은는 <xref:Microsoft.VisualBasic.Collection.Item%2A>다양 한 컬렉션 클래스에는 속성입니다.</xref:Microsoft.VisualBasic.Collection.Item%2A>  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 기본 속성 소스 코드의 문자를 약간 저하 될 수 있지만 코드를 읽을 수 더 어렵게 만들 수 있습니다. 클래스 또는 구조체 이름에 대 한 참조를 수행할 때 호출 코드에서 클래스 또는 구조체에 익숙하지 않은 경우 수 없습니다 특정 참조 하는 클래스 또는 구조체 자체를 기본 속성에 액세스 하는지 여부. 이 경우 컴파일러 오류 또는 미묘한 런타임 논리 오류가 발생할 수 있습니다.  
  
 항상 사용 하 여 기본 속성 오류 가능성을을 다소 줄일 수는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 컴파일러 형식 검사를 설정 하려면 `On`합니다.  
  
 에서 사용 하는 미리 정의 된 클래스 또는 구조체에서 코드를 결정 해야 기본 속성이 있는지 여부 그리고 있다면 하고자 한다면 어떤 이름은입니다.  
  
 이러한 단점 때문에 기본 속성을 정의 하지 않는 고려해 야 합니다. 또한 항상 모든 속성에 명시적으로 참조를 고려해 해야 코드 가독성을 기본 속성까지 하세요.  
  
## <a name="see-also"></a>참고 항목  
 [속성 프로시저](./property-procedures.md)   
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)   
 [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [기본값](../../../../visual-basic/language-reference/modifiers/default.md)   
 [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md)   
 [방법: 속성 만들기](./how-to-create-a-property.md)   
 [방법: 액세스 수준이 혼합된 된 속성 선언](./how-to-declare-a-property-with-mixed-access-levels.md)   
 [방법: 속성 프로시저 호출](./how-to-call-a-property-procedure.md)   
 [방법: 속성 값 입력](./how-to-put-a-value-in-a-property.md)   
 [방법: 속성에서 값 가져오기](./how-to-get-a-value-from-a-property.md)
