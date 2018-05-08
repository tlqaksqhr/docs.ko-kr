---
title: End 문
ms.date: 07/20/2015
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
ms.openlocfilehash: 864ac5ef1713f8ffa93c18accede8ecd5b3b7a8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="end-statement"></a>End 문
즉시 실행을 종료합니다.  
  
## <a name="syntax"></a>구문  
  
```  
End  
```  
  
## <a name="remarks"></a>설명  
 배치할 수 있습니다는 `End` 전체 응용 프로그램에서 실행을 중지 하려면 프로시저의 아무 곳 이나 문입니다. `End` 사용 하 여 열린 파일을 닫고 프로그램 `Open` 문을 응용 프로그램의 모든 변수를 지웁니다. 응용 프로그램을 해당 개체에 대 한 참조를 보유 하는 다른 프로그램 있으며 실행 중인 코드의 항목이 즉시 종료 합니다.  
  
> [!NOTE]
>  `End` 문을 갑자기 코드 실행이 중지 되 고 호출 하지 않습니다는 `Dispose` 또는 `Finalize` 메서드 또는 Visual Basic 코드입니다. 다른 프로그램에서의 개체 참조를 무효화 합니다. 경우는 `End` 내에서 문이 `Try` 또는 `Catch` 제어 블록에 해당 요소에 통과 하지 못하는 `Finally` 블록입니다.  
  
 `Stop` 문을 달리 하지만 실행을 일시 중단 `End`, 파일을 모두 닫고 하거나 컴파일된 실행 파일 (.exe) 파일에서 발생 하지 않는 모든 변수를 선택 취소 하지 않습니다.  
  
 때문에 `End` 처리 하지 않고 응용 프로그램을 종료 열려 있는 모든 리소스를 사용 하기 전에 완전히을 닫기 하려고 해야 합니다. 예를 들어 경우 응용 프로그램에 모든 양식을 열고 닫아야 합니다 제어가 전달 되기 전에 `End` 문.  
  
 사용 해야 `End` 만 최소화 해야 즉시 중지 합니다. 프로시저를 종료 하는 일반적인 방법 ([Return 문을](../../../visual-basic/language-reference/statements/return-statement.md) 및 [Exit 문은](../../../visual-basic/language-reference/statements/exit-statement.md)) 뿐 아니라 프로시저를 완전히 종료 되지만 호출 코드에서 완전히 종료를 제공 합니다. 콘솔 응용 프로그램, 예를 들어 하기만 하면 `Return` 에서 `Main` 프로시저입니다.  
  
> [!IMPORTANT]
>  `End` 문 호출은 <xref:System.Environment.Exit%2A> 의 메서드는 <xref:System.Environment> 클래스에 <xref:System> 네임 스페이스입니다. <xref:System.Environment.Exit%2A> 해야 `UnmanagedCode` 권한. 그렇지 않고 하는 경우는 <xref:System.Security.SecurityException> 오류가 발생 합니다.  
  
 뒤에 키워드를 추가 하는 경우 [끝 \<키워드 > 문을](../../../visual-basic/language-reference/statements/end-keyword-statement.md) 적절 한 프로시저 또는 블록의 정의의 끝을 나타낼 합니다. 예를 들어 `End Function` 의 정의 종료 한 `Function` 프로시저입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `End` 문을 사용자가 요청할 경우 코드 실행을 종료 합니다.  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/end-statement_1.vb)]  
  
## <a name="smart-device-developer-notes"></a>스마트 장치 개발자 노트  
 이 문은 지원 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Security.Permissions.SecurityPermissionFlag>  
 [Stop 문](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [최종 \<키워드 > 문](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
