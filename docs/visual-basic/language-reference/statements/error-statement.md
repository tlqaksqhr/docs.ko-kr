---
title: Error 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 84fce92183228cbfa5554a3ba45770a86e83bff5
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39199481"
---
# <a name="error-statement"></a>Error 문
오류의 발생을 시뮬레이션 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a>요소  
 `errornumber`  
 필수. 유효한 임의의 오류 번호를 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `Error` 문은 이전 버전과 호환성을 위해 지원 됩니다. 새 코드에서는 개체를 만들 때 특히를 사용 합니다 `Err` 개체의 `Raise` 런타임 오류를 생성 하는 방법입니다.  
  
 경우 `errornumber` 정의 되는 `Error` 속성을 후 오류 처리기를 호출 하는 문을 `Err` 개체는 다음과 같은 기본값이 할당 됩니다:  
  
|속성|값|  
|--------------|-----------|  
|`Number`|인수로 지정 된 값 `Error` 문입니다. 유효한 임의의 오류 번호를 수 있습니다.|  
|`Source`|현재 Visual Basic 프로젝트의 이름입니다.|  
|`Description`|문자열 식의 반환 값에 해당 하는 `Error` 지정 된 함수 `Number`이 문자열이 존재 하는 경우. 문자열이 없으면 `Description` 길이가 0 인 문자열 포함 ("").|  
|`HelpFile`|정규화 된 드라이브, 경로 및 적절 한 Visual Basic 도움말 파일의 파일 이름입니다.|  
|`HelpContext`|적절 한 Visual Basic 도움말 파일 컨텍스트 ID에 해당 하는 오류에 대 한는 `Number` 속성입니다.|  
|`LastDLLError`|0입니다.|  
  
 오류 처리기가 없거나, 또는 오류 메시지가 생성 되어 표시에서 none을 사용 하는 경우는 `Err` 개체 속성입니다.  
  
> [!NOTE]
>  일부 Visual Basic 호스트 응용 프로그램 개체를 만들 수 없습니다. 클래스 및 개체를 만들 수 있는지 확인 하려면 호스트 응용 프로그램의 설명서를 참조 하세요.  
  
## <a name="example"></a>예  
 이 예제에서는 `Error` 문의 오류 번호 11을 생성 합니다.  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>요구 사항  
 **: Namespace** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **어셈블리:** Visual Basic 런타임 라이브러리 (Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>  
 [On Error 문](../../../visual-basic/language-reference/statements/on-error-statement.md)  
 [Resume 문](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [오류 메시지](../../../visual-basic/language-reference/error-messages/index.md)
