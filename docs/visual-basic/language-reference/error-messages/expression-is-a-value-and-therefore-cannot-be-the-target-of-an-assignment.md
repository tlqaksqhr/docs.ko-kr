---
title: 식이 값이므로 할당 대상일 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: dd5618bd0533f885a6aef8229b2d8cb1bc34c237
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a>식이 값이므로 할당 대상일 수 없습니다.
문에서 식에 값을 할당 하려고 했습니다. 런타임 시 쓰기 가능한 변수, 속성 또는 배열 요소에만 값을 할당할 수 있습니다. 다음 예제에서는이 오류가 발생 하는 방법을 보여 줍니다.  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 유사한 예 속성 및 배열 요소에 적용할 수 있습니다.  
  
 **간접 액세스 합니다.** 값 형식을 통해 간접적으로 액세스도이 오류를 생성할 수 있습니다. 다음 코드 예제 값을 설정 하려고 시도 하는 것이 좋습니다 <xref:System.Drawing.Point> 통해 간접적으로 액세스 하 여 <xref:System.Windows.Forms.Control.Location%2A>합니다.  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 위 예의 마지막 문이 실패에 대 한 임시 할당만을 만들기 때문에 <xref:System.Drawing.Point> 에서 반환 된 구조는 <xref:System.Windows.Forms.Control.Location%2A> 속성입니다. 구조체는 값 형식 및 문이 실행 된 후에 임시 구조 보존 되지 않습니다. 선언에 대 한 변수를 사용 하 여 문제가 해결 될 <xref:System.Windows.Forms.Control.Location%2A>에 대 한 더 영구적인 할당 만듦는 <xref:System.Drawing.Point> 구조입니다. 다음 예제에서는 앞의 예제의 마지막 문으로 대체할 수 있는 코드를 보여 줍니다.  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 **오류 ID:** BC30068  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   문이 값 식에 할당 하는 경우 단일 쓰기 가능한 변수, 속성 또는 배열 요소와 식을 대체 합니다.  
  
-   문을 통해 값 형식 (일반적으로 구조)를 통해 간접적으로 액세스를 경우 값 형식을 보유할 변수를 만듭니다.  
  
-   적절 한 구조 (또는 다른 값 형식)를 변수에 할당 합니다.  
  
-   변수를 사용 하 여 값을 할당 하는 속성에 액세스 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [문](../../../visual-basic/programming-guide/language-features/statements.md)  
 [프로시저 문제 해결](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
