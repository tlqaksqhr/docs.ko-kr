---
title: "방법: Visual Basic에서 직렬 포트로 문자열 보내기"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- ports, sending strings to
- strings [Visual Basic], sending to serial ports
- My.Computer.Ports object
- serial ports, sending strings to
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 602b249d01252bbb1853ed02d9af86697d54b0a5
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a>방법: Visual Basic에서 직렬 포트로 문자열 보내기
이 항목에서는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에서 `My.Computer.Ports`를 사용하여 컴퓨터의 직렬 포트에 문자열을 보내는 방법을 설명합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 COM1 직렬 포트에 문자열을 보냅니다. 컴퓨터의 다른 직렬 포트를 사용해야 할 수도 있습니다.  
  
 `My.Computer.Ports.OpenSerialPort` 메서드를 사용하여 포트에 대한 참조를 가져옵니다. 자세한 내용은 <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>을 참조하십시오.  
  
 `Using` 블록을 사용하면 예외를 생성하는 경우 응용 프로그램이 직렬 포트를 닫을 수 있습니다. 직렬 포트를 조작하는 모든 코드는 이 블록 안이나 `Try...Catch...Finally` 블록 안에 표시되어야 합니다.  
  
 <xref:System.IO.Ports.SerialPort.WriteLine%2A> 메서드는 데이터를 직렬 포트로 보냅니다.  
  
 [!code-vb[VbVbalrMyComputer#33](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-send-strings-to-serial-ports_1.vb)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   이 예제에서는 컴퓨터가 `COM1`을 사용 중이라고 가정합니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 이 예제에서는 컴퓨터가 `COM1`을 사용 중이라고 가정합니다. 유연성 향상을 위해 코드에서 사용자가 사용 가능한 포트 목록에서 원하는 직렬 포트를 선택할 수 있도록 해야 합니다. 자세한 내용은 [방법: 사용할 수 있는 직렬 포트 표시](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)를 참조하세요.  
  
 이 예제에서는 `Using` 블록을 사용하여 예외가 throw되는 경우에도 응용 프로그램이 포트를 닫도록 합니다. 자세한 내용은 [using 문](../../../../visual-basic/language-reference/statements/using-statement.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [방법: 직렬 포트에 연결된 모뎀 전화 접속](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [방법: 사용할 수 있는 직렬 포트 표시](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)

