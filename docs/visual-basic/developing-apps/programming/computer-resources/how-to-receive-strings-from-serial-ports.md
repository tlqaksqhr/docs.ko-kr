---
title: "방법: Visual Basic에서 직렬 포트의 문자열 받기 | Microsoft 문서"
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
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8e56646b1d8ff3b682a402b4b2fc7442c3338a49
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a>방법: Visual Basic에서 직렬 포트의 문자열 받기
이 항목에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 `My.Computer.Ports`를 사용하여 컴퓨터의 직렬 포트에서 문자열을 받는 방법을 설명합니다.  
  
### <a name="to-receive-strings-from-the-serial-port"></a>직렬 포트에서 문자열을 받으려면  
  
1.  반환 문자열을 초기화합니다.  
  
     [!code-vb[VbVbalrMyComputer#38](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_1.vb)]  
  
2.  문자열을 제공해야 하는 직렬 포트를 확인합니다. 이 예제에서는 `COM1`이라고 가정합니다.  
  
3.  `My.Computer.Ports.OpenSerialPort` 메서드를 사용하여 포트에 대한 참조를 가져옵니다. 자세한 내용은 <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>를 참조하세요.  
  
     `Try...Catch...Finally` 블록을 사용하면 예외를 생성하는 경우 응용 프로그램이 직렬 포트를 닫을 수 있습니다. 직렬 포트를 조작하는 모든 코드는 이 블록 안에 표시되어야 합니다.  
  
     [!code-vb[VbVbalrMyComputer#39](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_2.vb)]  
  
4.  줄이 더 이상 없을 때까지 텍스트 줄을 읽기 위한 `Do` 루프를 만듭니다.  
  
     [!code-vb[VbVbalrMyComputer#40](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_3.vb)]  
  
5.  <xref:System.IO.Ports.SerialPort.ReadLine%2A> 메서드를 사용하여 직렬 포트에서 사용 가능한 다음 텍스트 줄을 읽습니다.  
  
     [!code-vb[VbVbalrMyComputer#41](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_4.vb)]  
  
6.  `If` 문을 사용하여 <xref:System.IO.Ports.SerialPort.ReadLine%2A> 메서드가 `Nothing`(텍스트가 더 이상 없음)을 반환하는지 확인합니다. `Nothing`이 반환되는 경우 `Do` 루프를 종료합니다.  
  
     [!code-vb[VbVbalrMyComputer#42](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_5.vb)]  
  
7.  `If` 문에 `Else` 블록을 추가하여 문자열을 실제로 읽는 경우를 처리합니다. 이 블록은 직렬 포트의 문자열을 반환 문자열에 추가합니다.  
  
     [!code-vb[VbVbalrMyComputer#43](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_6.vb)]  
  
8.  문자열을 반환합니다.  
  
     [!code-vb[VbVbalrMyComputer#44](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_7.vb)]  
  
## <a name="example"></a>예제  
 [!code-vb[VbVbalrMyComputer#37](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_8.vb)]  
  
 이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다. 코드 조각 선택에서는 **연결 및 네트워킹**에 있습니다. 자세한 내용은 [코드 조각](https://docs.microsoft.com/visualstudio/ide/code-snippets)을 참조하세요.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에서는 컴퓨터가 `COM1`을 사용 중이라고 가정합니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 이 예제에서는 컴퓨터가 `COM1`을 사용 중이라고 가정합니다. 유연성 향상을 위해 코드에서 사용자가 사용 가능한 포트 목록에서 원하는 직렬 포트를 선택할 수 있도록 해야 합니다. 자세한 내용은 [방법: 사용할 수 있는 직렬 포트 표시](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)를 참조하세요.  
  
 이 예제에서는 `Try...Catch...Finally` 블록을 사용하여 응용 프로그램이 포트를 닫도록 하고 시간 초과 예외를 catch합니다. 자세한 내용은 [Try...Catch...Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [방법: 직렬 포트에 연결된 모뎀 전화 접속](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [방법: 직렬 포트로 문자열 보내기](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [방법: 사용할 수 있는 직렬 포트 표시](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
