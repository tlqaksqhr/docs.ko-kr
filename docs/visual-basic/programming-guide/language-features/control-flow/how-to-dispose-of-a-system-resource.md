---
title: '방법: 시스템 리소스 해제(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
ms.openlocfilehash: cbb66934833da2bd6f0b797944dbb9c4df267cfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647233"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>방법: 시스템 리소스 해제(Visual Basic)
사용할 수는 `Using` 블록 코드 블록을 종료할 때 시스템 리소스의 삭제 되도록 합니다. 또는 다른 구성 요소가 사용 하 여 할 많은 양의 메모리를 사용 하는 시스템 리소스를 사용 하는 경우에 유용 합니다.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>코드는 작업을 마쳤을 때 데이터베이스 연결을 삭제 하기 위해  
  
1.  적절 한 포함 되어 있는지 확인 [Imports 문 (.NET Namespace 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 소스 파일의 시작 부분에서 데이터베이스 연결에 대 한 (이 경우 <xref:System.Data.SqlClient>).  
  
2.  만들기는 `Using` 블록와 함께 `Using` 및 `End Using` 문. 블록 내의 데이터베이스 연결에서 설명 하는 코드를 입력 합니다.  
  
3.  연결을 선언 하 고의 일환으로 해당 형식의 인스턴스를 만듭니다는 `Using` 문.  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     시스템 처리 되지 않은 예외가 대/소문자를 포함 하 여 블록을 종료 하는 방법에 관계 없이 리소스를 삭제 합니다.  
  
     액세스할 수 없는 참고 `sqc` 에서 외부의 `Using` 변수 범위는 블록으로 제한 때문에 차단 합니다.  
  
     COM 래퍼 열려 있는 파일 핸들 등의 시스템 리소스에 동일한 기법을 사용할 수 있습니다. 사용 된 `Using` 블록을 종료 한 후 다른 구성 요소에 사용할 수 있는 리소스에 확실 하 게 하려는 경우는 `Using` 블록입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.SqlClient.SqlConnection>  
 [제어 흐름](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [판단 구조](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [루프 구조](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [기타 제어 구조](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [중첩 제어 구조](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Using 문](../../../../visual-basic/language-reference/statements/using-statement.md)
