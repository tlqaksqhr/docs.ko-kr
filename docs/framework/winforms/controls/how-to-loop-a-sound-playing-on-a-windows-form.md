---
title: "방법: Windows Form에서 소리 재생 반복"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sound loops
- SoundPlayer class [Windows Forms], play looping
- sounds [Windows Forms], looping
- playing sounds [Windows Forms], looping
ms.assetid: ea95dd46-10a3-46c0-8263-4b205f00df7f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f7ade624f57f58a5ec91a5d993375c73d1cc26fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-loop-a-sound-playing-on-a-windows-form"></a><span data-ttu-id="ad847-102">방법: Windows Form에서 소리 재생 반복</span><span class="sxs-lookup"><span data-stu-id="ad847-102">How to: Loop a Sound Playing on a Windows Form</span></span>
<span data-ttu-id="ad847-103">다음 코드 예제에서는 반복해서 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="ad847-103">The following code example plays a sound repeatedly.</span></span> <span data-ttu-id="ad847-104">`stopPlayingButton_Click` 이벤트 처리기의 코드가 실행되면 현재 재생되는 모든 소리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad847-104">When the code in the `stopPlayingButton_Click` event handler runs, any sound currently playing stops.</span></span> <span data-ttu-id="ad847-105">소리가 재생되지 않으면 아무것도 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad847-105">If no sound is playing, nothing happens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad847-106">예</span><span class="sxs-lookup"><span data-stu-id="ad847-106">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ad847-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ad847-107">Compiling the Code</span></span>  
 <span data-ttu-id="ad847-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ad847-108">This example requires:</span></span>  
  
-   <span data-ttu-id="ad847-109">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="ad847-109">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="ad847-110">파일 이름 `"c:\Windows\Media\chimes.wav"`를 유효한 파일 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ad847-110">That you replace the file name `"c:\Windows\Media\chimes.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="ad847-111">[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad847-111">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="ad847-112">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad847-112">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="ad847-113">또한 [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad847-113">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ad847-114">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="ad847-114">Robust Programming</span></span>  
 <span data-ttu-id="ad847-115">파일 작업을 적절한 예외 처리 블록 내에 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad847-115">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="ad847-116">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ad847-116">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="ad847-117">경로 이름 형식이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ad847-117">The path name is malformed.</span></span> <span data-ttu-id="ad847-118">예를 들어 잘못된 문자를 포함하거나 공백만 포함합니다(<xref:System.ArgumentException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="ad847-118">For example, it contains characters that are not valid or it is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="ad847-119">경로가 읽기 전용입니다(<xref:System.IO.IOException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="ad847-119">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="ad847-120">경로 이름이 `Nothing`입니다(<xref:System.ArgumentNullException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="ad847-120">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="ad847-121">경로 이름이 너무 깁니다(<xref:System.IO.PathTooLongException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="ad847-121">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="ad847-122">경로가 잘못되었습니다(<xref:System.IO.DirectoryNotFoundException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="ad847-122">The path is invalid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="ad847-123">경로가 콜론 “:”뿐입니다(<xref:System.NotSupportedException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="ad847-123">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ad847-124">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="ad847-124">.NET Framework Security</span></span>  
 <span data-ttu-id="ad847-125">파일 이름을 바탕으로 파일 내용을 판단하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad847-125">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="ad847-126">예를 들어 Form1.vb 파일이 Visual Basic 소스 파일이 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad847-126">For example, the file Form1.vb may not be a Visual Basic source file.</span></span> <span data-ttu-id="ad847-127">응용 프로그램에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad847-127">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad847-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad847-128">See Also</span></span>  
 <xref:System.Media.SoundPlayer.PlayLooping%2A>  
 [<span data-ttu-id="ad847-129">방법: Windows Form에서 소리 재생</span><span class="sxs-lookup"><span data-stu-id="ad847-129">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)  
 [<span data-ttu-id="ad847-130">SoundPlayer 클래스 개요</span><span class="sxs-lookup"><span data-stu-id="ad847-130">SoundPlayer Class Overview</span></span>](../../../../docs/framework/winforms/controls/soundplayer-class-overview.md)
