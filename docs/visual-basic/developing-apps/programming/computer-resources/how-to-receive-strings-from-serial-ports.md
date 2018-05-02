---
title: '방법: Visual Basic에서 직렬 포트의 문자열 받기'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76124654e479ae84702524d68bcced34610d1526
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a><span data-ttu-id="3c52c-102">방법: Visual Basic에서 직렬 포트의 문자열 받기</span><span class="sxs-lookup"><span data-stu-id="3c52c-102">How to: Receive Strings From Serial Ports in Visual Basic</span></span>
<span data-ttu-id="3c52c-103">이 항목에서는 Visual Basic에서 `My.Computer.Ports`를 사용하여 컴퓨터의 직렬 포트에서 문자열을 받는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-103">This topic describes how to use `My.Computer.Ports` to receive strings from the computer's serial ports in Visual Basic.</span></span>  
  
### <a name="to-receive-strings-from-the-serial-port"></a><span data-ttu-id="3c52c-104">직렬 포트에서 문자열을 받으려면</span><span class="sxs-lookup"><span data-stu-id="3c52c-104">To receive strings from the serial port</span></span>  
  
1.  <span data-ttu-id="3c52c-105">반환 문자열을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-105">Initialize the return string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#38](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_1.vb)]  
  
2.  <span data-ttu-id="3c52c-106">문자열을 제공해야 하는 직렬 포트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-106">Determine which serial port should provide the strings.</span></span> <span data-ttu-id="3c52c-107">이 예제에서는 `COM1`이라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-107">This example assumes it is `COM1`.</span></span>  
  
3.  <span data-ttu-id="3c52c-108">`My.Computer.Ports.OpenSerialPort` 메서드를 사용하여 포트에 대한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-108">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="3c52c-109">자세한 내용은 <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c52c-109">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="3c52c-110">`Try...Catch...Finally` 블록을 사용하면 예외를 생성하는 경우 응용 프로그램이 직렬 포트를 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-110">The `Try...Catch...Finally` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="3c52c-111">직렬 포트를 조작하는 모든 코드는 이 블록 안에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-111">All code that manipulates the serial port should appear within this block.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#39](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_2.vb)]  
  
4.  <span data-ttu-id="3c52c-112">줄이 더 이상 없을 때까지 텍스트 줄을 읽기 위한 `Do` 루프를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-112">Create a `Do` loop for reading lines of text until no more lines are available.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#40](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_3.vb)]  
  
5.  <span data-ttu-id="3c52c-113"><xref:System.IO.Ports.SerialPort.ReadLine> 메서드를 사용하여 직렬 포트에서 텍스트의 사용 가능한 다음 줄을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-113">Use the <xref:System.IO.Ports.SerialPort.ReadLine> method to read the next available line of text from the serial port.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#41](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_4.vb)]  
  
6.  <span data-ttu-id="3c52c-114">`If` 문을 사용하여 <xref:System.IO.Ports.SerialPort.ReadLine> 메서드가 `Nothing`(텍스트가 더 이상 없음)을 반환하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-114">Use an `If` statement to determine if the <xref:System.IO.Ports.SerialPort.ReadLine> method returns `Nothing` (which means no more text is available).</span></span> <span data-ttu-id="3c52c-115">`Nothing`이 반환되는 경우 `Do` 루프를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-115">If it does return `Nothing`, exit the `Do` loop.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#42](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_5.vb)]  
  
7.  <span data-ttu-id="3c52c-116">`If` 문에 `Else` 블록을 추가하여 문자열을 실제로 읽는 경우를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-116">Add an `Else` block to the `If` statement to handle the case if the string is actually read.</span></span> <span data-ttu-id="3c52c-117">이 블록은 직렬 포트의 문자열을 반환 문자열에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-117">The block appends the string from the serial port to the return string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#43](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_6.vb)]  
  
8.  <span data-ttu-id="3c52c-118">문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-118">Return the string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#44](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_7.vb)]  
  
## <a name="example"></a><span data-ttu-id="3c52c-119">예</span><span class="sxs-lookup"><span data-stu-id="3c52c-119">Example</span></span>  
 [!code-vb[VbVbalrMyComputer#37](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_8.vb)]  
  
 <span data-ttu-id="3c52c-120">이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-120">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="3c52c-121">코드 조각 선택에서는 **연결 및 네트워킹**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-121">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="3c52c-122">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c52c-122">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3c52c-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3c52c-123">Compiling the Code</span></span>  
 <span data-ttu-id="3c52c-124">이 예제에서는 컴퓨터가 `COM1`을 사용 중이라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-124">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3c52c-125">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="3c52c-125">Robust Programming</span></span>  
 <span data-ttu-id="3c52c-126">이 예제에서는 컴퓨터가 `COM1`을 사용 중이라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-126">This example assumes the computer is using `COM1`.</span></span> <span data-ttu-id="3c52c-127">유연성 향상을 위해 코드에서 사용자가 사용 가능한 포트 목록에서 원하는 직렬 포트를 선택할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-127">For more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="3c52c-128">자세한 내용은 [방법: 사용할 수 있는 직렬 포트 표시](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c52c-128">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="3c52c-129">이 예제에서는 `Try...Catch...Finally` 블록을 사용하여 응용 프로그램이 포트를 닫도록 하고 시간 초과 예외를 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="3c52c-129">This example uses a `Try...Catch...Finally` block to make sure that the application closes the port and to catch any timeout exceptions.</span></span> <span data-ttu-id="3c52c-130">자세한 내용은 [Try...Catch...Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c52c-130">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c52c-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c52c-131">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Ports>  
 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>  
 [<span data-ttu-id="3c52c-132">방법: 직렬 포트에 연결된 모뎀 전화 접속</span><span class="sxs-lookup"><span data-stu-id="3c52c-132">How to: Dial Modems Attached to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)  
 [<span data-ttu-id="3c52c-133">방법: 직렬 포트로 문자열 보내기</span><span class="sxs-lookup"><span data-stu-id="3c52c-133">How to: Send Strings to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)  
 [<span data-ttu-id="3c52c-134">방법: 사용할 수 있는 직렬 포트 표시</span><span class="sxs-lookup"><span data-stu-id="3c52c-134">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
