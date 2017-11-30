---
title: "방법: 정규화 경로가 긴 개체에 대한 액세스 속도 개선(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5d91eeaeb034a4c8b4fefcffdf2fdebe72127d66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>방법: 정규화 경로가 긴 개체에 대한 액세스 속도 개선(Visual Basic)
여러 메서드 및 속성의 정규화 경로가 필요로 하는 개체를 자주 액세스 하는 경우 있습니다 속도를 높일 수 코드 정규화 된 경로 반복 하지 않음으로써 합니다.  
  
 두 가지 방법으로 반복 되는 정규화 된 경로 방지할 수 있습니다. 개체를 변수에 할당할 수 있습니다 또는에서 사용할 수는 `With`... `End With` 블록입니다.  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a>속도를 높이기 위해 액세스를 과도 하 게 정규화 된 개체를 변수에 할당 하 여  
  
1.  자주 액세스 하는 개체 유형의 변수를 선언 합니다. 선언의 초기화 부분에 정규화 된 경로 지정 합니다.  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  변수를 사용 하 여 개체의 멤버에 액세스할 수 있습니다.  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a>속도를 높이기 위해 액세스를 과도 하 게 정규화 된 개체는 With를 사용 하 여... End With 블록  
  
1.  정규화 된 경로에 배치 된 `With` 문.  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  내부 개체의 멤버 액세스는 `With` 차단 하기 전에 `End With` 문.  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [With...End With 문](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
