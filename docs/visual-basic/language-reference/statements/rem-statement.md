---
title: "REM 문(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d64ce970e3e74437f5e8c63c8a4d578900902192
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="rem-statement-visual-basic"></a>REM 문(Visual Basic)
프로그램의 소스 코드에 설명 주석을 포함 하는 데 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a>요소  
 `comment`  
 선택 사항입니다. 포함할 주석의 텍스트입니다. 사이 공백을 않습니다는 `REM` 키워드 및 `comment`합니다.  
  
## <a name="remarks"></a>설명  
 넣을 수는 `REM` 문만 각 줄에 다른 문 다음에 줄에 넣을 수 있습니다. `REM` 문은 줄에서 마지막 문 이어야 합니다. 다른 문의 오는 경우는 `REM` 공백으로 해당 문에서 구분 되어야 합니다.  
  
 작은따옴표를 사용할 수 있습니다 (`'`) 대신 `REM`합니다. 의견 다른 문이 같은 줄에 오거나 단독 줄에 유용 합니다.  
  
> [!NOTE]
>  계속할 수 없습니다는 `REM` 줄 연속 시퀀스를 사용 하 여 문 (`_`). 주석 시작 되 면 컴파일러는 특별 한 의미에 대 한 문자를 검사 하지 않습니다. 주석이 여러 행에 대 한 다른 사용 `REM` 문이나 주석 기호 (`'`) 각 줄에 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제는 `REM` 문이 프로그램에 설명 주석을 포함 하는 데 사용 됩니다. 또한 단일 따옴표 문자를 사용 하는 방법도 보여 줍니다 (`'`) 대신 `REM`합니다.  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [코드 주석](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 [방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
