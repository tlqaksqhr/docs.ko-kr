---
title: "방법: 변수 값 저장 및 검색(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fefb1979e35cd7b5fa1917f8f1a57af575e51234
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>방법: 변수 값 저장 및 검색(Visual Basic)
대입문의 왼쪽에 변수 이름을 입력 하 여 변수에 값을 저장 합니다.  
  
## <a name="putting-data-in-a-variable"></a>변수에 데이터 게시  
  
#### <a name="to-store-a-value-in-a-variable"></a>변수에 값을 저장 하려면  
  
-   대입문의 왼쪽에 변수 이름을 사용 합니다.  
  
     변수의 값을 설정 하는 다음 예제에서는 `alpha`합니다.  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     대입문의 오른쪽에 생성 된 값은 변수에 저장 됩니다.  
  
## <a name="getting-data-from-a-variable"></a>변수에서 데이터 가져오기  
 식에서 변수 이름을 포함 하 여 변수의 값을 검색 합니다.  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a>변수에서 값을 검색 하려면  
  
-   식에서 변수 이름을 사용 합니다. 변수를 사용 하려면 모든 위치에서 사용할 수 있습니다 상수 또는 리터럴, 제외 하 고 상수 값을 정의 하는 식입니다.  
  
     또는  
  
-   다음에 오는 변수 이름 사용 (`=`) 대입문에 로그인 합니다.  
  
     다음 예제에서는 변수 값을 읽고 `startValue` 다음 변수 값을 사용 하 여 `counter` 식에 있습니다.  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     변수의 값은 상수 및 변수 또는 대입문의 왼쪽에 있는 속성에 저장 됩니다 하듯이 식에 참여 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [변수](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
