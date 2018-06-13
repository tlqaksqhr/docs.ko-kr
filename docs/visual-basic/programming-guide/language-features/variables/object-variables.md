---
title: Visual Basic의 개체 변수
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: 8383261c1806732c4c8abea9834000f003a848a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649115"
---
# <a name="object-variables-in-visual-basic"></a>Visual Basic의 개체 변수
값을 직접 저장 하는 것 외에도 변수 개체를 참조할 수 있습니다. 변수에 값을 할당할 같은 이유로 변수에 개체 할당:  
  
-   변수 이름은 메서드 및 개체 자체에 액세스 하는 데 필요한 속성의 전체 경로 보다 기억 하기 쉽고 자주입니다.  
  
-   개체를 참조 하는 변수를 사용 하 여 반복 해 서 필요한 메서드 또는 속성을 통해 개체 자체를 액세스할 때 보다 더 효율적입니다.  
  
-   코드를 실행 하는 동안 다른 개체를 참조 하는 변수를 변경할 수 있습니다.  
  
## <a name="making-code-shorter"></a>코드 길이 줄이기  
 개체 변수를 입력 해야 하는 코드를 단축할 수 있습니다 사용할 수 있습니다. 다음 예제에서는 메서드 및 속성의 전체 경로 사용 하 여 액세스 하는 <xref:System.Windows.Forms.Control> 개체입니다.  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 이 코드를 줄이고 실행 속도를 높일, 컨트롤에 대 한 개체 변수를 사용 하는 경우 수 있습니다. 여기에 할당 하려는 특정 클래스와 개체 변수를 선언 해야 합니다 (`Control` 이 경우). 개체를 변수에 할당 하면으로 처리할 수 있습니다 완전히 동일 참조 하는 개체를 다룰 때와 합니다. 설정 또는 개체의 속성을 검색 하거나 해당 메서드 중 하나를 사용할 수 있습니다. 다음 예제에서는 앞의 예제에서 코드를 단순화 하는 개체 변수를 사용 합니다.  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a>참고 항목  
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [방법: 정규화 경로가 긴 개체에 대한 액세스 속도 개선](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)  
 [개체 변수 선언](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [개체 변수 할당](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [개체 변수 값](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
