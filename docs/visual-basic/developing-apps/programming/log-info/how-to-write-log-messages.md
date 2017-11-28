---
title: "방법: 로그 메시지 쓰기(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: My.Application.Log object, writing log messags
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ae4d875fd4f95ca51fff565551009e780b17d07a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-log-messages-visual-basic"></a>방법: 로그 메시지 쓰기(Visual Basic)
`My.Application.Log` 및 `My.Log` 개체를 사용하여 응용 프로그램에 대한 정보를 기록할 수 있습니다. 이 예제에서는 `My.Application.Log.WriteEntry` 메서드를 사용하여 추적 정보를 기록하는 방법을 보여 줍니다.  
  
 예외 정보를 기록하려면 `My.Application.Log.WriteException` 메서드를 사용합니다. [방법: 예외 기록](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)을 참조하세요.  
  
## <a name="example"></a>예제  
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
