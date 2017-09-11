---
title: "방법: Visual Basic에서 사용할 수 있는 직렬 포트 표시"
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
- serial ports, availability
- My.Computer.Ports.SerialPortNames property
- My.Computer.Ports object
- ports, serial port availability
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
caps.latest.revision: 20
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
ms.openlocfilehash: bab6177c788a847b46586db19a525c1a1b36476d
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-show-available-serial-ports-in-visual-basic"></a><span data-ttu-id="2ce6b-102">방법: Visual Basic에서 사용할 수 있는 직렬 포트 표시</span><span class="sxs-lookup"><span data-stu-id="2ce6b-102">How to: Show Available Serial Ports in Visual Basic</span></span>
<span data-ttu-id="2ce6b-103">이 항목에서는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에서 `My.Computer.Ports`를 사용하여 컴퓨터에서 사용 가능한 직렬 포트를 보여 주는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-103">This topic describes how to use `My.Computer.Ports` to show the available serial ports of the computer in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="2ce6b-104">사용자가 사용할 포트를 선택할 수 있도록 직렬 포트의 이름이 <xref:System.Windows.Forms.ListBox>에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-104">To allow a user to select which port to use, the names of the serial ports are placed in a <xref:System.Windows.Forms.ListBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ce6b-105">예제</span><span class="sxs-lookup"><span data-stu-id="2ce6b-105">Example</span></span>  
 <span data-ttu-id="2ce6b-106">이 예제에서는 `My.Computer.Ports.SerialPortNames` 속성이 반환하는 모든 문자열을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-106">This example loops over all the strings that the `My.Computer.Ports.SerialPortNames` property returns.</span></span> <span data-ttu-id="2ce6b-107">이러한 문자열은 컴퓨터에서 사용할 수 있는 직렬 포트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-107">These strings are the names of the available serial ports on the computer.</span></span>  
  
 <span data-ttu-id="2ce6b-108">일반적으로 사용자는 사용 가능한 포트 목록에서 응용 프로그램이 사용해야 하는 직렬 포트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-108">Typically, a user selects which serial port the application should use from the list of available ports.</span></span> <span data-ttu-id="2ce6b-109">이 예제에서 직렬 포트 이름은 <xref:System.Windows.Forms.ListBox> 컨트롤에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-109">In this example, the serial port names are stored in a <xref:System.Windows.Forms.ListBox> control.</span></span> <span data-ttu-id="2ce6b-110">자세한 내용은 [ListBox 컨트롤](../../../../framework/winforms/controls/listbox-control-windows-forms.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-110">For more information, see [ListBox Control](../../../../framework/winforms/controls/listbox-control-windows-forms.md).</span></span>  
  
 <span data-ttu-id="2ce6b-111">[!code-vb[VbVbalrMyComputer#45](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-show-available-serial-ports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2ce6b-111">[!code-vb[VbVbalrMyComputer#45](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-show-available-serial-ports_1.vb)]</span></span>  
  
 <span data-ttu-id="2ce6b-112">이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-112">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="2ce6b-113">코드 조각 선택에서는 **연결 및 네트워킹**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-113">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="2ce6b-114">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-114">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2ce6b-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="2ce6b-115">Compiling the Code</span></span>  
 <span data-ttu-id="2ce6b-116">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-116">This example requires:</span></span>  
  
-   <span data-ttu-id="2ce6b-117">System.Windows.Forms.dll에 대한 프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="2ce6b-117">A project reference to System.Windows.Forms.dll.</span></span>  
  
-   <span data-ttu-id="2ce6b-118"><xref:System.Windows.Forms> 네임스페이스의 멤버에 대한 액세스 권한.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-118">Access to the members of the <xref:System.Windows.Forms> namespace.</span></span> <span data-ttu-id="2ce6b-119">코드에서 멤버 이름을 정규화하지 않는 경우 `Imports` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-119">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="2ce6b-120">자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-120">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
-   <span data-ttu-id="2ce6b-121">`ListBox1`이라는 <xref:System.Windows.Forms.ListBox> 컨트롤이 폼에 있어야 함</span><span class="sxs-lookup"><span data-stu-id="2ce6b-121">That your form have a <xref:System.Windows.Forms.ListBox> control named `ListBox1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="2ce6b-122">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="2ce6b-122">Robust Programming</span></span>  
 <span data-ttu-id="2ce6b-123">사용 가능한 직렬 포트 이름을 표시하기 위해 <xref:System.Windows.Forms.ListBox> 컨트롤을 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-123">You do not have to use the <xref:System.Windows.Forms.ListBox> control to display the available serial port names.</span></span> <span data-ttu-id="2ce6b-124">대신 <xref:System.Windows.Forms.ComboBox> 또는 기타 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-124">Instead, you can use a <xref:System.Windows.Forms.ComboBox> or other control.</span></span> <span data-ttu-id="2ce6b-125">응용 프로그램에 사용자 응답이 필요하지 않은 경우 <xref:System.Windows.Forms.TextBox> 컨트롤을 사용하여 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-125">If the application does not need a response from the user, you can use a <xref:System.Windows.Forms.TextBox> control to display the information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ce6b-126">Windows 98에서 실행하는 경우 `My.Computer.Ports.SerialPortNames`에서 반환되는 포트 이름이 부정확할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-126">The port names returned by `My.Computer.Ports.SerialPortNames` may be incorrect when run on Windows 98.</span></span> <span data-ttu-id="2ce6b-127">응용 프로그램 오류를 방지하려면 포트 이름을 사용하여 포트를 열 때 `Try...Catch...Finally` 문 또는 `Using` 문과 같은 예외 처리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ce6b-127">To prevent application errors, use exception handling, such as the `Try...Catch...Finally` statement or the `Using` statement, when using the port names to open ports.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ce6b-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ce6b-128">See Also</span></span>  
 <span data-ttu-id="2ce6b-129"><xref:Microsoft.VisualBasic.Devices.Ports></span><span class="sxs-lookup"><span data-stu-id="2ce6b-129"><xref:Microsoft.VisualBasic.Devices.Ports></span></span>   
 <span data-ttu-id="2ce6b-130">[방법: 직렬 포트에 연결된 모뎀 전화 접속](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="2ce6b-130">[How to: Dial Modems Attached to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md) </span></span>  
 <span data-ttu-id="2ce6b-131">[방법: 직렬 포트로 문자열 보내기](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="2ce6b-131">[How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span></span>  
 [<span data-ttu-id="2ce6b-132">방법: 직렬 포트에서 문자열 받기</span><span class="sxs-lookup"><span data-stu-id="2ce6b-132">How to: Receive Strings From Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)

