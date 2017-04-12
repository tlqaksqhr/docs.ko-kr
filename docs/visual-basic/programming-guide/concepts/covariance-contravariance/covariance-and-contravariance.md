---
title: "공 분산과 반공 분산 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 59224c46-9931-466b-8c6e-3648c3e609c6
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
ms.openlocfilehash: b785e298c5ba38a8e3d8cc549b2dcf2df1ef6bd8
ms.lasthandoff: 03/13/2017

---
# <a name="covariance-and-contravariance-visual-basic"></a>공 분산과 반공 분산 (Visual Basic)
Visual Basic의 공 분산과 반공 분산을 사용 하도록 설정 배열 형식, 대리자 형식 및 제네릭 형식 인수에 대 한 암시적 참조 변환 합니다. 할당 호환성을 유지 하는 공변성 (covariance) 및 반 공변성 것를 반대로 바꿉니다.  
  
 다음 코드에서는 할당 호환성, 공 분산과 반공 분산의 차이 보여 줍니다.  
  
```vb  
' Assignment compatibility.   
Dim str As String = "test"  
' An object of a more derived type is assigned to an object of a less derived type.   
Dim obj As Object = str  
  
' Covariance.   
Dim strings As IEnumerable(Of String) = New List(Of String)()  
' An object that is instantiated with a more derived type argument   
' is assigned to an object instantiated with a less derived type argument.   
' Assignment compatibility is preserved.   
Dim objects As IEnumerable(Of Object) = strings  
  
' Contravariance.             
' Assume that there is the following method in the class:   
' Shared Sub SetObject(ByVal o As Object)  
' End Sub  
Dim actObject As Action(Of Object) = AddressOf SetObject  
  
' An object that is instantiated with a less derived type argument   
' is assigned to an object instantiated with a more derived type argument.   
' Assignment compatibility is reversed.   
Dim actString As Action(Of String) = actObject  
```  
  
 배열에 대 한 공변성 (covariance)에 더 적게 파생 된 형식의 배열에 더 많이 파생 된 형식의 배열로 암시적 변환할 수 있습니다. 하지만 다음 코드 예제와 같이이 작업은 형식이 안전한 아닙니다.  
  
```vb  
Dim array() As Object = New String(10) {}  
' The following statement produces a run-time exception.  
' array(0) = 10  
```  
  
 메서드 그룹에 대 한 지원을 공 분산과 반공 분산 메서드 시그니처를 대리자 형식과 일치 시킬 수 있습니다. 이 통해 대리자 형식에 지정 된 것 보다 더 적은 파생 형식을 (반공 분산)는 매개 변수를 적용할 뿐만 아니라 서명, 뿐만 아니라 형식 (공 분산) 또는 더 많이 파생 된 반환 하는 메서드를 일치 하는 메서드를 대리자에 할당할 수 있습니다. 자세한 내용은 참조 [대리자 (Visual Basic)에 대 한 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) 및 [대리자 (Visual Basic)에서 사용 하 여 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)합니다.  
  
 다음 코드 예제에서는 공 분산과 반공 분산 메서드 그룹에 대 한 지원  
  
```vb  
Shared Function GetObject() As Object  
    Return Nothing  
End Function  
  
Shared Sub SetObject(ByVal obj As Object)  
End Sub  
  
Shared Function GetString() As String  
    Return ""  
End Function  
  
Shared Sub SetString(ByVal str As String)  
  
End Sub  
  
Shared Sub Test()  
    ' Covariance. A delegate specifies a return type as object,  
    ' but you can assign a method that returns a string.  
    Dim del As Func(Of Object) = AddressOf GetString  
  
    ' Contravariance. A delegate specifies a parameter type as string,  
    ' but you can assign a method that takes an object.  
    Dim del2 As Action(Of String) = AddressOf SetObject  
End Sub  
```  
  
 .NET Framework 4 또는 이후 Visual Basic에서 제네릭 인터페이스 및 대리자의 공 분산과 반공 분산을 지원 하 고 제네릭 형식 매개 변수는 암시적 변환을 허용 합니다. 자세한 내용은 참조 [제네릭 인터페이스 (Visual Basic)에 대 한 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) 및 [대리자 (Visual Basic)에 대 한 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)합니다.  
  
 다음 코드 예제에는 제네릭 인터페이스에 대 한 암시적 참조 변환을 보여 줍니다.  
  
```vb  
Dim strings As IEnumerable(Of String) = New List(Of String)  
Dim objects As IEnumerable(Of Object) = strings  
```  
  
 제네릭 인터페이스 또는 대리자 라고 *variant* 제네릭 매개 변수는 공변 (covariant)를 선언 하는 경우 또는 반공 변입니다. Visual Basic을 사용 하면 사용자 고유의 variant 인터페이스 및 대리자를 만들 수 있습니다. 자세한 내용은 참조 [만드는 Variant 제네릭 인터페이스 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) 및 [대리자 (Visual Basic)에 대 한 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)합니다.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[(Visual Basic) 제네릭 인터페이스의 가변성](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)|제네릭 인터페이스의 공분산 및 반공분산에 대해 설명하고 .NET Framework의 Variant 제네릭 인터페이스의 목록을 제공합니다.|  
|[Variant 제네릭 인터페이스 만들기 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)|사용자 지정 variant 인터페이스를 만드는 방법을 보여 줍니다.|  
|[(Visual Basic) 제네릭 컬렉션 용 인터페이스의 가변성 사용](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)|공 분산과 반공 분산에 지원 하는 방법을 보여 줍니다.는 <xref:System.Collections.Generic.IEnumerable%601>및 <xref:System.IComparable%601>인터페이스 코드를 다시 사용 하는 데 도움이 수 있습니다.</xref:System.IComparable%601> </xref:System.Collections.Generic.IEnumerable%601>|  
|[(Visual Basic) 대리자의 가변성](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)|제네릭 및 제네릭이 아닌 대리자의 공변성과 반 공변성을 설명 하 고.NET Framework의 변형 제네릭 대리자의 목록을 제공 합니다.|  
|[(Visual Basic) 대리자의 가변성 사용](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)|메서드 시그니처를 대리자 형식과 일치 제네릭이 아닌 대리자의 공 분산과 반공 분산 지원 기능을 사용 하는 방법을 보여 줍니다.|  
|[Func 및 Action 제네릭 대리자 (Visual Basic)에 대 한 분산을 사용 하 여](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)|공 분산과 반공 분산에 지원 하는 방법을 보여 줍니다.는 `Func` 및 `Action` 대리자 코드를 다시 사용 하는 데 도움이 수 있습니다.|
