---
title: "How to: Dispose of a System Resource (Visual Basic) | Microsoft Docs"
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
  - "Using statement, disposing of system resources"
  - "Visual Basic code, control flow"
  - "system resources, disposing of"
  - "resources [Visual Basic], disposing of system"
  - "system resources"
  - "Using statement, Using...End Using"
  - "Using block"
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Dispose of a System Resource (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Using` 블록을 사용하면 코드에서 블록을 종료할 때 시스템에서 리소스를 해제하도록 할 수 있습니다.  이 블록은 많은 양의 메모리를 사용하거나 다른 구성 요소에서도 사용할 수 있는 시스템 리소스를 사용하는 경우에 유용합니다.  
  
### 코드가 데이터베이스 연결 상태에서 끝날 때 데이터베이스 연결을 삭제하려면  
  
1.  소스 파일의 시작 부분에 데이터베이스 연결을 위한 적절한 [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)\(이 경우 <xref:System.Data.SqlClient>\)이 포함되어 있는지 확인합니다.  
  
2.  `Using` 및 `End Using` 문을 사용하여 `Using` 블록을 만듭니다.  블록 안에 데이터베이스 연결을 처리하는 코드를 넣습니다.  
  
3.  연결을 선언하고 이 연결 인스턴스를 `Using` 문의 일부로 만듭니다.  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     시스템에서는 블록 종료 방식에 관계없이 리소스를 삭제합니다. 여기에는 처리되지 않은 예외가 발생하는 경우도 포함됩니다.  
  
     `sqc`는 범위가 `Using` 블록으로 제한되므로 이 블록의 외부에서는 액세스할 수 없습니다.  
  
     파일 핸들 또는 COM 래퍼 등의 시스템 리소스에도 동일한 기술을 사용할 수 있습니다.  `Using` 블록을 종료한 후 다른 구성 요소에서 리소스를 사용할 수 있도록 하려면 `Using` 블록을 사용합니다.  
  
## 참고 항목  
 <xref:System.Data.SqlClient.SqlConnection>   
 [Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)   
 [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md)