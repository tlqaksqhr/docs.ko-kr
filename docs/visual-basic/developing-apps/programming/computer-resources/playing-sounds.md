---
title: "소리 재생(Visual Basic)"
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
- system sounds, playing
- system sounds
- playing sounds, Visual Basic
- sound loops
- My.Computer.Audio object, tasks
- sounds, playing
- sounds, background
- playing sounds
ms.assetid: f0d9e4ab-57c7-47b6-86d3-99ff07078040
caps.latest.revision: 21
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
ms.openlocfilehash: a15efff54bd54fdaced6c741cd6acf5c8b544cdd
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="playing-sounds-visual-basic"></a><span data-ttu-id="0c423-102">소리 재생(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c423-102">Playing Sounds (Visual Basic)</span></span>
<span data-ttu-id="0c423-103">`My.Computer.Audio` 개체는 소리 재생 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-103">The `My.Computer.Audio` object provides methods for playing sounds.</span></span>  
  
## <a name="playing-sounds"></a><span data-ttu-id="0c423-104">소리 재생</span><span class="sxs-lookup"><span data-stu-id="0c423-104">Playing Sounds</span></span>  
 <span data-ttu-id="0c423-105">백그라운드 재생을 사용하면 응용 프로그램이 소리가 재생되는 동안 다른 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-105">Background playing lets the application execute other code while the sound plays.</span></span> <span data-ttu-id="0c423-106">`My.Computer.Audio.Play` 메서드를 사용하면 응용 프로그램이 한 번에 하나의 배경 소리만 재생할 수 있습니다. 응용 프로그램이 새 배경 소리를 재생하는 경우 이전 배경 소리의 재생을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-106">The `My.Computer.Audio.Play` method allows the application to play only one background sound at a time; when the application plays a new background sound, it stops playing the previous background sound.</span></span> <span data-ttu-id="0c423-107">소리를 재생하고 완료될 때까지 기다릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-107">You can also play a sound and wait for it to complete.</span></span>  
  
 <span data-ttu-id="0c423-108">다음 예제에서는 `My.Computer.Audio.Play` 메서드가 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-108">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="0c423-109">`AudioPlayMode.WaitToComplete`를 지정하면 `My.Computer.Audio.Play`는 호출하는 코드가 계속되기 전에 소리가 완료될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-109">When `AudioPlayMode.WaitToComplete` is specified, `My.Computer.Audio.Play` waits until the sound completes before calling code continues.</span></span> <span data-ttu-id="0c423-110">이 예제를 사용하는 경우 파일 이름이 컴퓨터에 있는 .wav 사운드 파일을 가리키는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-110">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer</span></span>  
  
 <span data-ttu-id="0c423-111">[!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c423-111">[!code-vb[VbVbalrMyComputer#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_1.vb)]</span></span>  
  
 <span data-ttu-id="0c423-112">다음 예제에서는 `My.Computer.Audio.Play` 메서드가 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-112">In the following example, the `My.Computer.Audio.Play` method plays a sound.</span></span> <span data-ttu-id="0c423-113">이 예제를 사용하는 경우 응용 프로그램 리소스에 Waterfall로 이름이 지정된 .wav 사운드 파일이 포함되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-113">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 <span data-ttu-id="0c423-114">[!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c423-114">[!code-vb[VbVbalrMyComputer#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_2.vb)]</span></span>  
  
## <a name="playing-looping-sounds"></a><span data-ttu-id="0c423-115">소리 반복 재생</span><span class="sxs-lookup"><span data-stu-id="0c423-115">Playing Looping Sounds</span></span>  
 <span data-ttu-id="0c423-116">다음 예제에서 `My.Computer.Audio.Play` 메서드는 `PlayMode.BackgroundLoop`가 지정된 경우 백그라운드에서 지정한 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-116">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="0c423-117">이 예제를 사용하는 경우 파일 이름이 컴퓨터에 있는 .wav 사운드 파일을 가리키는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-117">When using this example, you should ensure that the file name refers to a .wav sound file that is on your computer.</span></span>  
  
 <span data-ttu-id="0c423-118">[!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c423-118">[!code-vb[VbVbalrMyComputer#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_3.vb)]</span></span>  
  
 <span data-ttu-id="0c423-119">다음 예제에서 `My.Computer.Audio.Play` 메서드는 `PlayMode.BackgroundLoop`가 지정된 경우 백그라운드에서 지정한 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-119">In the following example, the `My.Computer.Audio.Play` method plays the specified sound in the background when `PlayMode.BackgroundLoop` is specified.</span></span> <span data-ttu-id="0c423-120">이 예제를 사용하는 경우 응용 프로그램 리소스에 Waterfall로 이름이 지정된 .wav 사운드 파일이 포함되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-120">When using this example, you should ensure that the application resources include a .wav sound file that is named Waterfall.</span></span>  
  
 <span data-ttu-id="0c423-121">[!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c423-121">[!code-vb[VbVbalrMyComputer#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_4.vb)]</span></span>  
  
 <span data-ttu-id="0c423-122">앞의 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-122">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="0c423-123">코드 조각 선택에서 **Windows Forms 응용 프로그램 > 소리**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-123">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="0c423-124">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c423-124">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="0c423-125">일반적으로 응용 프로그램이 소리를 반복 재생하는 경우 결국 소리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-125">In general, when an application plays a looping sound, it should eventually stop the sound.</span></span>  
  
## <a name="stopping-the-playing-of-sounds-in-the-background"></a><span data-ttu-id="0c423-126">백그라운드에서 소리 재생 중지</span><span class="sxs-lookup"><span data-stu-id="0c423-126">Stopping the Playing of Sounds in the Background</span></span>  
 <span data-ttu-id="0c423-127">`My.Computer.Audio.Stop` 메서드를 사용하여 응용 프로그램이 백그라운드에서 현재 재생 중인 소리나 소리 반복 재생을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-127">Use the `My.Computer.Audio.Stop` method to stop the application's currently playing background or looping sound.</span></span>  
  
 <span data-ttu-id="0c423-128">일반적으로 응용 프로그램이 소리를 반복 재생하는 경우 어느 시점에 소리가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-128">In general, when an application plays a looping sound, it should stop the sound at some point.</span></span>  
  
 <span data-ttu-id="0c423-129">다음 예제에서는 백그라운드에서 재생 중인 소리를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-129">The following example stops a sound that is playing in the background.</span></span>  
  
 <span data-ttu-id="0c423-130">[!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c423-130">[!code-vb[VbVbalrMyComputer#18](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_5.vb)]</span></span>  
  
 <span data-ttu-id="0c423-131">앞의 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-131">The preceding code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="0c423-132">코드 조각 선택에서 **Windows Forms 응용 프로그램 > 소리**에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-132">In the code snippet picker, it is located in **Windows Forms Applications > Sound**.</span></span> <span data-ttu-id="0c423-133">자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0c423-133">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="playing-system-sounds"></a><span data-ttu-id="0c423-134">시스템 소리 재생</span><span class="sxs-lookup"><span data-stu-id="0c423-134">Playing System Sounds</span></span>  
 <span data-ttu-id="0c423-135">`My.Computer.Audio.PlaySystemSound` 메서드를 사용하여 지정된 시스템 소리를 재생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-135">Use the `My.Computer.Audio.PlaySystemSound` method to play the specified system sound.</span></span>  
  
 <span data-ttu-id="0c423-136">`My.Computer.Audio.PlaySystemSound` 메서드는 <xref:System.Media.SystemSound> 클래스의 공유 멤버 중 하나를 매개 변수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-136">The `My.Computer.Audio.PlaySystemSound` method takes as a parameter one of the shared members from the <xref:System.Media.SystemSound> class.</span></span> <span data-ttu-id="0c423-137">시스템 소리 <xref:System.Media.SystemSounds.Asterisk%2A>는 일반적으로 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-137">The system sound <xref:System.Media.SystemSounds.Asterisk%2A> generally denotes errors.</span></span>  
  
 <span data-ttu-id="0c423-138">다음 예제에서는 `My.Computer.Audio.PlaySystemSound` 메서드를 사용하여 시스템 소리를 재생합니다.</span><span class="sxs-lookup"><span data-stu-id="0c423-138">The following example uses the `My.Computer.Audio.PlaySystemSound` method to play a system sound.</span></span>  
  
 <span data-ttu-id="0c423-139">[!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c423-139">[!code-vb[VbVbalrMyComputer#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/playing-sounds_6.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c423-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c423-140">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Audio>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.PlaySystemSound%2A>   
 <xref:Microsoft.VisualBasic.Devices.Audio.Stop%2A>   
 <xref:Microsoft.VisualBasic.AudioPlayMode>

