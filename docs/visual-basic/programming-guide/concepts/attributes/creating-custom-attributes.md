---
title: 사용자 지정 특성 (Visual Basic) 만들기
ms.date: 07/20/2015
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
ms.openlocfilehash: 9af0832e04308bf1942fc955afe5a67161096465
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="creating-custom-attributes-visual-basic"></a>사용자 지정 특성 (Visual Basic) 만들기
메타데이터에서 특성 정의를 빠르고 쉽게 식별할 수 있도록 하는 <xref:System.Attribute>에서 직접 또는 간접적으로 파생되는 특성 클래스를 정의하여 자체 사용자 지정 특성을 만들 수 있습니다. 형식을 작성한 프로그래머의 이름을 형식에 태그로 지정한다고 가정합니다. 사용자 지정 `Author` 특성 클래스를 정의할 수 있습니다.  
  
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
  
 클래스 이름은 특성의 이름인 `Author`입니다. 이 클래스는 `System.Attribute`에서 파생되므로 사용자 지정 특성 클래스입니다. 생성자의 매개 변수는 사용자 지정 특성의 위치 매개 변수입니다. 이 예제에서는 `name`이 위치 매개 변수입니다. 모든 public 읽기-쓰기 필드 또는 속성은 명명된 매개 변수입니다. 이 경우에는 `version`이 유일한 명명된 매개 변수입니다. 클래스 및 `Structure` 선언에서만 `Author` 특성을 유효하게 설정하려면 `AttributeUsage` 특성을 사용해야 합니다.  
  
 이 새로운 특성은 다음과 같이 사용할 수 있습니다.  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 `AttributeUsage`에는 사용자 지정 특성을 한 번 또는 여러 번 사용하도록 설정하는 데 이용하는 명명된 매개 변수인 `AllowMultiple`이 있습니다. 다음 코드 예제에서는 다중 사용 특성이 만들어집니다.  
  
```vb  
' multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
```  
  
 다음 코드 예제에서는 같은 형식의 여러 특성이 한 클래스에 적용됩니다.  
  
```vb  
<Author("P. Ackerman", Version:=1.1),   
Author("R. Koch", Version:=1.2)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
    ' R. Koch's code goes here...  
End Class  
```  
  
> [!NOTE]
>  특성 클래스에 속성이 포함되면 해당 속성은 읽기-쓰기여야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Reflection>  
 [Visual Basic 프로그래밍 가이드](../../../../visual-basic/programming-guide/index.md)  
 [사용자 지정 특성 작성](../../../../standard/attributes/writing-custom-attributes.md)  
 [리플렉션(Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)  
 [특성(Visual Basic)](../../../../visual-basic/language-reference/attributes.md)  
 [리플렉션을 사용하여 특성 액세스(Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)  
 [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
