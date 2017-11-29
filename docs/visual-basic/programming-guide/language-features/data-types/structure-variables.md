---
title: "구조체 변수(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef42c44de84caffde909eb2b3e9361016a6abb97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="structure-variables-visual-basic"></a>구조체 변수(Visual Basic)
구조를 만든 후에 해당 형식으로 프로시저 수준 및 모듈 수준 변수를 선언할 수 있습니다. 예를 들어 컴퓨터 시스템에 대 한 정보를 기록 하는 구조를 만들 수 있습니다. 다음은 이에 대한 예입니다.  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 해당 형식의 변수를 선언할 수 있습니다. 다음 선언은이입니다.  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  클래스와 모듈에서 선언 된 구조체를 사용 하 여 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 기본적으로 공용 액세스 합니다. 구조체를 전용으로 지정 하려는 경우 사용 하 여 선언 있는지 확인은 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 키워드입니다.  
  
## <a name="access-to-structure-values"></a>구조 값에 대 한 액세스  
 지정 하 고 구조체 변수의 요소에서 값을 검색을 설정 하 고 개체에서 속성을 사용 하 여 동일한 구문을 사용 합니다. 멤버 액세스 연산자를 배치 (`.`) 구조 변수 이름 사이 요소 이름입니다. 다음 예제에서는 액세스 요소 형식으로 이전에 선언 된 변수의 `systemInfo`합니다.  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a>구조체 변수 할당  
 둘 다 동일한 구조체 형식 경우 다른 하나의 변수를 할당할 수도 있습니다. 이 다른의 해당 요소를 한 구조체의 모든 요소를 복사합니다. 다음 선언은이입니다.  
  
```  
yourSystem = mySystem  
```  
  
 구조 요소 인지 참조 형식이 같은 `String`, `Object`, 또는 데이터에 대 한 포인터 배열에 복사 됩니다. 이전 예제의 경우 `systemInfo` 앞의 예제에서 포인터 복사 하는 다음 개체 변수에 포함 된 `mySystem` 를 `yourSystem`, 및 액세스할 때 한 구조를 통해 개체의 데이터의 변경 내용이 적용 됩니다 통해 다른 구조입니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [복합 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [구조체](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [방법: 구조체 선언](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [구조체 및 기타 프로그래밍 요소](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [구조체와 클래스](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Structure 문](../../../../visual-basic/language-reference/statements/structure-statement.md)
