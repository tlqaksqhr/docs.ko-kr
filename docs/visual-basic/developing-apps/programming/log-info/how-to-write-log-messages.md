---
title: '방법: 로그 메시지 쓰기(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messags
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: 8b0d50e70572d849f20f01914d2380a64e4495a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-log-messages-visual-basic"></a>방법: 로그 메시지 쓰기(Visual Basic)
`My.Application.Log` 및 `My.Log` 개체를 사용하여 응용 프로그램에 대한 정보를 기록할 수 있습니다. 이 예제에서는 `My.Application.Log.WriteEntry` 메서드를 사용하여 추적 정보를 기록하는 방법을 보여 줍니다.  
  
 예외 정보를 기록하려면 `My.Application.Log.WriteException` 메서드를 사용합니다. [방법: 예외 기록](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)을 참조하세요.  
  
## <a name="example"></a>예  
 이 예제에서는 `My.Application.Log.WriteEntry` 메서드를 사용하여 추적 정보를 기록합니다.  
  
 [!code-vb[VbVbalrMyApplicationLog#11](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-write-log-messages_1.vb)]  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 로그에 쓰는 데이터에 사용자 암호와 같은 중요한 정보가 포함되지 않도록 해야 합니다. 자세한 내용은 [응용 프로그램 로그 작업](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>  
 [응용 프로그램 로그 작업](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [방법: 예외 기록](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)  
 [연습: My.Application.Log가 정보를 기록하는 위치 확인](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)  
 [연습: My.Application.Log가 정보를 기록하는 위치 변경](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)  
 [연습: My.Application.Log 출력 필터링](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)
