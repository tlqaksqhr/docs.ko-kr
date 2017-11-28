---
title: "데이터를 클립보드에 저장하고 클립보드에서 읽기(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Clipboard, storing data to (My.Computer.Clipboard)
- Clipboard, reading from (My.Computer.Clipboard)
- Clipboard
- My.Computer.Clipboard object, tasks
- data [Visual Basic], Clipboard
- reading data, from Clipboard
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e7bb4ad56f0a039aa7b23d7f0612aaab9366cb9e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="storing-data-to-and-reading-from-the-clipboard-visual-basic"></a><span data-ttu-id="ac0d3-102">데이터를 클립보드에 저장하고 클립보드에서 읽기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac0d3-102">Storing data to and reading from the Clipboard (Visual Basic)</span></span>
<span data-ttu-id="ac0d3-103">클립보드를 사용하여 텍스트 및 이미지와 같은 데이터를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-103">The Clipboard can be used to store data, such as text and images.</span></span> <span data-ttu-id="ac0d3-104">클립보드는 모든 활성 프로세스에서 공유되기 때문에 프로세스 간에 데이터를 전송하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-104">Because the Clipboard is shared by all active processes, it can be used to transfer data between them.</span></span> <span data-ttu-id="ac0d3-105">`My.Computer.Clipboard` 개체를 사용하면 클립보드에 쉽게 액세스하고 읽고 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-105">The `My.Computer.Clipboard` object allows you to easily access the Clipboard and to read from and write to it.</span></span>  
  
## <a name="reading-from-the-clipboard"></a><span data-ttu-id="ac0d3-106">클립보드에서 읽기</span><span class="sxs-lookup"><span data-stu-id="ac0d3-106">Reading from the Clipboard</span></span>  
 <span data-ttu-id="ac0d3-107"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> 메서드를 사용하여 클립보드에 텍스트를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-107">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> method to read the text in the Clipboard.</span></span> <span data-ttu-id="ac0d3-108">다음 코드는 텍스트를 읽고 메시지 상자에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-108">The following code reads the text and displays it in a message box.</span></span> <span data-ttu-id="ac0d3-109">예제가 제대로 실행되려면 클립보드에 텍스트가 저장되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-109">There must be text stored on the Clipboard for the example to run correctly.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_1.vb)]  
  
 <span data-ttu-id="ac0d3-110">이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-110">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="ac0d3-111">코드 조각 선택에서 **Windows Forms 응용 프로그램 > 클립보드**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-111">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.</span></span> <span data-ttu-id="ac0d3-112">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-112">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="ac0d3-113"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> 메서드를 사용하여 클립보드에서 이미지를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-113">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> method to retrieve an image from the Clipboard.</span></span> <span data-ttu-id="ac0d3-114">이 예제에서는 이미지를 검색하고 `PictureBox1`에 할당하기 전에 클립보드에 이미지가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-114">This example checks to see if there is an image on the Clipboard before retrieving it and assigning it to `PictureBox1`.</span></span>  
  
 [!code-vb[VbResourceTasks#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_2.vb)]  
  
 <span data-ttu-id="ac0d3-115">이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-115">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="ac0d3-116">코드 조각 선택에서 **Windows Forms 응용 프로그램 > 클립보드**에 있습니다. 자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-116">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="ac0d3-117">클립보드에 배치된 항목은 응용 프로그램이 종료된 후에도 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-117">Items placed on the Clipboard will persist even after the application is shut down.</span></span>  
  
## <a name="determining-the-type-of-file-stored-in-the-clipboard"></a><span data-ttu-id="ac0d3-118">클립보드에 저장된 파일 형식 확인</span><span class="sxs-lookup"><span data-stu-id="ac0d3-118">Determining the type of file stored in the Clipboard</span></span>  
 <span data-ttu-id="ac0d3-119">클립보드의 데이터는 텍스트, 오디오 파일 또는 이미지와 같은 다양한 형태일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-119">Data on the Clipboard may take a number of different forms, such as text, an audio file, or an image.</span></span> <span data-ttu-id="ac0d3-120">클립보드에 있는 파일의 종류를 확인하려는 경우 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A> 등의 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-120">In order to determine what sort of file is on the Clipboard, you can use methods such as <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A>, and <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.</span></span> <span data-ttu-id="ac0d3-121">사용자 지정 형식을 확인하려는 경우에는 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-121">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> method can be used if you have a custom format that you want to check.</span></span>  
  
 <span data-ttu-id="ac0d3-122">`ContainsImage` 함수를 사용하여 클립보드에 포함된 데이터가 이미지인지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-122">Use the `ContainsImage` function to determine whether the data contained on the Clipboard is an image.</span></span> <span data-ttu-id="ac0d3-123">다음 코드는 데이터가 이미지인지 여부를 확인하고 그에 따라 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-123">The following code checks to see whether the data is an image and reports accordingly.</span></span>  
  
 [!code-vb[VbResourceTasks#13](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_3.vb)]  
  
## <a name="clearing-the-clipboard"></a><span data-ttu-id="ac0d3-124">클립보드 지우기</span><span class="sxs-lookup"><span data-stu-id="ac0d3-124">Clearing the Clipboard</span></span>  
 <span data-ttu-id="ac0d3-125"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> 메서드는 클립보드를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-125">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> method clears the Clipboard.</span></span> <span data-ttu-id="ac0d3-126">클립보드가 다른 프로세스에서 공유되기 때문에 클립보드를 지우면 해당 프로세스에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-126">Because the Clipboard is shared by other processes, clearing it may have an impact on those processes.</span></span>  
  
 <span data-ttu-id="ac0d3-127">다음 코드에서는 `Clear` 메서드를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-127">The following code shows how to use the `Clear` method.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_4.vb)]  
  
## <a name="writing-to-the-clipboard"></a><span data-ttu-id="ac0d3-128">클립보드에 쓰기</span><span class="sxs-lookup"><span data-stu-id="ac0d3-128">Writing to the Clipboard</span></span>  
 <span data-ttu-id="ac0d3-129"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> 메서드를 사용하여 클립보드에 텍스트를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-129">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> method to write text to the Clipboard.</span></span> <span data-ttu-id="ac0d3-130">다음 코드는 클립보드에 "This is a test string" 문자열을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-130">The following code writes the string "This is a test string" to the Clipboard.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#1](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_5.vb)]  
  
 <span data-ttu-id="ac0d3-131">`SetText` 메서드는 <xref:System.Windows.Forms.TextDataFormat> 형식을 포함하는 형식 매개 변수를 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-131">The `SetText` method can accept a format parameter that contains a type of <xref:System.Windows.Forms.TextDataFormat>.</span></span> <span data-ttu-id="ac0d3-132">다음 코드는 클립보드에 "This is a test string" 문자열을 RTF 텍스트로 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-132">The following code writes the string "This is a test string" to the Clipboard as RTF text.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#2](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_6.vb)]  
  
 <span data-ttu-id="ac0d3-133"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> 메서드를 사용하여 클립보드에 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-133">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> method to write data to the Clipboard.</span></span> <span data-ttu-id="ac0d3-134">이 예제에서는 `DataObject``dataChunk`를 사용자 지정 형식 `specialFormat`으로 클립보드에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-134">This example writes the `DataObject``dataChunk` to the Clipboard in the custom format `specialFormat`.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_7.vb)]  
  
 <span data-ttu-id="ac0d3-135"><xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> 메서드를 사용하여 클립보드에 오디오 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-135">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> method to write audio data to the Clipboard.</span></span> <span data-ttu-id="ac0d3-136">이 예제에서는 바이트 배열 `musicReader`를 만들고, `cool.wav` 파일을 배열로 읽어온 다음 클립보드에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-136">This example creates the byte array `musicReader`, reads the file `cool.wav` into it, and then writes it to the Clipboard.</span></span>  
  
 [!code-vb[VbResourceTasks#5](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_8.vb)]  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac0d3-137">다른 사용자가 클립보드에 액세스할 수 있기 때문에 클립보드를 사용하여 암호 또는 기밀 데이터와 같은 중요한 정보를 저장하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ac0d3-137">Because the Clipboard can be accessed by other users, do not use it to store sensitive information, such as passwords or confidential data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac0d3-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac0d3-138">See also</span></span>  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>  
 [<span data-ttu-id="ac0d3-139">방법: XML 파일에서 개체 데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="ac0d3-139">How to: Read Object Data from an XML File</span></span>](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)  
 [<span data-ttu-id="ac0d3-140">방법: XML 파일에 개체 데이터 쓰기</span><span class="sxs-lookup"><span data-stu-id="ac0d3-140">How to: Write Object Data to an XML File</span></span>](../../../programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
