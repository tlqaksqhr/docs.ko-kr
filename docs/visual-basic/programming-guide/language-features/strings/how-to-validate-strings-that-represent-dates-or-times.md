---
title: '방법: 날짜 또는 시간을 나타내는 문자열 확인(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 411c8517783421b2472c3e4aa77287f8252f179b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>방법: 날짜 또는 시간을 나타내는 문자열 확인(Visual Basic)
다음 코드 예제에서는 한 `Boolean` 문자열이 유효한 날짜 또는 시간을 나타내는지 여부를 나타내는 값입니다.  
  
## <a name="example"></a>예제  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 대체 `("01/01/03")` 및 `"9:30 PM"` 의 날짜와 시간 유효성을 검사 하려고 합니다. 와 다른 하드 코드 된 문자열을 사용 하 여 문자열을 바꿀 수 있습니다는 `String` 와 같은 하는 문자열을 반환 변수, 또는 메서드에서 `InputBox`합니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 이 메서드를 사용 하 여 문자열 변환 하기 전에 유효성을 검사 하는 `String` 에 `DateTime` 변수입니다. 날짜 또는 시간을 먼저 확인 하 여 런타임 시 예외를 생성을 방지할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>  
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>  
 [Visual Basic의 문자열 유효성 검사](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
