---
title: '방법: 개체 변수가 인스턴스를 참조하지 않도록 설정(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: bf918b762261e1dd1fc4161a10203f3d0067e454
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649726"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>방법: 개체 변수가 인스턴스를 참조하지 않도록 설정(Visual Basic)
로 설정 하 여 개체 인스턴스에서 개체 변수를 분리할 수 [Nothing](../../../../visual-basic/language-reference/nothing.md)합니다.  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>연결을 끊을 개체 인스턴스에서 개체 변수  
  
-   이 변수를 설정 `Nothing` 대입문에서 합니다.  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 코드에 설정 된 개체 변수의 멤버에 액세스 하려고 할 경우 `Nothing`, <xref:System.NullReferenceException> 발생 합니다. 개체 변수를 설정 하면 `Nothing` 자주에서 멤버 액세스 하는 것이 좋습니다가 변수는 초기화 되지 않았습니다 가능한 경우 한 `Try...Catch...Finally` 블록입니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 기밀 또는 중요 한 데이터를 포함 하는 개체에 대 한 개체 변수를 사용 하는 경우는 변수를 설정할 수 있습니다 `Nothing` 때 처리 하지 않을 적극적으로 이러한 개체 중 하나입니다. 데이터에 액세스 하는 악성 코드의 가능성을 줄일 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.NullReferenceException>  
 [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [개체 변수 할당](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Nothing](../../../../visual-basic/language-reference/nothing.md)  
 [Try...Catch...Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [예외 문제 해결: System.NullReferenceException](http://msdn.microsoft.com/library/4822b0b4-8105-43fb-887a-3cc51ff02899)
