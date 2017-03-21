---
title: "방법: 특성 (Visual Basic)를 사용 하 여 C + + 공용 구조체 만들기 | Microsoft 문서"
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
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3ff1686328630b233b25839c79d0009d48aab5ab
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a>방법: 특성 (Visual Basic)를 사용 하 여 C/c + + 공용 구조체 만들기
특성을 사용 하 여 구조체 레이아웃 하는 방법 메모리에 사용자 지정할 수 있습니다. 이것이 C/c + +에서 공용 구조체를 사용 하 여 만들 수는 예를 들어는 `StructLayout(LayoutKind.Explicit)` 및 `FieldOffset` 특성입니다.  
  
## <a name="example"></a>예제  
 이 코드 세그먼트의 필드를 모두에서 `TestUnion` 메모리의 같은 위치에서 시작 합니다.  
  
```vb  
' Add an Imports statement for System.Runtime.InteropServices.  
  
<System.Runtime.InteropServices.StructLayout(   
      System.Runtime.InteropServices.LayoutKind.Explicit)>   
Structure TestUnion  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public i As Integer  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public d As Double  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public c As Char  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public b As Byte  
End Structure  
```  
  
## <a name="example"></a>예제  
 다음은 또 다른 예 각 다른 필드의 시작 위치를 명시적으로 설정 합니다.  
  
```vb  
' Add an Imports statement for System.Runtime.InteropServices.  
  
 <System.Runtime.InteropServices.StructLayout(   
      System.Runtime.InteropServices.LayoutKind.Explicit)>   
Structure TestExplicit  
     <System.Runtime.InteropServices.FieldOffset(0)>   
     Public lg As Long  
  
     <System.Runtime.InteropServices.FieldOffset(0)>   
     Public i1 As Integer  
  
     <System.Runtime.InteropServices.FieldOffset(4)>   
     Public i2 As Integer  
  
     <System.Runtime.InteropServices.FieldOffset(8)>   
     Public d As Double  
  
     <System.Runtime.InteropServices.FieldOffset(12)>   
     Public c As Char  
  
     <System.Runtime.InteropServices.FieldOffset(14)>   
     Public b As Byte  
 End Structure  
```  
  
 두 개의 정수 필드 `i1` 및 `i2`와 동일한 메모리 위치를 공유 `lg`합니다. 이러한 종류의 구조체 레이아웃에 대 한 제어는 플랫폼 호출을 사용 하는 경우 유용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Reflection></xref:System.Reflection>   
 <xref:System.Attribute></xref:System.Attribute>   
 [Visual Basic 프로그래밍 가이드](../../../../visual-basic/programming-guide/index.md)   
 [특성](https://msdn.microsoft.com/library/5x6cd29c)   
 [리플렉션 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [특성 (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)   
 [사용자 지정 특성 (Visual Basic) 만들기](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)   
 [(Visual Basic) 리플렉션을 사용 하 여 특성 액세스](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
