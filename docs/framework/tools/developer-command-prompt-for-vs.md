---
title: Visual Studio용 개발자 명령 프롬프트
ms.date: 03/30/2017
helpviewer_keywords:
- command prompt, Windows SDK
- Visual Studio command prompt
- command prompt, Visual Studio
- SDK command prompt
- tools [.NET Framework], setting environment variables
- environment variables, setting for tools
- developer command prompt
ms.assetid: 94fcf524-9045-4993-bfb2-e2d8bad44219
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d3ff897e37e3fa2f7202a54c05c8093ba05282c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402030"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="21605-102">Visual Studio용 개발자 명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="21605-102">Developer Command Prompt for Visual Studio</span></span>
<span data-ttu-id="21605-103">Visual Studio용 개발자 명령 프롬프트는 .NET Framework 도구를 쉽게 사용할 수 있는 환경 변수를 자동으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-103">The Developer Command Prompt for Visual Studio automatically sets the environment variables that enable you to easily use .NET Framework tools.</span></span> <span data-ttu-id="21605-104">개발자 명령 프롬프트는 전체 또는 커뮤니티 버전의 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="21605-104">The Developer Command Prompt is installed with full or community editions of Visual Studio.</span></span> <span data-ttu-id="21605-105">Express 버전의 Visual Studio에서는 설치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21605-105">It is not installed with the Express versions of Visual Studio.</span></span>  
  
<a name="find"></a>   
## <a name="searching-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="21605-106">컴퓨터에서 명령 프롬프트 검색</span><span class="sxs-lookup"><span data-stu-id="21605-106">Searching for the Command Prompt on your machine</span></span>  
 <span data-ttu-id="21605-107">설치한 Visual Studio의 버전과 추가 SDK에 따라 여러 개의 명령 프롬프트가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21605-107">You may see multiple command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="21605-108">예를 들어 64비트 버전의 Visual Studio는 32비트 및 64비트 명령 프롬프트를 모두 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-108">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="21605-109">(32비트 및 64비트 버전의 대부분의 도구는 동일하나, 몇 가지 도구에서는 32비트 및 64비트 환경에 맞게 변경됩니다.) 아래 단계가 작동하지 않는 경우 [컴퓨터에서 수동으로 파일 찾기](#alternative) 또는 [Visual Studio 내에서 명령 프롬프트 실행](#visualstudio)을 시도해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21605-109">(The 32-bit and 64-bit versions of most tools are identical; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the steps below don't work, you can try [Manually locating the files on your machine](#alternative) or [Running command prompt from inside Visual Studio](#visualstudio).</span></span>  
  
 <span data-ttu-id="21605-110">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="21605-110">**In Windows 10**</span></span>  
  
1.  <span data-ttu-id="21605-111">키보드에서 Windows 로고 키 ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")를 눌러 **시작** 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="21605-111">Open the **Start** menu, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="21605-112">**시작** 메뉴에서 `dev`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-112">On the **Start** menu, enter `dev`.</span></span> <span data-ttu-id="21605-113">그러면 검색 패턴에 일치하는 설치된 응용 프로그램의 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="21605-113">This will bring a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="21605-114">다른 명령 프롬프트를 찾으려면 `prompt`와 같은 다른 검색어를 입력해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="21605-114">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>  
  
3.  <span data-ttu-id="21605-115">**개발자 명령 프롬프트**(또는 사용할 명령 프롬프트)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-115">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="21605-116">**Windows 8.1**</span><span class="sxs-lookup"><span data-stu-id="21605-116">**In Windows 8.1**</span></span>  
  
1.  <span data-ttu-id="21605-117">키보드에서 Windows 로고 키 ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")를 눌러 **시작** 화면으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-117">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="21605-118">**시작** 화면에서 `CTRL + TAB`을 눌러 **앱** 목록을 열고 `V` 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="21605-118">On the **Start** screen, press `CTRL + TAB` to open the **Apps** list and then enter `V`.</span></span> <span data-ttu-id="21605-119">그러면 설치된 모든 Visual Studio 명령 프롬프트가 포함된 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="21605-119">This will bring a list that includes all installed Visual Studio command prompts.</span></span>  
  
3.  <span data-ttu-id="21605-120">**개발자 명령 프롬프트**(또는 사용할 명령 프롬프트)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-120">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="21605-121">**Windows 8**</span><span class="sxs-lookup"><span data-stu-id="21605-121">**In Windows 8**</span></span>  
  
1.  <span data-ttu-id="21605-122">키보드에서 Windows 로고 키 ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")를 눌러 **시작** 화면으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-122">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>  
  
2.  <span data-ttu-id="21605-123">**시작**에서 Windows 로고 키 ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="21605-123">On the **Start** screen, press the Windows logo key ![Windows logo](../../../docs/framework/get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>  
  
3.  <span data-ttu-id="21605-124">화면 아래쪽에서 **앱 보기** 아이콘을 선택하고 `V` 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="21605-124">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="21605-125">그러면 설치된 모든 Visual Studio 명령 프롬프트가 포함된 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="21605-125">This will bring a list that includes all installed Visual Studio command prompts.</span></span>  
  
4.  <span data-ttu-id="21605-126">**개발자 명령 프롬프트**(또는 사용할 명령 프롬프트)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-126">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>  
  
 <span data-ttu-id="21605-127">**Windows 7**</span><span class="sxs-lookup"><span data-stu-id="21605-127">**In Windows 7**</span></span>  
  
1.  <span data-ttu-id="21605-128">**시작**을 선택하고 **모든 프로그램**, **Microsoft Visual Studio**를 차례로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-128">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="21605-129">설치한 Visual Studio 버전에 따라 **Visual Studio Tools**, **Visual Studio 명령 프롬프트** 또는 사용할 명령 프롬프트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-129">Depending on the version of Visual Studio you have installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>  
  
 <span data-ttu-id="21605-130">[Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) 또는 [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk)를 설치한 경우 ARM, x86 또는 x64 아키텍처의 추가 명령 프롬프트가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21605-130">If you have the [Windows SDK](http://msdn.microsoft.com/windows/desktop/aa904949) or [Windows Phone SDK](https://dev.windowsphone.com/downloadsdk) installed, you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="21605-131">각 도구의 설명서를 확인하여 사용할 명령 프롬프트 버전을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-131">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>  
  
<a name="alternative"></a>   
## <a name="manually-locating-the-files-on-your-machine"></a><span data-ttu-id="21605-132">컴퓨터에서 수동으로 파일 찾기</span><span class="sxs-lookup"><span data-stu-id="21605-132">Manually locating the files on your machine</span></span>  
  <span data-ttu-id="21605-133">일반적으로 설치한 명령 프롬프트의 바로 가기는 C:\ProgramData\Microsoft\Windows\시작 메뉴\Programs\Visual Studio 2015\Visual Studio Tools와 같이 Visual Studio에 대한 **시작 메뉴** 폴더에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="21605-133">Usually, the shortcuts for the command prompts you have installed will be placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2015\Visual Studio Tools.</span></span>    <span data-ttu-id="21605-134">하지만 어떤 이유로 명령 프롬프트를 검색했는데 예상된 결과를 생성하지 않는 경우, 컴퓨터에서 수동으로 바로 가기를 찾아 이를 사용하려고 시도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21605-134">But if for some reason, searching for the command prompt doesn't yield the expected results, you can try to manually locate the shortcut on your machine in order to use it.</span></span>   <span data-ttu-id="21605-135">VsDevCmd.bat와 같은 명령 프롬프트 파일의 이름 검색을 시도하거나 C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools와 같은 도구 폴더로 이동합니다(경로는 Visual Studio 버전 및 설치 위치에 따라 바뀜).</span><span class="sxs-lookup"><span data-stu-id="21605-135">Try searching for the name of the command prompt file such as VsDevCmd.bat or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools (path will change according to your Visual Studio version and installation location).</span></span>  
  
<a name="visualstudio"></a>   
## <a name="running-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="21605-136">Visual Studio 내에서 명령 프롬프트 실행</span><span class="sxs-lookup"><span data-stu-id="21605-136">Running command prompt from inside Visual Studio</span></span>  
 <span data-ttu-id="21605-137">Visual Studio 개발자 명령 프롬프트 또는 다른 명령 프롬프트를 외부 도구 목록에 추가하여 Visual Studio의 도구 메뉴에 추가하면 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21605-137">For easier access, you can add the Visual Studio Developer Command Prompt  or any other command prompt to the Tools menu on Visual Studio, by adding it to the external tools list.</span></span> <span data-ttu-id="21605-138">다음은 이 작업을 수행할 수 있는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="21605-138">This is how you can accomplish that:</span></span>  
  
1.  <span data-ttu-id="21605-139">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="21605-139">Open Visual Studio.</span></span>  
  
2.  <span data-ttu-id="21605-140">**도구** 메뉴를 선택하고 **외부 도구...** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-140">Select the **Tools** menu and choose **External Tools...**.</span></span>  
  
3.  <span data-ttu-id="21605-141">**외부 도구** 대화 상자에서 **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-141">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="21605-142">새 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="21605-142">A new entry appears</span></span>  
  
4.  <span data-ttu-id="21605-143">`Command Prompt`와 같은 새 메뉴 항목에 대해 **제목**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-143">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>  
  
5.  <span data-ttu-id="21605-144">**명령** 필드에서 `%comspec%` 또는 `C:\Windows\System32\cmd.exe` 등의 시작할 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-144">In the **Command** field, specify the file you want to launch such as `%comspec%` or `C:\Windows\System32\cmd.exe` .</span></span>  
  
6.  <span data-ttu-id="21605-145">**인수** 필드에서 `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"` 등의 사용하려는 특정 명령 프롬프트가 있는 위치를 지정합니다(이렇게 하면 [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]로 설치된 개발자 명령 프롬프트를 시작함).</span><span class="sxs-lookup"><span data-stu-id="21605-145">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\Tools\VsDevCmd.bat"` (this will launch the Developer Command Prompt installed with [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]).</span></span> <span data-ttu-id="21605-146">Visual Studio 버전 및 설치 위치에 따라 이 값을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-146">This value needs to be changed according to your Visual Studio version and installation location.</span></span>  
  
7.  <span data-ttu-id="21605-147">**프로젝트 디렉터리**와 같은 **초기 디렉터리** 필드에 대한 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-147">Choose a value for the **Initial directory** field such as **Project Directory** .</span></span>  
  
8.  <span data-ttu-id="21605-148">**확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="21605-148">Choose the **OK** button.</span></span>  
  
 <span data-ttu-id="21605-149">그런 다음 새 메뉴 항목이 추가되고 **도구** 메뉴에서 명령 프롬프트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21605-149">After that, the new menu item is added and you can access the command prompt from the **Tools** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21605-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21605-150">See Also</span></span>  
 [<span data-ttu-id="21605-151">도구</span><span class="sxs-lookup"><span data-stu-id="21605-151">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="21605-152">외부 도구 관리</span><span class="sxs-lookup"><span data-stu-id="21605-152">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)
