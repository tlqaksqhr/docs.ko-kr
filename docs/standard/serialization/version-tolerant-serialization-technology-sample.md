---
title: "Version Tolerant Serialization 기술 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a183664-bfbf-4ff0-96f6-c836284ea916
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bde508f6fd578050501f95f2f9316c6c458017de
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="version-tolerant-serialization-technology-sample"></a><span data-ttu-id="fa78b-102">Version Tolerant Serialization 기술 샘플</span><span class="sxs-lookup"><span data-stu-id="fa78b-102">Version Tolerant Serialization Technology Sample</span></span>
[<span data-ttu-id="fa78b-103">샘플 다운로드</span><span class="sxs-lookup"><span data-stu-id="fa78b-103">Download Sample</span></span>](http://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Runtime%20Serialization/VTS.zip.exe)  
  
 <span data-ttu-id="fa78b-104">이 샘플에서는 .NET Serialization의 버전 내결함성 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa78b-104">This sample demonstrates the version tolerance features of .NET Serialization.</span></span> <span data-ttu-id="fa78b-105">이 샘플에서는 서로 다른 버전의 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>를 사용하여 데이터를 serialize하거나 deserialize하는 두 개의 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa78b-105">The sample builds applications that use different versions of a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> to serialize and deserialize data.</span></span> <span data-ttu-id="fa78b-106">서로 다른 형식 버전이 사용되지만 응용 프로그램은 서로 원활하게 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="fa78b-106">Despite the presence of different type versions, the applications communicate seamlessly.</span></span> <span data-ttu-id="fa78b-107">자세한 내용은 [버전 독립적 Serialization](../../../docs/standard/serialization/version-tolerant-serialization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa78b-107">For more information, see [Version Tolerant Serialization](../../../docs/standard/serialization/version-tolerant-serialization.md).</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="fa78b-108">명령 프롬프트를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="fa78b-108">To build the sample using the command prompt</span></span>  
  
1.  <span data-ttu-id="fa78b-109">명령 프롬프트 창을 열고 V1 응용 프로그램 또는 V2 응용 프로그램 아래에 있는 샘플에 대한 언어별 하위 디렉터리 중 하나로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fa78b-109">Open a Command Prompt window and navigate to one of the language-specific subdirectories (under V1 Application or V2 Application) for the sample.</span></span>  
  
2.  <span data-ttu-id="fa78b-110">명령줄에 **msbuild.exe \<ver> application.sln**을 입력합니다. 여기서 \<ver>은 v1 또는 v2입니다.</span><span class="sxs-lookup"><span data-stu-id="fa78b-110">Type **msbuild.exe \<ver> application.sln** at the command line (where \<ver> is either v1 or v2).</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="fa78b-111">Visual Studio를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="fa78b-111">To build the sample using Visual Studio</span></span>  
  
1.  <span data-ttu-id="fa78b-112">[!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)]를 열고 샘플에 대한 언어별 하위 디렉터리 중 하나로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fa78b-112">Open [!INCLUDE[fileExplorer](../../../includes/fileexplorer-md.md)] and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2.  <span data-ttu-id="fa78b-113">이전 단계에서 선택한 디렉터리의 V1 Application 하위 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fa78b-113">Navigate to the V1 Application subdirectory of the directory you selected in the previous step.</span></span>  
  
3.  <span data-ttu-id="fa78b-114">V1 Application.sln의 아이콘을 두 번 클릭하여 Visual Studio에서 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fa78b-114">Double-click the icon for V1 Application.sln to open the file in Visual Studio.</span></span>  
  
4.  <span data-ttu-id="fa78b-115">**빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fa78b-115">On the **Build** menu, click **Build Solution**.</span></span>  
  
5.  <span data-ttu-id="fa78b-116">V2 Application 하위 디렉터리로 이동하고 이전의 두 단계를 반복하여 V2 Application을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="fa78b-116">Navigate to the V2 Application subdirectory and repeat the two previous steps to build the V2 Application.</span></span>  
  
 <span data-ttu-id="fa78b-117">응용 프로그램은 각각의 프로젝트 디렉터리에 있는 기본 \bin 또는 \bin\Debug 하위 디렉터리에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa78b-117">The applications will be built in the default \bin or \bin\Debug subdirectories of their respective project directories.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="fa78b-118">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="fa78b-118">To run the sample</span></span>  
  
1.  <span data-ttu-id="fa78b-119">명령 프롬프트 창에서 샘플 응용 프로그램을 빌드할 때 선택한 언어별 하위 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fa78b-119">In the Command Prompt window, navigate to the language-specific subdirectory that you selected when you built the sample applications.</span></span>  
  
2.  <span data-ttu-id="fa78b-120">명령줄에 **runme.cmd**를 입력하여 두 응용 프로그램을 한 번에 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa78b-120">Type **runme.cmd** at the command line to run both applications at once.</span></span>  
  
 <span data-ttu-id="fa78b-121">새 실행 파일이 있는 디렉터리로 이동한 다음 하나씩 순서대로 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa78b-121">Alternatively, navigate to the directories that contain the new executables and run them sequentially.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa78b-122">이 샘플에서는 콘솔 응용 프로그램을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="fa78b-122">The sample builds console applications.</span></span> <span data-ttu-id="fa78b-123">출력을 보려면 응용 프로그램을 명령 프롬프트 창에서 시작하고 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa78b-123">You must launch and run them in a Command Prompt window to view their output.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa78b-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa78b-124">See Also</span></span>  
 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>  
 <xref:System.IO.FileStream>
