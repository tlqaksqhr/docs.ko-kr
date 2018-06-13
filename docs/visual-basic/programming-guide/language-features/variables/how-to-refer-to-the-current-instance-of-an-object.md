---
title: '방법: 개체의 현재 인스턴스 참조(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: c1b79f1b6a9768941d6fe966c5b5886ea742f808
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648361"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>방법: 개체의 현재 인스턴스 참조(Visual Basic)
*현재 인스턴스가* 는 코드가 현재 실행 중인 개체입니다.  
  
 사용 된 `Me` 키워드를 현재 인스턴스를 참조 합니다.  
  
### <a name="to-refer-to-the-current-instance"></a>현재 인스턴스 참조 하려면  
  
-   사용 하 여는 `Me` 키워드 일반적으로 사용 되는 개체 변수의 이름입니다.  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     하지만 `Me` 개체 처럼 동작 변수를 선언할 수 없거나 값을 할당할 합니다. `Me` 항상 현재 인스턴스를 참조 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [개체 변수 할당](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
