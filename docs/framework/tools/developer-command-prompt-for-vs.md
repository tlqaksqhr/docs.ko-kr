---
title: Visual Studio용 개발자 명령 프롬프트
ms.date: 06/18/2018
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
ms.openlocfilehash: 8e64facffd4face929b28d660ffd5210f127c3bd
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36315227"
---
# <a name="developer-command-prompt-for-visual-studio"></a><span data-ttu-id="687da-102">Visual Studio용 개발자 명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="687da-102">Developer Command Prompt for Visual Studio</span></span>

<span data-ttu-id="687da-103">Visual Studio용 개발자 명령 프롬프트는 .NET Framework 도구를 쉽게 사용할 수 있는 환경 변수를 자동으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-103">The Developer Command Prompt for Visual Studio automatically sets the environment variables that enable you to easily use .NET Framework tools.</span></span> <span data-ttu-id="687da-104">개발자 명령 프롬프트는 전체 또는 커뮤니티 버전의 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="687da-104">The Developer Command Prompt is installed with full or community editions of Visual Studio.</span></span> <span data-ttu-id="687da-105">Express 버전의 Visual Studio에서는 설치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="687da-105">It isn't installed with the Express versions of Visual Studio.</span></span>

> [!div class="button"]
[<span data-ttu-id="687da-106">Visual Studio 다운로드</span><span class="sxs-lookup"><span data-stu-id="687da-106">Download Visual Studio</span></span>](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

## <a name="searching-for-the-command-prompt-on-your-machine"></a><span data-ttu-id="687da-107">컴퓨터에서 명령 프롬프트 검색</span><span class="sxs-lookup"><span data-stu-id="687da-107">Searching for the Command Prompt on your machine</span></span>

<span data-ttu-id="687da-108">설치한 Visual Studio의 버전과 추가 SDK에 따라 많은 명령 프롬프트가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="687da-108">You may see many command prompts, depending on the version of Visual Studio and any additional SDKs you've installed.</span></span> <span data-ttu-id="687da-109">예를 들어 64비트 버전의 Visual Studio는 32비트 및 64비트 명령 프롬프트를 모두 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-109">For example, 64-bit versions of Visual Studio provide both 32-bit and 64-bit command prompts.</span></span> <span data-ttu-id="687da-110">(32비트 및 64비트 버전의 도구는 대부분 동일하지만, 몇 가지 도구는 32비트 및 64비트 환경에 맞게 변경됩니다.) 다음 단계가 작동하지 않는 경우 [컴퓨터에서 수동으로 파일 찾기](#manually-locating-the-files-on-your-machine) 또는 [Visual Studio 내에서 명령 프롬프트 실행](#running-command-prompt-from-inside-visual-studio)을 시도해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="687da-110">(The 32-bit and 64-bit versions of most tools are the same; however, a few tools make changes specific to 32-bit and 64-bit environments.) If the following steps don't work, you can try [Manually locating the files on your machine](#manually-locating-the-files-on-your-machine) or [Running command prompt from inside Visual Studio](#running-command-prompt-from-inside-visual-studio).</span></span>

### <a name="in-windows-10"></a><span data-ttu-id="687da-111">Windows 10</span><span class="sxs-lookup"><span data-stu-id="687da-111">In Windows 10</span></span>

1. <span data-ttu-id="687da-112">작업 표시줄의 검색 상자에 `dev` 또는 `developer command prompt`와 같은 도구 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-112">In the search box on the taskbar, start typing the name of the tool, such as `dev` or `developer command prompt`.</span></span> <span data-ttu-id="687da-113">그러면 검색 패턴과 일치하는 설치된 앱의 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="687da-113">This brings a list of installed apps that match your search pattern.</span></span> <span data-ttu-id="687da-114">다른 명령 프롬프트를 찾으려면 `prompt`와 같은 다른 검색어를 입력해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="687da-114">If you're looking for a different command prompt, try entering a different search term such as `prompt`.</span></span>

2. <span data-ttu-id="687da-115">**개발자 명령 프롬프트**(또는 사용할 명령 프롬프트)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-115">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-81"></a><span data-ttu-id="687da-116">Windows 8.1에서</span><span class="sxs-lookup"><span data-stu-id="687da-116">In Windows 8.1</span></span>

1. <span data-ttu-id="687da-117">키보드에서 Windows 로고 키 ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")를 눌러 **시작** 화면으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-117">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="687da-118">**시작** 화면에서 `CTRL + TAB`을 눌러 **앱** 목록을 열고 `V` 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="687da-118">On the **Start** screen, press `CTRL + TAB` to open the **Apps** list and then enter `V`.</span></span> <span data-ttu-id="687da-119">그러면 설치된 모든 Visual Studio 명령 프롬프트가 포함된 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="687da-119">This brings a list that includes all installed Visual Studio command prompts.</span></span>

3. <span data-ttu-id="687da-120">**개발자 명령 프롬프트**(또는 사용할 명령 프롬프트)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-120">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-8"></a><span data-ttu-id="687da-121">Windows 8에서</span><span class="sxs-lookup"><span data-stu-id="687da-121">In Windows 8</span></span>

1. <span data-ttu-id="687da-122">키보드에서 Windows 로고 키 ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")를 눌러 **시작** 화면으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-122">Go to the **Start** screen, by pressing the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") on your keyboard for example.</span></span>

2. <span data-ttu-id="687da-123">**시작**에서 Windows 로고 키 ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="687da-123">On the **Start** screen, press the Windows logo key ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo") `+ Z`.</span></span>

3. <span data-ttu-id="687da-124">화면 아래쪽에서 **앱 보기** 아이콘을 선택하고 `V` 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="687da-124">Choose the **Apps view** icon at the bottom of the screen and then enter `V`.</span></span> <span data-ttu-id="687da-125">그러면 설치된 모든 Visual Studio 명령 프롬프트가 포함된 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="687da-125">This brings a list that includes all installed Visual Studio command prompts.</span></span>

4. <span data-ttu-id="687da-126">**개발자 명령 프롬프트**(또는 사용할 명령 프롬프트)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-126">Choose the **Developer Command Prompt** (or the command prompt you want to use).</span></span>

### <a name="in-windows-7"></a><span data-ttu-id="687da-127">Windows 7에서</span><span class="sxs-lookup"><span data-stu-id="687da-127">In Windows 7</span></span>

1. <span data-ttu-id="687da-128">**시작**을 선택하고 **모든 프로그램**, **Microsoft Visual Studio**를 차례로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-128">Choose **Start**, expand **All Programs**, and then expand **Microsoft Visual Studio**.</span></span>

2. <span data-ttu-id="687da-129">설치한 Visual Studio 버전에 따라 **Visual Studio Tools**, **Visual Studio 명령 프롬프트** 또는 사용할 명령 프롬프트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-129">Depending on the version of Visual Studio you've installed, choose  **Visual Studio Tools**, **Visual Studio Command Prompt**, or the command prompt you want to use.</span></span>

<span data-ttu-id="687da-130">[Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) 또는 [이전 버전](https://developer.microsoft.com/windows/downloads/sdk-archive)과 같은 다른 SDK를 설치한 경우 ARM, x86 또는 x64 아키텍처에 대한 추가 명령 프롬프트가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="687da-130">If you have other SDKs installed such as the [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) or [previous versions](https://developer.microsoft.com/windows/downloads/sdk-archive) installed, you may see additional command prompts for ARM, x86, or x64 architectures.</span></span> <span data-ttu-id="687da-131">각 도구의 설명서를 확인하여 사용할 명령 프롬프트 버전을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-131">Check the documentation for the individual tools to determine which version of the command prompt you should use.</span></span>

## <a name="manually-locating-the-files-on-your-machine"></a><span data-ttu-id="687da-132">컴퓨터에서 수동으로 파일 찾기</span><span class="sxs-lookup"><span data-stu-id="687da-132">Manually locating the files on your machine</span></span>

<span data-ttu-id="687da-133">일반적으로 설치한 명령 프롬프트의 바로 가기는 C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools와 같이 Visual Studio에 대한 **시작 메뉴** 폴더에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="687da-133">Usually, the shortcuts for the command prompts you have installed are placed at the **Start Menu** folder for Visual Studio, such as in C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools.</span></span> <span data-ttu-id="687da-134">하지만 어떤 이유로 명령 프롬프트를 검색했는데 예상된 결과가 나타나지 않는 경우, 컴퓨터에서 수동으로 바로 가기를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="687da-134">But if for some reason, searching for the command prompt doesn't bring the expected results, you can try to manually locate the shortcut on your machine.</span></span> <span data-ttu-id="687da-135">*VsDevCmd.bat*와 같은 명령 프롬프트 파일의 이름 검색을 시도하거나 C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools와 같은 도구 폴더로 이동합니다(경로는 Visual Studio 버전, 에디션 및 설치 위치에 따라 바뀜).</span><span class="sxs-lookup"><span data-stu-id="687da-135">Try searching for the name of the command prompt file, such as *VsDevCmd.bat*, or go to the Tools folder such as C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools (path changes according to your Visual Studio version, edition, and installation location).</span></span>

## <a name="running-command-prompt-from-inside-visual-studio"></a><span data-ttu-id="687da-136">Visual Studio 내에서 명령 프롬프트 실행</span><span class="sxs-lookup"><span data-stu-id="687da-136">Running command prompt from inside Visual Studio</span></span>

<span data-ttu-id="687da-137">Visual Studio 개발자 명령 프롬프트 또는 다른 명령 프롬프트를 외부 도구 목록에 추가하여 Visual Studio의 도구 메뉴에 추가하면 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="687da-137">For easier access, you can add the Visual Studio Developer Command Prompt  or any other command prompt to the Tools menu on Visual Studio, by adding it to the external tools list.</span></span> <span data-ttu-id="687da-138">다음은 이 작업을 수행할 수 있는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="687da-138">This is how you can accomplish that:</span></span>

1. <span data-ttu-id="687da-139">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="687da-139">Open Visual Studio.</span></span>

2. <span data-ttu-id="687da-140">**도구** 메뉴를 선택하고 **외부 도구**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-140">Select the **Tools** menu and choose **External Tools**.</span></span>

3. <span data-ttu-id="687da-141">**외부 도구** 대화 상자에서 **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-141">On the **External Tools** dialog box, choose the **Add** button.</span></span> <span data-ttu-id="687da-142">새 항목이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="687da-142">A new entry appears.</span></span>

4. <span data-ttu-id="687da-143">`Command Prompt`와 같은 새 메뉴 항목에 대해 **제목**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-143">Enter a **Title** for your new menu item such as `Command Prompt`.</span></span>

5. <span data-ttu-id="687da-144">**명령** 필드에서 `%comspec%` 또는 `C:\Windows\System32\cmd.exe` 등의 시작할 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-144">In the **Command** field, specify the file you want to launch such as `%comspec%` or `C:\Windows\System32\cmd.exe`.</span></span>

6. <span data-ttu-id="687da-145">**인수** 필드에서 `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"`과 같이 사용할 특정 명령 프롬프트가 있는 위치를 지정합니다(이 명령은 Visual Studio 2017 Enterprise와 함께 설치된 개발자 명령 프롬프트를 시작함).</span><span class="sxs-lookup"><span data-stu-id="687da-145">In the **Arguments** field, specify where to find the specific command prompt you want to use such as `/k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\Tools\VsDevCmd.bat"` (this command launches the Developer Command Prompt that is installed with Visual Studio 2017 Enterprise).</span></span> <span data-ttu-id="687da-146">Visual Studio 버전, 에디션 및 설치 위치에 따라 이 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-146">Change this value according to your Visual Studio version, edition, and installation location.</span></span>

7. <span data-ttu-id="687da-147">**프로젝트 디렉터리**와 같은 **초기 디렉터리** 필드에 대한 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-147">Choose a value for the **Initial directory** field such as **Project Directory**.</span></span>

8. <span data-ttu-id="687da-148">**확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="687da-148">Choose the **OK** button.</span></span>

<span data-ttu-id="687da-149">그런 다음 새 메뉴 항목이 추가되고 **도구** 메뉴에서 명령 프롬프트에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="687da-149">After that, the new menu item is added and you can access the command prompt from the **Tools** menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="687da-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="687da-150">See also</span></span>

 [<span data-ttu-id="687da-151">도구</span><span class="sxs-lookup"><span data-stu-id="687da-151">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="687da-152">외부 도구 관리</span><span class="sxs-lookup"><span data-stu-id="687da-152">Managing External Tools</span></span>](/visualstudio/ide/managing-external-tools)  
