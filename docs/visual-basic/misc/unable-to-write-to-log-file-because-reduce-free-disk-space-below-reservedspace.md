---
title: "사용 가능한 디스크 공간이 ReservedSpace 값 미만으로 줄어들 수 있기 때문에 로그 파일에 쓸 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrApplicationLog_ReservedSpaceEncroached
ms.assetid: 95832e70-4ecc-47aa-90c1-f35c4d468151
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0adc3438a9473885022e9785c5381f8da0b6f303
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-reduce-free-disk-space-below-reservedspace-value"></a>사용 가능한 디스크 공간이 ReservedSpace 값 미만으로 줄어들 수 있기 때문에 로그 파일에 쓸 수 없습니다.
<xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 클래스가 다음 이유로 로그 파일에 쓸 수 없습니다.  
  
-   여유 디스크 공간(바이트)의 용량이 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> 속성의 값보다 작습니다.  
  
     —그리고—  
  
-   <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> 속성의 값이 <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>이었습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 개체가 새 로그를 만들 수 있도록 기존 로그를 보관하고 컴퓨터에서 제거합니다.  
  
2.  <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> 속성의 값을 더 작은 숫자로 변경하여 작은 디스크 공간을 예약합니다.  
  
3.  여유 디스크 공간이 충분하지 않은 경우 경고 없이 메시지를 무시하려면 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> 속성을 <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> 로 설정합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>  
 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>  
 [My.Application.Log 개체](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [My.Log 개체](../../visual-basic/language-reference/objects/my-log-object.md)
