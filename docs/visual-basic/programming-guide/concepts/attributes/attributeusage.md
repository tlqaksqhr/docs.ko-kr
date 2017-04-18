---
title: "AttributeUsage (Visual Basic) | Microsoft 문서"
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
ms.assetid: 48757216-c21d-4051-86d5-8a3e03c39d2c
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
ms.openlocfilehash: bf56f40033f9d1547d63fccd25e3c0561bb62cb1
ms.lasthandoff: 03/13/2017

---
# <a name="attributeusage-visual-basic"></a>AttributeUsage (Visual Basic)
사용자 지정 특성 클래스를 사용할 수 있는 방법을 결정 합니다. `AttributeUsage`새 특성을 적용 하 하는 방법을 제어 하는 사용자 지정 특성 정의에 적용할 수 있는 특성이입니다. 기본 설정을 명시적으로 적용 하는 경우 다음과 같이 표시 됩니다.  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All,   
                   AllowMultiple:=False,   
                   Inherited:=True)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 이 예제에서는 `NewAttribute` 될 수 있는 클래스에 모든 특성 코드 엔터티에 적용 되지만 각 엔터티에 한 번만 적용할 수 있습니다. 기본 클래스에 적용 된 경우 파생된 클래스에서 상속 합니다.  
  
 `AllowMultiple` 및 `Inherited` 인수는 선택 사항 이므로이 코드는 동일한 효과가 있습니다.  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 첫 번째 `AttributeUsage` 인수 중 하나 이상의 요소가 있어야 합니다.는 <xref:System.AttributeTargets>열거형.</xref:System.AttributeTargets> 여러 개의 대상 형식은 다음과 같이 OR 연산자와 함께 연결 될 수 있습니다.  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Property Or AttributeTargets.Field)>   
Class NewPropertyOrFieldAttribute  
    Inherits Attribute  
End Class  
```  
  
 하는 경우는 `AllowMultiple` 인수가로 설정 된 `true`, 다음 다음과 같이 단일 엔터티를 결과 특성을 두 번 이상 적용할 수 있습니다.  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=True)>   
Class MultiUseAttr  
    Inherits Attribute  
End Class  
  
<MultiUseAttr(), MultiUseAttr()>   
Class Class1  
End Class  
```  
  
 이 경우 `MultiUseAttr` 때문에 반복 해 서 적용할 수 `AllowMultiple` 로 설정 된 `true`합니다. 여러 특성을 적용 하기 위해 표시 하는 두 형식을 사용할 수 있습니다.  
  
 경우 `Inherited` 로 설정 된 `false`, 다음 특성을 사용 하는 클래스에서 파생 된 클래스에 특성을 상속 하지 않습니다. 예:  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Class, Inherited:=False)>   
Class Attr1  
    Inherits Attribute  
End Class  
  
<Attr1()>   
Class BClass  
  
End Class    
  
Class DClass  
    Inherits BClass  
End Class  
```  
  
 이 경우 `Attr1` 에 적용 되지 않으면 `DClass` 상속을 통해.  
  
## <a name="remarks"></a>주의  
 `AttributeUsage` 특성은&1; 회용 특성-동일한 클래스에 두 번 이상 적용할 수 없습니다. `AttributeUsage`<xref:System.AttributeUsageAttribute>.</xref:System.AttributeUsageAttribute> 별칭은  
  
 자세한 내용은 참조 [(Visual Basic) 리플렉션을 사용 하 여 특성 액세스](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는의 효과 보여 줍니다.는 `Inherited` 및 `AllowMultiple` 에 대 한 인수는 `AttributeUsage` 특성과 어떻게 클래스에 적용 되는 사용자 지정 특성을 열거할 수 있습니다.  
  
```vb  
Imports System  
```  
  
```vb  
' Create some custom attributes:  
<AttributeUsage(System.AttributeTargets.Class, Inherited:=False)>   
Class A1  
    Inherits System.Attribute  
End Class  
  
<AttributeUsage(System.AttributeTargets.Class)>   
Class A2  
    Inherits System.Attribute  
End Class      
  
<AttributeUsage(System.AttributeTargets.Class, AllowMultiple:=True)>   
Class A3  
    Inherits System.Attribute  
End Class  
  
' Apply custom attributes to classes:  
<A1(), A2()>   
Class BaseClass  
  
End Class  
  
<A3(), A3()>   
Class DerivedClass  
    Inherits BaseClass  
End Class  
  
Public Class TestAttributeUsage  
    Sub Main()  
        Dim b As New BaseClass  
        Dim d As New DerivedClass  
        ' Display custom attributes for each class.  
        Console.WriteLine("Attributes on Base Class:")  
        Dim attrs() As Object = b.GetType().GetCustomAttributes(True)  
  
        For Each attr In attrs  
            Console.WriteLine(attr)  
        Next  
  
        Console.WriteLine("Attributes on Derived Class:")  
        attrs = d.GetType().GetCustomAttributes(True)  
        For Each attr In attrs  
            Console.WriteLine(attr)  
        Next              
    End Sub  
End Class  
```  
  
## <a name="sample-output"></a>샘플 출력  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Attribute></xref:System.Attribute>   
 <xref:System.Reflection></xref:System.Reflection>   
 [Visual Basic 프로그래밍 가이드](../../../../visual-basic/programming-guide/index.md)   
 [특성](https://msdn.microsoft.com/library/5x6cd29c)   
 [리플렉션 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [특성 (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)   
 [사용자 지정 특성 (Visual Basic) 만들기](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)   
 [(Visual Basic) 리플렉션을 사용 하 여 특성 액세스](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
