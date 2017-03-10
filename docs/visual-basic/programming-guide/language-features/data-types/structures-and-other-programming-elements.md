---
title: "Structures and Other Programming Elements (Visual Basic) | Microsoft Docs"
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
  - "structures, arrays"
  - "procedures, structures as arguments to"
  - "objects [Visual Basic], structure elements"
  - "arrays [Visual Basic], structure elements"
  - "nested structures"
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Structures and Other Programming Elements (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

구조체를 상호 간에 사용할 수 있을 뿐만 아니라 구조체를 배열, 개체 및 프로시저와 함께 사용할 수도 있습니다.  상호 작용에는 이 요소들이 개별적으로 사용하는 것과 동일한 구문이 사용됩니다.  
  
> [!NOTE]
>  구조체 선언에서는 구조체 요소를 초기화할 수 없습니다.  또한 구조체 형식으로 선언된 변수의 요소에만 값을 할당할 수 있습니다.  
  
## 구조체와 배열  
 구조체는 배열을 요소로 포함할 수 있습니다.  다음은 이에 대한 예입니다.  
  
```vb#  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure   
```  
  
 개체의 속성에 액세스할 때와 동일한 방법으로 구조체 내의 배열 값에 액세스할 수 있습니다.  다음은 이에 대한 예입니다.  
  
```vb#  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 구조체의 배열을 선언할 수도 있습니다.  다음은 이에 대한 예입니다.  
  
```vb#  
Dim allSystems(100) As systemInfo  
```  
  
 동일한 규칙에 따라 이 데이터 아키텍처의 구성 요소에 액세스할 수 있습니다.  다음은 이에 대한 예입니다.  
  
```vb#  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## 구조체와 개체  
 구조체는 개체를 요소로 포함할 수 있습니다.  다음은 이에 대한 예입니다.  
  
```vb#  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 이러한 선언에서는 `Object` 대신 특정 개체 클래스를 사용해야 합니다.  
  
## 구조체와 프로시저  
 구조체를 프로시저 인수로 전달할 수 있습니다.  다음은 이에 대한 예입니다.  
  
```vb#  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 위 예제에서는 *참조로* 구조체를 전달합니다. 즉, 프로시저가 구조체의 요소를 수정하여 호출 코드를 변경할 수 있습니다.  구조체를 이러한 수정으로부터 보호하려면 값으로 구조체를 전달합니다.  
  
 `Function` 프로시저로부터 구조체를 반환할 수도 있습니다.  다음은 이에 대한 예입니다.  
  
```vb#  
Dim allSystems(100) As systemInfo  
Function findByDate(ByVal searchDate As Date) As systemInfo  
    Dim i As Integer  
    For i = 1 To 100  
        If allSystems(i).purchaseDate = searchDate Then Return allSystems(i)  
    Next i  
   ' Process error: system with desired purchase date not found.  
End Function  
```  
  
## 구조체 안의 구조체  
 구조체는 다른 구조체를 포함할 수 있습니다.  다음은 이에 대한 예입니다.  
  
```vb#  
Public Structure driveInfo  
    Public type As String  
    Public size As Long  
End Structure  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As driveInfo  
    Public purchaseDate As Date  
End Structure  
```  
  
```vb#  
Dim allSystems(100) As systemInfo  
ReDim allSystems(1).diskDrives(3)  
allSystems(1).diskDrives(0).type = "Floppy"  
```  
  
 이 기법을 사용하여 구조체 안의 한 모듈에 정의된 구조체를 다른 모듈에 정의된 구조체 안으로 캡슐화할 수 있습니다.  
  
 구조체는 다른 구조체를 중첩해서 포함할 수 있습니다.  
  
## 참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Structure Variables](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)   
 [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)   
 [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)