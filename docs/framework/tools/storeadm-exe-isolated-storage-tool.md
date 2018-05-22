---
title: Storeadm.exe(격리된 저장소 도구)
ms.date: 03/30/2017
helpviewer_keywords:
- Storeadm.exe
- listing stores for current user
- Isolated Storage tool
- stores, current user
- removing stores
ms.assetid: b81202b8-d91d-4b23-9c53-4a112f74a44a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c9b8d0680a50d9945bef0d03d10e45750fc49a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="storeadmexe-isolated-storage-tool"></a><span data-ttu-id="37c08-102">Storeadm.exe(격리된 저장소 도구)</span><span class="sxs-lookup"><span data-stu-id="37c08-102">Storeadm.exe (Isolated Storage Tool)</span></span>
<span data-ttu-id="37c08-103">격리된 저장소 도구를 사용하면 현재 사용자의 기존 저장소를 모두 표시하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-103">The Isolated Storage tool lists or removes all existing stores for the current user.</span></span>  
  
 <span data-ttu-id="37c08-104">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="37c08-105">이 도구를 실행하려면 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-105">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="37c08-106">자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="37c08-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="37c08-107">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37c08-108">구문</span><span class="sxs-lookup"><span data-stu-id="37c08-108">Syntax</span></span>  
  
```  
storeadm [/list][/machine][/remove][/roaming][/quiet]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37c08-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37c08-109">Parameters</span></span>  
  
|<span data-ttu-id="37c08-110">옵션</span><span class="sxs-lookup"><span data-stu-id="37c08-110">Option</span></span>|<span data-ttu-id="37c08-111">설명</span><span class="sxs-lookup"><span data-stu-id="37c08-111">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="37c08-112">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="37c08-112">**/h**[**elp**]</span></span>|<span data-ttu-id="37c08-113">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-113">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="37c08-114">**/list**</span><span class="sxs-lookup"><span data-stu-id="37c08-114">**/list**</span></span>|<span data-ttu-id="37c08-115">현재 사용자의 기존 저장소를 모두 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-115">Displays all existing stores for the current user.</span></span> <span data-ttu-id="37c08-116">여기에는 해당 사용자가 실행한 모든 응용 프로그램 또는 어셈블리의 저장소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-116">This includes the stores for all applications or assemblies executed by this user.</span></span>|  
|<span data-ttu-id="37c08-117">**/machine**</span><span class="sxs-lookup"><span data-stu-id="37c08-117">**/machine**</span></span>|<span data-ttu-id="37c08-118">컴퓨터 저장소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-118">Selects the machine store.</span></span> <span data-ttu-id="37c08-119">이 옵션을 **/list** 또는 **/remove** 옵션과 함께 사용하면 해당 작업이 컴퓨터 저장소에 적용되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-119">Use this option with the **/list** or **/remove** option to specify that the action should apply to the machine store.</span></span><br /><br /> <span data-ttu-id="37c08-120">.NET Framework 2.0에 새로 추가된 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-120">New in the .NET Framework 2.0</span></span>|  
|<span data-ttu-id="37c08-121">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="37c08-121">**/quiet**</span></span>|<span data-ttu-id="37c08-122">자동 모드를 지정합니다. 오류 메시지만 표시되도록 자세한 정보는 출력하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-122">Specifies quiet mode; suppresses informational output so that only error messages appear.</span></span>|  
|<span data-ttu-id="37c08-123">**/remove**</span><span class="sxs-lookup"><span data-stu-id="37c08-123">**/remove**</span></span>|<span data-ttu-id="37c08-124">현재 사용자의 기존 저장소를 모두 영구 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-124">Permanently removes all existing stores for the current user.</span></span>|  
|<span data-ttu-id="37c08-125">**/roaming**</span><span class="sxs-lookup"><span data-stu-id="37c08-125">**/roaming**</span></span>|<span data-ttu-id="37c08-126">로밍 저장소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-126">Selects the roaming store.</span></span> <span data-ttu-id="37c08-127">이 옵션을 **/list** 또는 **/remove** 옵션과 함께 사용하면 해당 작업이 로밍 저장소에 적용되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-127">Use this option with the **/list** or **/remove** options to specify that the action should apply to the roaming store.</span></span>|  
|<span data-ttu-id="37c08-128">**/?**</span><span class="sxs-lookup"><span data-stu-id="37c08-128">**/?**</span></span>|<span data-ttu-id="37c08-129">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-129">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37c08-130">설명</span><span class="sxs-lookup"><span data-stu-id="37c08-130">Remarks</span></span>  
 <span data-ttu-id="37c08-131">아무 옵션도 지정하지 않고 명령줄에서 Storeadm.exe를 실행하면 이 도구의 구문 및 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-131">Running Storeadm.exe from the command line without specifying any options displays the syntax and options for the tool.</span></span>  
  
 <span data-ttu-id="37c08-132">**/list** 옵션 및 **/remove** 옵션은 일반적으로 한 번에 하나만 사용되지만 둘 이상의 옵션을 지정한 경우에는 명령줄에 표시된 순서대로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-132">The **/list** and **/remove** options are typically used one at a time; however, if two or more options are specified they will be performed in the order in which they appear on the command line.</span></span>  
  
 <span data-ttu-id="37c08-133">응용 프로그램에서는 두 개의 사용자용 저장소 중 하나 또는 컴퓨터 저장소를 선택하여 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-133">Applications have a choice of saving to one of two stores for a user or to the machine store:</span></span>  
  
-   <span data-ttu-id="37c08-134">로컬 저장소는 해당 사용자에 대해 사용자 데이터 로밍이 사용되는 경우에도 로밍되지 않는 위치에 있습니다(Windows 2000 이상의 경우).</span><span class="sxs-lookup"><span data-stu-id="37c08-134">The local store exists in a location that is guaranteed not to roam (on Windows 2000 and later) even if user data roaming is enabled for the user.</span></span>  
  
-   <span data-ttu-id="37c08-135">로밍 저장소는 로밍할 수 있는 위치에 있지만 Windows NT 관리를 통해 해당 사용자에 대해 로밍이 사용되는 경우에만 로밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-135">The roaming store exists in a location that is able to roam, but can only do so if roaming is enabled for the user via Windows NT administration.</span></span>  
  
-   <span data-ttu-id="37c08-136">컴퓨터 저장소는 컴퓨터의 모든 사용자에게 공통적이며 해당 컴퓨터의 공용 디렉터리에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-136">The machine store is common to all users on a machine and is stored under a common directory on that machine.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="37c08-137">컴퓨터 저장소는 .NET Framework 버전 2.0에서 새로 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-137">The machine store is new in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="37c08-138">사용자에 대해 로밍이 실제로 사용되는지 여부는 Storeadm.exe의 관리에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-138">Whether roaming is actually enabled for the user does not affect the administration of Storeadm.exe.</span></span> <span data-ttu-id="37c08-139">옵션 없이 이 도구를 실행하면 모든 작업이 로컬 저장소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-139">Running the tool without any options applies all actions to the local store.</span></span> <span data-ttu-id="37c08-140">**/roaming** 옵션을 지정하여 이 도구를 실행하면 모든 작업이 로밍 가능한 저장소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-140">Running the tool with the **/roaming** option applies all actions to the store that is able to roam.</span></span> <span data-ttu-id="37c08-141">**/machine** 옵션을 지정하여 이 도구를 실행하면 모든 작업이 컴퓨터 저장소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="37c08-141">Running the tool with the **/machine** option applies all actions to the machine store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37c08-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="37c08-142">See Also</span></span>  
 [<span data-ttu-id="37c08-143">도구</span><span class="sxs-lookup"><span data-stu-id="37c08-143">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="37c08-144">격리된 저장소</span><span class="sxs-lookup"><span data-stu-id="37c08-144">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)  
 [<span data-ttu-id="37c08-145">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="37c08-145">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
