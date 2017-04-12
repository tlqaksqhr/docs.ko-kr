---
title: "사용자 지정 특성 (Visual Basic) 만들기 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1aa97a591fdbdfab931a8b5e4f70ec3c00762332
ms.lasthandoff: 03/13/2017

---
# <a name="creating-custom-attributes-visual-basic"></a>사용자 지정 특성 (Visual Basic) 만들기
특성 클래스에서 직접 또는 간접적으로 파생 되는 클래스를 정의 하 여 사용자 지정 특성을 만들 수 있습니다 <xref:System.Attribute>, 식별 하는 쉽고 빠르게 메타 데이터의 특성 정의가 있습니다.</xref:System.Attribute> 이름으로 형식을 작성 하는 프로그래머의 태그 형식으로 한다고 가정 합니다. 사용자 지정을 정의할 수 있습니다 `Author` 클래스에 특성:  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
        version = 1.0  
    End Sub  
End Class  
```  
  
 클래스 이름은 특성의 이름이 `Author`합니다. 파생 된 `System.Attribute`이므로 사용자 지정 특성 클래스입니다. 생성자의 매개 변수는 사용자 지정 특성의 위치 매개 변수입니다. 이 예제에서는 `name` 위치 매개 변수입니다. 모든 공용 읽기 / 쓰기 필드 또는 속성에는 매개 변수 이름이 지정 됩니다. 이 경우 `version` 은 유일한 명명 된 매개 변수입니다. 사용 하 여는 `AttributeUsage` 특성 확인을 `Author` 특성 클래스에 대해서만 유효 하 고 `Structure` 선언 합니다.  
  
 이 새 특성을 다음과 같이 사용할 수 있습니다.  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 `AttributeUsage`명명 된 매개 변수가 `AllowMultiple`, 있는 하거나 설정할 수 있습니다 사용자 지정 특성 일회용 다용도 사용 합니다. 다음 코드 예제에서는 다용도 특성이 만들어집니다.  
  
```vb  
' multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
```  
  
 다음 코드 예제에서는 동일한 형식의 여러 특성 클래스에 적용 됩니다.  
  
```vb  
<Author("P. Ackerman", Version:=1.1),   
Author("R. Koch", Version:=1.2)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
    ' R. Koch's code goes here...  
End Class  
```  
  
> [!NOTE]
>  특성 클래스 속성을 포함 하는 경우 해당 속성에는 읽기 / 쓰기 여야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Reflection></xref:System.Reflection>   
 [Visual Basic 프로그래밍 가이드](../../../../visual-basic/programming-guide/index.md)   
 [사용자 지정 특성 작성](http://msdn.microsoft.com/library/97216f69-bde8-49fd-ac40-f18c500ef5dc)   
 [리플렉션 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [특성 (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)   
 [(Visual Basic) 리플렉션을 사용 하 여 특성 액세스](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)   
 [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
