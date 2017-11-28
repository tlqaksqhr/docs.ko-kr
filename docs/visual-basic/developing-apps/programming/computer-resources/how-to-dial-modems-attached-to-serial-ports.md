---
title: "방법: Visual Basic에서 직렬 포트에 연결된 모뎀 전화 접속"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- modems [Visual Basic], dialing
- serial ports [Visual Basic], dialing
- My.Computer.Ports object
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ea1b2d6152af8919ac1aa272def4ba198b33867c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-dial-modems-attached-to-serial-ports-in-visual-basic"></a><span data-ttu-id="d261d-102">방법: Visual Basic에서 직렬 포트에 연결된 모뎀 전화 접속</span><span class="sxs-lookup"><span data-stu-id="d261d-102">How to: Dial Modems Attached to Serial Ports in Visual Basic</span></span>
<span data-ttu-id="d261d-103">이 항목에서는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에서 `My.Computer.Ports`를 사용하여 모뎀으로 전화를 거는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-103">This topic describes how to use `My.Computer.Ports` to dial a modem in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="d261d-104">일반적으로 모뎀은 컴퓨터의 직렬 포트 중 하나에 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-104">Typically, the modem is connected to one of the serial ports on the computer.</span></span> <span data-ttu-id="d261d-105">응용 프로그램이 모뎀과 통신하려면 적절한 직렬 포트로 명령을 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-105">For your application to communicate with the modem, it must send commands to the appropriate serial port.</span></span>  
  
### <a name="to-dial-a-modem"></a><span data-ttu-id="d261d-106">모뎀으로 전화를 걸려면</span><span class="sxs-lookup"><span data-stu-id="d261d-106">To dial a modem</span></span>  
  
1.  <span data-ttu-id="d261d-107">모뎀이 연결된 직렬 포트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-107">Determine which serial port the modem is connected to.</span></span> <span data-ttu-id="d261d-108">이 예제에서는 모뎀이 COM1에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-108">This example assumes the modem is on COM1.</span></span>  
  
2.  <span data-ttu-id="d261d-109">`My.Computer.Ports.OpenSerialPort` 메서드를 사용하여 포트에 대한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-109">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="d261d-110">자세한 내용은 <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d261d-110">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="d261d-111">`Using` 블록을 사용하면 예외를 생성하는 경우 응용 프로그램이 직렬 포트를 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-111">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="d261d-112">직렬 포트를 조작하는 모든 코드는 이 블록 안이나 `Try...Catch...Finally` 블록 안에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-112">All code that manipulates the serial port should appear within this block, or within a `Try...Catch...Finally` block.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#28](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_1.vb)]  
  
3.  <span data-ttu-id="d261d-113">`DtrEnable` 속성을 설정하여 컴퓨터가 모뎀에서 들어오는 전송을 받을 준비가 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-113">Set the `DtrEnable` property to indicate that the computer is ready to accept an incoming transmission from the modem.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#29](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_2.vb)]  
  
4.  <span data-ttu-id="d261d-114"><xref:System.IO.Ports.SerialPort.Write%2A> 메서드를 사용하여 직렬 포트를 통해 전화 걸기 명령과 전화 번호를 모뎀으로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-114">Send the dial command and the phone number to the modem through the serial port by means of the <xref:System.IO.Ports.SerialPort.Write%2A> method.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#30](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="d261d-115">예제</span><span class="sxs-lookup"><span data-stu-id="d261d-115">Example</span></span>  
 [!code-vb[VbVbalrMyComputer#27](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_4.vb)]  
  
 <span data-ttu-id="d261d-116">이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-116">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="d261d-117">코드 조각 선택에서는 **연결 및 네트워킹**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-117">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="d261d-118">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d261d-118">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d261d-119">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d261d-119">Compiling the Code</span></span>  
 <span data-ttu-id="d261d-120">이 예제에서는 <xref:System?displayProperty=nameWithType> 네임스페이스에 대한 참조가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-120">This example requires a reference to the <xref:System?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d261d-121">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="d261d-121">Robust Programming</span></span>  
 <span data-ttu-id="d261d-122">이 예제에서는 모뎀이 COM1에 연결되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-122">This example assumes the modem is connected to COM1.</span></span> <span data-ttu-id="d261d-123">코드에서 사용자가 사용 가능한 포트 목록에서 원하는 직렬 포트를 선택할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-123">We recommend that your code allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="d261d-124">자세한 내용은 [방법: 사용할 수 있는 직렬 포트 표시](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d261d-124">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="d261d-125">이 예제에서는 `Using` 블록을 사용하여 예외가 throw되는 경우에도 응용 프로그램이 포트를 닫도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-125">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="d261d-126">자세한 내용은 [using 문](../../../../visual-basic/language-reference/statements/using-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d261d-126">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
 <span data-ttu-id="d261d-127">이 예제에서 응용 프로그램은 모뎀으로 전화를 건 후 직렬 포트의 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-127">In this example, the application disconnects the serial port after it dials the modem.</span></span> <span data-ttu-id="d261d-128">현실적으로 모뎀과 데이터를 주고받으려 합니다.</span><span class="sxs-lookup"><span data-stu-id="d261d-128">Realistically, you will want to transfer data to and from the modem.</span></span> <span data-ttu-id="d261d-129">자세한 내용은 [방법: 직렬 포트에서 문자열 받기](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d261d-129">For more information, see [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d261d-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d261d-130">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Ports>  
 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>  
 [<span data-ttu-id="d261d-131">방법: 직렬 포트로 문자열 보내기</span><span class="sxs-lookup"><span data-stu-id="d261d-131">How to: Send Strings to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)  
 [<span data-ttu-id="d261d-132">방법: 직렬 포트에서 문자열 받기</span><span class="sxs-lookup"><span data-stu-id="d261d-132">How to: Receive Strings From Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)  
 [<span data-ttu-id="d261d-133">방법: 사용할 수 있는 직렬 포트 표시</span><span class="sxs-lookup"><span data-stu-id="d261d-133">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
