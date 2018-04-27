---
title: '방법: Visual Basic에서 기본 속성 선언 및 호출'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9c4f471eba42e47d6bef45a4d38abc0cbd2d32bc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>방법: Visual Basic에서 기본 속성 선언 및 호출
A *기본 속성* 지정 하지 않고 코드에 액세스할 수 있는 클래스 또는 구조체 속성입니다. 코드 이름을 호출 하는 경우 클래스 또는 구조 하지만 하지는 속성 및 컨텍스트 속성에 대 한 액세스를 허용, Visual Basic 있을 경우 해당 클래스 또는 구조체의 기본 속성에 대 한 액세스를 확인 합니다.  
  
 클래스 또는 구조체 수 최대 하나의 기본 속성이 있어야 합니다. 그러나 기본 속성을 오버 로드 수 있으며 버전을 여러 개 있을 수 있습니다.  
  
 자세한 내용은 참조 [기본](../../../../visual-basic/language-reference/modifiers/default.md)합니다.  
  
### <a name="to-declare-a-default-property"></a>기본 속성을 선언 하려면  
  
1.  일반적인 방법으로 속성을 선언 합니다. 지정 하지 않으면는 `Shared` 또는 `Private` 키워드입니다.  
  
2.  포함 된 `Default` 속성 선언에서 키워드입니다.  
  
3.  속성에 대 한 하나 이상의 매개 변수를 지정 합니다. 하나 이상의 인수를 사용 하지 않는 기본 속성을 정의할 수 없습니다.  
  
     [!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### <a name="to-call-a-default-property"></a>기본 속성을 호출 하려면  
  
1.  포함 하는 클래스 또는 구조체 형식의 변수를 선언 합니다.  
  
     [!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  속성 이름은 일반적으로 포함 위치 식에서 변수 이름만을 사용 합니다.  
  
     [!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  에 인수 목록 괄호로 묶어 변수 이름을 뒤에 있습니다. 기본 속성은 하나 이상의 인수를 사용 해야 합니다.  
  
     [!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  기본 속성 값을 검색 하려면 변수 이름 또는 등호 따라 식에서 인수 목록과 함께 사용 하 여 (`=`) 대입문에 로그인 합니다.  
  
     [!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  기본 속성 값을 설정 하려면 대입문의 왼쪽에는 인수 목록을 사용 하 여 변수 이름으로 사용 합니다.  
  
     [!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  다른 속성에 액세스 하려면 수행한 것 처럼 항상 기본 속성 이름은 변수 이름과 함께 지정할 수 있습니다.  
  
     [!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 클래스에 기본 속성을 선언 합니다.  
  
 [!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 기본 속성을 호출 하는 방법을 `myProperty` 클래스에 `class1`합니다. 에 값을 저장 하는 세 개의 대입문 `myProperty`, 및 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 통화 값을 읽습니다.  
  
 [!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 기본 속성의 가장 일반적으로 사용 되는 <xref:Microsoft.VisualBasic.Collection.Item%2A> 다양 한 컬렉션 클래스는 속성입니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 기본 속성 소스 코드 문자가 약간 저하 될 수 있지만 코드를 읽기 더 어렵게 만들 수 있습니다. 클래스 또는 구조체 이름에 대 한 참조는 시 호출 코드에서 클래스 또는 구조체에 익숙하지 않은 경우 않아야 특정 참조 하는 클래스 또는 구조체를 자체 또는 기본 속성에 액세스 하는지 여부입니다. 컴파일러 오류 또는 미묘한 런타임에 논리 오류가 발생할 수 있습니다.  
  
 항상 사용 하 여 기본 속성 오류의 가능성을 어느 정도 줄일 수 있습니다는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 컴파일러 형식 검사를 설정 하려면 `On`합니다.  
  
 에서 사용 하는 미리 정의 된 클래스 또는 구조체 코드를 결정 해야 기본 속성이 여부와 그럴 경우 계획 이라면 해당 이름이 무엇 인지 합니다.  
  
 이러한 단점으로 인해 기본 속성을 정의 하지 않는 고려해 야 합니다. 코드의 가독성을 높이기 위해 또한 항상 모든 속성에 명시적으로 참조를 고려 해야, 심지어 기본 속성 키를 누릅니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 프로시저](./property-procedures.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [기본](../../../../visual-basic/language-reference/modifiers/default.md)  
 [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md)  
 [방법: 속성 만들기](./how-to-create-a-property.md)  
 [방법: 액세스 수준이 혼합된 속성 선언](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [방법: 속성 프로시저 호출](./how-to-call-a-property-procedure.md)  
 [방법: 속성 값 입력](./how-to-put-a-value-in-a-property.md)  
 [방법: 속성에서 값 가져오기](./how-to-get-a-value-from-a-property.md)
