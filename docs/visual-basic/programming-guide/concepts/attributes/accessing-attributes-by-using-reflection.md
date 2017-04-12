---
title: "(Visual Basic) 리플렉션을 사용 하 여 특성 액세스 | Microsoft 문서"
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
ms.assetid: c56e41da-5433-464f-a7bf-2a722e78bc9f
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
ms.openlocfilehash: 4763eccc5d1a6bdf3e89c1c4d825d5ff5c6caa3e
ms.lasthandoff: 03/13/2017

---
# <a name="accessing-attributes-by-using-reflection-visual-basic"></a>(Visual Basic) 리플렉션을 사용 하 여 특성 액세스
해당 정보를 검색 하 고 작업할 방법이 없는 작은 값의 사용자 지정 특성을 정의 하 고 소스 코드에 배치할 수 있는 팩트는 것입니다. 리플렉션을 사용 하 여, 사용자 지정 특성으로 정의 된 정보를 검색할 수 있습니다. 핵심 메서드는 `GetCustomAttributes`, 소스 코드 특성의 해당 하는 런타임 실행 되는 개체의 배열을 반환 합니다. 이 메서드는 몇 가지 오버 로드 된 버전이 있습니다. 자세한 내용은 <xref:System.Attribute>.</xref:System.Attribute> 을 참조 하십시오.  
  
 와 같은 특성 사양:  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 개념적으로이에 해당 합니다.  
  
```vb  
Dim anonymousAuthorObject As Author = New Author("P. Ackerman")  
anonymousAuthorObject.version = 1.1  
```  
  
 그러나 코드에 실행 됩니다 `SampleClass` 특성에 대 한 쿼리 됩니다. 호출 `GetCustomAttributes` 에 `SampleClass` 하면는 `Author` 개체를 생성 하 고 위에서 설명한 것 처럼 초기화 합니다. 클래스에 다른 특성이 다른 특성 개체 마찬가지로 생성 됩니다. `GetCustomAttributes`그런 다음 반환 된 `Author` 배열에 다른 특성 개체와 개체입니다. 각 배열 요소의 형식에 따라 적용 된 특성을 결정 하 고 특성 개체에서 정보를 추출이 배열을 반복할 수 있습니다.  
  
## <a name="example"></a>예제  
 전체 예제는 다음과 같습니다. 사용자 지정 특성 정의 하 고 여러 엔터티에 적용 하 고 리플렉션을 통해 검색 됩니다.  
  
```vb  
' Multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
  
        ' Default value  
        version = 1.0  
    End Sub  
  
    Function GetName() As String  
        Return name  
    End Function          
End Class  
  
' Class with the Author attribute  
<Author("P. Ackerman")>   
Public Class FirstClass  
End Class  
  
' Class without the Author attribute  
Public Class SecondClass  
End Class  
  
' Class with multiple Author attributes.  
<Author("P. Ackerman"), Author("R. Koch", Version:=2.0)>   
Public Class ThirdClass  
End Class  
  
Class TestAuthorAttribute  
    Sub Main()  
        PrintAuthorInfo(GetType(FirstClass))  
        PrintAuthorInfo(GetType(SecondClass))  
        PrintAuthorInfo(GetType(ThirdClass))  
    End Sub  
  
    Private Shared Sub PrintAuthorInfo(ByVal t As System.Type)  
        System.Console.WriteLine("Author information for {0}", t)  
  
        ' Using reflection  
        Dim attrs() As System.Attribute = System.Attribute.GetCustomAttributes(t)  
  
        ' Displaying output  
        For Each attr In attrs  
            Dim a As Author = CType(attr, Author)  
            System.Console.WriteLine("   {0}, version {1:f}", a.GetName(), a.version)  
        Next              
    End Sub  
  
    ' Output:  
    '   Author information for FirstClass  
    '     P. Ackerman, version 1.00  
    ' Author information for SecondClass  
    ' Author information for ThirdClass  
    '  R. Koch, version 2.00  
    '  P. Ackerman, version 1.00  
  
End Class  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Reflection></xref:System.Reflection>   
 <xref:System.Attribute></xref:System.Attribute>   
 [Visual Basic 프로그래밍 가이드](../../../../visual-basic/programming-guide/index.md)   
 [특성에 저장 된 정보 검색](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)   
 [리플렉션 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [특성 (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)   
 [사용자 지정 특성 (Visual Basic) 만들기](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
