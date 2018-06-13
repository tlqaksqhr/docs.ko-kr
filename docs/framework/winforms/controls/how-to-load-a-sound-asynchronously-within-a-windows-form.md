---
title: '방법: Windows Form에서 비동기적으로 소리 로드'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SoundPlayer class [Windows Forms], loading sounds asynchronously
- sounds [Windows Forms], loading on separate threads
- threading [Windows Forms], sounds
ms.assetid: 3b6a9296-1d5e-4d52-a4ba-94366d6fe302
ms.openlocfilehash: 9ebede03a3a9d2cc6db1cda2537bcaf30afcb2d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533571"
---
# <a name="how-to-load-a-sound-asynchronously-within-a-windows-form"></a><span data-ttu-id="e9451-102">방법: Windows Form에서 비동기적으로 소리 로드</span><span class="sxs-lookup"><span data-stu-id="e9451-102">How to: Load a Sound Asynchronously within a Windows Form</span></span>
<span data-ttu-id="e9451-103">다음 코드 예제는 URL에서 소리를 비동기적으로 로드한 다음 새 스레드에서 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="e9451-103">The following code example asynchronously loads a sound from an URL and then plays it on a new thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9451-104">예제</span><span class="sxs-lookup"><span data-stu-id="e9451-104">Example</span></span>  
 [!code-csharp[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e9451-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e9451-105">Compiling the Code</span></span>  
 <span data-ttu-id="e9451-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e9451-106">This example requires:</span></span>  
  
-   <span data-ttu-id="e9451-107">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="e9451-107">References to the System and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="e9451-108">파일 이름 `"http://www.tailspintoys.com/sounds/stop.wav"`를 유효한 파일 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e9451-108">That you replace the file name `"http://www.tailspintoys.com/sounds/stop.wav"` with a valid file name.</span></span>  
  
 <span data-ttu-id="e9451-109">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e9451-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="e9451-110">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9451-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="e9451-111">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e9451-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e9451-112">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="e9451-112">Robust Programming</span></span>  
 <span data-ttu-id="e9451-113">파일 작업을 적절한 예외 처리 블록 내에 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9451-113">File operations should be enclosed within appropriate exception-handling blocks.</span></span>  
  
 <span data-ttu-id="e9451-114">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e9451-114">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="e9451-115">경로 이름 형식이 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e9451-115">The path name is malformed.</span></span> <span data-ttu-id="e9451-116">예를 들어 잘못된 문자를 포함하거나 공백만 포함합니다(<xref:System.ArgumentException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="e9451-116">For example, it contains characters that are not valid or is only white space (<xref:System.ArgumentException> class).</span></span>  
  
-   <span data-ttu-id="e9451-117">경로가 읽기 전용입니다(<xref:System.IO.IOException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="e9451-117">The path is read-only (<xref:System.IO.IOException> class).</span></span>  
  
-   <span data-ttu-id="e9451-118">경로 이름이 `Nothing`입니다(<xref:System.ArgumentNullException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="e9451-118">The path name is `Nothing` (<xref:System.ArgumentNullException> class).</span></span>  
  
-   <span data-ttu-id="e9451-119">경로 이름이 너무 깁니다(<xref:System.IO.PathTooLongException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="e9451-119">The path name is too long (<xref:System.IO.PathTooLongException> class).</span></span>  
  
-   <span data-ttu-id="e9451-120">경로가 잘못되었습니다(<xref:System.IO.DirectoryNotFoundException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="e9451-120">The path is not valid (<xref:System.IO.DirectoryNotFoundException> class).</span></span>  
  
-   <span data-ttu-id="e9451-121">경로가 콜론 “:”뿐입니다(<xref:System.NotSupportedException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="e9451-121">The path is only a colon ":" (<xref:System.NotSupportedException> class).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e9451-122">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="e9451-122">.NET Framework Security</span></span>  
 <span data-ttu-id="e9451-123">파일 이름을 바탕으로 파일 내용을 판단하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9451-123">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="e9451-124">예를 들어 `Form1.vb` 파일이 Visual Basic 소스 파일이 아닐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9451-124">For example, the file `Form1.vb` may not be a Visual Basic source file.</span></span> <span data-ttu-id="e9451-125">응용 프로그램에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9451-125">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9451-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9451-126">See Also</span></span>  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <xref:System.Media.SoundPlayer.LoadCompleted>  
 <xref:System.Media.SoundPlayer.Play%2A>  
 [<span data-ttu-id="e9451-127">방법: Windows Form에서 소리 재생</span><span class="sxs-lookup"><span data-stu-id="e9451-127">How to: Play a Sound from a Windows Form</span></span>](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
