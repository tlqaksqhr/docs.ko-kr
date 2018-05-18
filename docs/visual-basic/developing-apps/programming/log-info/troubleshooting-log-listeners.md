---
title: '문제 해결: 로그 수신기(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
ms.openlocfilehash: 54c3ed0f607edf992fa3c40a8e6214252740587c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-log-listeners-visual-basic"></a>문제 해결: 로그 수신기(Visual Basic)
`My.Application.Log` 및 `My.Log` 개체를 사용하여 응용 프로그램에서 발생하는 이벤트에 대한 정보를 기록할 수 있습니다.  
  
 해당 메시지를 받는 로그 수신기를 확인하려면 [연습: My.Application.Log가 정보를 기록하는 위치 확인](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)을 참조하세요.  
  
 `Log` 개체는 로그 필터링을 사용하여 기록하는 정보의 양을 제한할 수 있습니다. 필터가 잘못 구성된 경우 로그에 잘못된 정보가 포함될 수 있습니다. 필터링에 대한 자세한 내용은 [연습: My.Application.Log 출력 필터링](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)을 참조하세요.  
  
 그러나 로그가 잘못 구성된 경우 현재 구성에 대한 자세한 정보가 필요할 수도 있습니다. 이 정보는 로그의 고급 `TraceSource` 속성을 통해 얻을 수 있습니다.  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a>코드에서 Log 개체에 대한 로그 수신기를 확인하려면  
  
1.  코드 파일의 시작 부분에 있는 <xref:System.Diagnostics> 네임스페이스를 가져옵니다. 자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.  
  
     [!code-vb[VbVbalrMyApplicationLog#13](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_1.vb)]  
  
2.  각 로그 수신기에 대한 정보로 구성된 문자열을 반환하는 함수를 만듭니다.  
  
     [!code-vb[VbVbalrMyApplicationLog#14](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_2.vb)]  
  
3.  로그의 추적 수신기 컬렉션을 `GetListeners` 함수에 전달하고 반환 값을 표시합니다.  
  
     [!code-vb[VbVbalrMyApplicationLog#19](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_3.vb)]  
  
     자세한 내용은 <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 [응용 프로그램 로그 작업](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [연습: My.Application.Log가 정보를 기록하는 위치 확인](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
