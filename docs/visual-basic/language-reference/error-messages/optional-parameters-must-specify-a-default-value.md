---
title: 선택적 매개 변수는 기본값을 지정해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 6788a7908489591e266af6d141006f2aa2d0e6f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="optional-parameters-must-specify-a-default-value"></a>선택적 매개 변수는 기본값을 지정해야 합니다.
선택적 매개 변수는 프로시저 호출에서 매개 변수가 없는 제공 하는 경우 사용할 수 있는 기본 값을 제공 해야 합니다.  
  
 **오류 ID:** BC30812  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   선택적 매개 변수;에 대 한 기본값을 지정 합니다. 예를 들어:  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [선택 사항](../../../visual-basic/language-reference/modifiers/optional.md)
