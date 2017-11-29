---
title: "Sub 또는 Function이 정의되지 않았습니다(Visual Basic)."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6237ca26b06bdffa06499607e634b3222725c189
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub 또는 Function이 정의되지 않았습니다(Visual Basic).
A `Sub` 또는 `Function` 호출 되려면 정의 되어야 합니다. 이 오류가 발생하는 원인은 다음과 같습니다.  
  
-   프로시저 이름의 철자가 틀린 경우입니다.  
  
-   다른 프로젝트에서 명시적으로 해당 프로젝트에 대 한 참조를 추가 하지 않고 프로시저를 호출 하는 **참조** 대화 상자.  
  
-   호출 하는 프로시저로 표시 되지 않는 프로시저를 지정 합니다.  
  
-   Windows 동적 연결 라이브러리 (DLL) 루틴 또는 지정된 된 라이브러리 또는 코드 리소스에 있지 않은 Macintosh 코드 리소스 루틴을 선언 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  프로시저 이름을 제대로 입력 했는지 확인 합니다.  
  
2.  호출 하려는 프로시저를 포함 하는 프로젝트의 이름 찾기는 **참조** 대화 상자. 표시 되지 않으면 클릭는 **찾아보기** 단추를 검색 합니다. 프로젝트 이름의 왼쪽에 있는 확인란을 선택 하 고 클릭 한 다음 **확인**합니다.  
  
3.  루틴의 이름을 확인 하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [오류 형식](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)
