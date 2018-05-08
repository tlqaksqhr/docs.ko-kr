---
title: 암호 복잡성 (Visual Basic) 유효성 검사
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: acfc8ab958c8671ed7f1afd245d24a43ca12be29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a>연습: 암호의 복합성 검사(Visual Basic)
이 메서드는 몇 가지 강력한 암호 특성에 대 한 확인 하 고 문자열 매개 변수 정보로 업데이트 실패에 대 한 암호를 확인 합니다.  
  
 사용자 권한을 부여 하는 보안 시스템에서 암호를 사용할 수 있으며 합니다. 그러나 암호 권한이 없는 사용자가 해야 할지 추측 하기가 어려울 수 해야 합니다. 공격자가 사용할 수는 *사전 공격* 프로그램 사전 (또는 다른 언어로 여러 사전)에 있는 단어의 모든 반복 하 고 단어 사용자의 암호 사용 되는지 테스트 합니다. "Yankees" 또는 "무스 탕"와 같은 취약 한 암호를 신속 하 게 추측할 수 있습니다. 강력한 암호와 같은 "? 사용자 'L1N3vaFiNdMeyeP@sSWerd! "을 추측할 수를 가능성이 훨씬 낮습니다. 암호로 보호 된 시스템 사용자가 강력한 암호를 선택 해야 합니다.  
  
 강력한 암호 (대문자, 소문자, 숫자 및 특수 문자의 조합을 포함) 복잡 하며 단어 아닙니다. 이 예제에는 복잡성을 확인 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
  
### <a name="code"></a>코드  
 [!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 해당 암호를 포함 하는 문자열을 전달 하 여이 메서드를 호출 합니다.  
  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System.Text.RegularExpressions> 네임스페이스의 멤버에 대한 액세스 권한. 코드에서 멤버 이름을 정규화하지 않는 경우 `Imports` 문을 추가합니다. 자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.  
  
## <a name="security"></a>보안  
 네트워크를 통해 암호를 이동 하는 경우 데이터 전송에 안전한 방법을 사용 해야 합니다. 자세한 내용은 참조 [ASP.NET 웹 응용 프로그램 보안](https://msdn.microsoft.com/library/330a99hc)합니다.  
  
 정확도 향상 시킬 수 있습니다는 `ValidatePassword` 복잡성이 추가 검사를 추가 하 여 함수:  
  
-   암호 및 사용자의 이름, 사용자 식별자 및 응용 프로그램 정의 사전 해당 부분 문자열을 비교 합니다. 또한 비교를 수행할 때 해당 키를 시각적으로 유사한 문자를 처리 합니다. 예를 들어 취급 문자에 "l" 및 "e"는 숫자 "1" 및 "3"에 해당 합니다.  
  
-   대 문자가 하나만 있으면 암호의 첫 문자가 아닌지 확인 합니다.  
  
-   암호는 마지막 두 자리 문자가 인지 확인 합니다.  
  
-   키보드의 맨 위 행에서 모든 기호는 입력 되는 암호를 허용 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Text.RegularExpressions.Regex>  
 [ASP.NET 웹 응용 프로그램 보안](https://msdn.microsoft.com/library/330a99hc)
