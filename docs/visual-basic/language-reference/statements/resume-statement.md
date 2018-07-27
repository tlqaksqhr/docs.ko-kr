---
title: Resume 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Resume
- vb.ResumeNext
helpviewer_keywords:
- Next statement [Visual Basic], Resume
- Resume Next statement [Visual Basic]
- execution [Visual Basic], resuming
- run-time errors [Visual Basic], resuming after
- Resume statement [Visual Basic], syntax
- errors [Visual Basic], resuming after
- Error statement [Visual Basic], and Resume statement
- execution
- Resume statement [Visual Basic]
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
ms.openlocfilehash: 853f3fe060b70c8a43957d3c843fb95539981679
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2018
ms.locfileid: "39296158"
---
# <a name="resume-statement"></a>Resume 문
오류 처리 루틴을 완료 된 후 실행을 다시 시작 합니다.  
  
 구조화 되지 않은 예외 처리를 사용 하기 보다는 가능 하면 코드에서 구조적된 예외 처리를 사용 하는 것이 좋습니다 하며 `On Error` 고 `Resume` 문입니다. 자세한 내용은 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.  
  
## <a name="syntax"></a>구문  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a>요소  
 `Resume`  
 필수. 오류 처리기로 동일한 프로시저에 오류가 발생 한 경우 오류를 발생 시킨 문을 사용 하 여 실행을 다시 시작 합니다. 호출된 된 프로시저에서 오류가 발생 한 경우 오류 처리 루틴을 포함 하는 프로시저에서 마지막으로 호출한 문에서 실행을 다시 시작 합니다.  
  
 `Next`  
 선택 사항입니다. 오류 처리기로 동일한 프로시저에 오류가 발생 한 경우 오류를 발생 시킨 문 바로 다음 문으로 실행을 다시 시작 합니다. 오류 처리 루틴을 포함 하는 프로시저에서 마지막으로 호출 하는 문 바로 다음 문으로 실행을 다시 시작 호출된 된 프로시저에서 오류가 발생 하는 경우 (또는 `On Error Resume Next` 문).  
  
 `line`  
 선택 사항입니다. 에 필요한 지정 된 줄에서 실행을 다시 시작할 `line` 인수입니다. `line` 인수 줄 레이블 또는 줄 번호 및 오류 처리기와 동일한 절차에 있어야 합니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  구조화 되지 않은 예외 처리를 사용 하기 보다는 가능 하면 코드에서 구조적된 예외 처리를 사용 하는 것이 좋습니다 하며 `On Error` 고 `Resume` 문입니다. 자세한 내용은 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.  
  
 사용 하는 경우는 `Resume` 문을 아무 곳 이나 이외의 다른 오류 처리 루틴에서 오류가 발생 합니다.  
  
 합니다 `Resume` 문을 포함 하는 모든 프로시저에 사용할 수 없습니다는 `Try...Catch...Finally` 문입니다.  
  
## <a name="example"></a>예  
 이 예제에서는 `Resume` 문을 프로시저의 오류 처리를 종료 하 고 오류를 발생 시킨 문 사용 하 여 실행을 다시 시작 합니다. 오류 번호 55 사용을 설명 하기 위해 생성 되는 `Resume` 문입니다.  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## <a name="requirements"></a>요구 사항  
 **: Namespace** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **어셈블리:** Visual Basic 런타임 라이브러리 (Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>참고 항목  
 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Error 문](../../../visual-basic/language-reference/statements/error-statement.md)  
 [On Error 문](../../../visual-basic/language-reference/statements/on-error-statement.md)
