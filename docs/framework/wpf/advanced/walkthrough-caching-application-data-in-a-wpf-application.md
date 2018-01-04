---
title: "연습: WPF 응용 프로그램에서 응용 프로그램 데이터 캐싱"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81d808b982852d5cc6dc187a3c8389748a0dc0bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="cf5d4-102">연습: WPF 응용 프로그램에서 응용 프로그램 데이터 캐싱</span><span class="sxs-lookup"><span data-stu-id="cf5d4-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="cf5d4-103">캐싱을 사용하면 빠른 액세스를 위해 데이터를 메모리에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="cf5d4-104">데이터 다시 액세스 하는 응용 프로그램 원본에서 검색 하는 대신 캐시에서 데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-104">When the data is accessed again, applications can get the data from the cache instead retrieving it from the original source.</span></span> <span data-ttu-id="cf5d4-105">이 경우 성능과 확장성이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-105">This can improve performance and scalability.</span></span> <span data-ttu-id="cf5d4-106">또한 캐싱을 사용하면 데이터 소스를 일시적으로 사용할 수 없는 경우에도 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>  
  
 <span data-ttu-id="cf5d4-107">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 에서 캐싱을 사용할 수 있도록 하는 클래스를 제공 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-107">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides classes that enable you to use caching in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="cf5d4-108">이러한 클래스에는 <xref:System.Runtime.Caching> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf5d4-109"><xref:System.Runtime.Caching> 네임 스페이스는의 새로운는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-109">The <xref:System.Runtime.Caching> namespace is new in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="cf5d4-110">이 네임 스페이스는 모든 사용할 캐싱은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-110">This namespace makes caching is available to all [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="cf5d4-111">이전 버전의 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서는 캐싱을 <xref:System.Web> 네임스페이스에서만 사용할 수 있었기 때문에 ASP.NET 클래스에 대한 종속성이 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-111">In previous versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>  
  
 <span data-ttu-id="cf5d4-112">이 연습에서 사용할 수 있는 캐싱 기능을 사용 하는 방법을 보여 줍니다.는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 의 일부로 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-112">This walkthrough shows you how to use the caching functionality that is available in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="cf5d4-113">이 연습에서는 텍스트 파일의 내용을 캐시합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-113">In the walkthrough, you cache the contents of a text file.</span></span>  
  
 <span data-ttu-id="cf5d4-114">이 연습에서 수행할 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-114">Tasks illustrated in this walkthrough include the following:</span></span>  
  
-   <span data-ttu-id="cf5d4-115">WPF 응용 프로그램 프로젝트를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-115">Creating a WPF application project.</span></span>  
  
-   <span data-ttu-id="cf5d4-116">에 대 한 참조 추가 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-116">Adding a reference to the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
-   <span data-ttu-id="cf5d4-117">캐시를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-117">Initializing a cache.</span></span>  
  
-   <span data-ttu-id="cf5d4-118">텍스트 파일의 내용을 포함 하는 캐시 엔트리를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-118">Adding a cache entry that contains the contents of a text file.</span></span>  
  
-   <span data-ttu-id="cf5d4-119">한 제거 정책 캐시 항목에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-119">Providing an eviction policy for the cache entry.</span></span>  
  
-   <span data-ttu-id="cf5d4-120">캐시 된 파일의 경로 모니터링 하 고 캐시 인스턴스에 대 한 알리기 모니터링된 항목을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cf5d4-121">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="cf5d4-121">Prerequisites</span></span>  
 <span data-ttu-id="cf5d4-122">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-122">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="cf5d4-123">Microsoft [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf5d4-123">Microsoft [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].</span></span>  
  
-   <span data-ttu-id="cf5d4-124">적은 양의 텍스트를 포함 하는 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="cf5d4-125">(메시지 상자에 텍스트 파일의 내용을 표시 합니다.) 이 연습에 제공 된 코드를 사용 하는 다음 파일을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>  
  
     `c:\cache\cacheText.txt`  
  
     <span data-ttu-id="cf5d4-126">그러나 모든 텍스트 파일을 사용할 수 있으며이 연습에서 코드를 약간 변경.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>  
  
## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="cf5d4-127">WPF 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="cf5d4-127">Creating a WPF Application Project</span></span>  
 <span data-ttu-id="cf5d4-128">WPF 응용 프로그램 프로젝트를 만들어 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-128">You will start by creating a WPF application project.</span></span>  
  
#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="cf5d4-129">WPF 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="cf5d4-129">To create a WPF application</span></span>  
  
1.  <span data-ttu-id="cf5d4-130">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-130">Start [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
2.  <span data-ttu-id="cf5d4-131">에 **파일** 메뉴를 클릭 **새로**, 클릭 하 고 **새 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>  
  
     <span data-ttu-id="cf5d4-132">**새 프로젝트** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-132">The **New Project** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="cf5d4-133">아래 **설치 된 템플릿**, 사용 하려는 프로그래밍 언어를 선택 (**Visual Basic** 또는 **Visual C#**).</span><span class="sxs-lookup"><span data-stu-id="cf5d4-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>  
  
4.  <span data-ttu-id="cf5d4-134">에 **새 프로젝트** 대화 상자에서 **WPF 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-134">In the **New Project** dialog box, select **WPF Application**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cf5d4-135">표시 되지 않으면는 **WPF 응용 프로그램** 서식 파일의 버전을 대상으로 하 고 있는지 확인은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] WPF를 지 원하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] that supports WPF.</span></span> <span data-ttu-id="cf5d4-136">에 **새 프로젝트** 대화 상자에서 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 목록에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-136">In the **New Project** dialog box, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] from the list.</span></span>  
  
5.  <span data-ttu-id="cf5d4-137">에 **이름** 텍스트 상자에 프로젝트의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="cf5d4-138">예를 들어 입력할 수 있습니다 **WPFCaching**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-138">For example, you can enter **WPFCaching**.</span></span>  
  
6.  <span data-ttu-id="cf5d4-139">선택 된 **솔루션용 디렉터리 만들기** 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-139">Select the **Create directory for solution** check box.</span></span>  
  
7.  <span data-ttu-id="cf5d4-140">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-140">Click **OK**.</span></span>  
  
     <span data-ttu-id="cf5d4-141">WPF 디자이너에서 엽니다 **디자인** 본 MainWindow.xaml 파일을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]<span data-ttu-id="cf5d4-142">만듭니다는 **My Project** 폴더, Application.xaml 파일 및 MainWindow.xaml 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-142"> creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>  
  
## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="cf5d4-143">.NET Framework를 대상으로 하 고 캐싱 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>  
 <span data-ttu-id="cf5d4-144">기본적으로 WPF 응용 프로그램 대상에서 [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-144">By default, WPF applications target the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span></span> <span data-ttu-id="cf5d4-145">사용 하는 <xref:System.Runtime.Caching> WPF 응용 프로그램에서 네임 스페이스를 응용 프로그램 대상으로 해야 합니다는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (하지는 [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) 네임 스페이스에 대 한 참조를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (not the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) and must include a reference to the namespace.</span></span>  
  
 <span data-ttu-id="cf5d4-146">따라서 다음 단계에 대 한 참조를 추가 하 고.NET Framework 대상을 변경 하는 것은 <xref:System.Runtime.Caching> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf5d4-147">.NET Framework 대상 변경에 대 한 절차는 Visual C# 프로젝트 및 Visual Basic 프로젝트에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>  
  
#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="cf5d4-148">Visual Basic에서.NET Framework 대상을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="cf5d4-148">To change the target .NET Framework in Visual Basic</span></span>  
  
1.  <span data-ttu-id="cf5d4-149">**솔루션 탐색기**프로젝트 이름을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="cf5d4-150">응용 프로그램에 대 한 속성 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-150">The properties window for the application is displayed.</span></span>  
  
2.  <span data-ttu-id="cf5d4-151">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-151">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="cf5d4-152">창의 아래쪽 클릭 **고급 컴파일 옵션...** .</span><span class="sxs-lookup"><span data-stu-id="cf5d4-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>  
  
     <span data-ttu-id="cf5d4-153">**고급 컴파일러 설정** 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="cf5d4-154">에 **대상 프레임 워크 (모든 구성)** 목록에서 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-154">In the **Target framework (all configurations)** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="cf5d4-155">(선택 하지 않으면 [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="cf5d4-155">(Do not select [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span></span>  
  
5.  <span data-ttu-id="cf5d4-156">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-156">Click **OK**.</span></span>  
  
     <span data-ttu-id="cf5d4-157">**대상 프레임 워크 변경** 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-157">The **Target Framework Change** dialog box is displayed.</span></span>  
  
6.  <span data-ttu-id="cf5d4-158">에 **대상 프레임 워크 변경** 대화 상자를 클릭 **예**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>  
  
     <span data-ttu-id="cf5d4-159">프로젝트 닫히고 후 다시 열립니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-159">The project is closed and is then reopened.</span></span>  
  
7.  <span data-ttu-id="cf5d4-160">다음 단계를 수행 하 여 캐싱 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-160">Add a reference to the caching assembly by following these steps:</span></span>  
  
    1.  <span data-ttu-id="cf5d4-161">**솔루션 탐색기**프로젝트의 이름을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="cf5d4-162">선택 된 **.NET** 탭을 `System.Runtime.Caching`, 클릭 하 고 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>  
  
#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="cf5d4-163">Visual C# 프로젝트의 대상.NET Framework를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="cf5d4-163">To change the target .NET Framework in a Visual C# project</span></span>  
  
1.  <span data-ttu-id="cf5d4-164">**솔루션 탐색기**프로젝트 이름을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>  
  
     <span data-ttu-id="cf5d4-165">응용 프로그램에 대 한 속성 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-165">The properties window for the application is displayed.</span></span>  
  
2.  <span data-ttu-id="cf5d4-166">**응용 프로그램** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-166">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="cf5d4-167">에 **대상 프레임 워크** 목록에서 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-167">In the **Target framework** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="cf5d4-168">(선택 하지 않으면 **.NET Framework 4 Client Profile**.)</span><span class="sxs-lookup"><span data-stu-id="cf5d4-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>  
  
4.  <span data-ttu-id="cf5d4-169">다음 단계를 수행 하 여 캐싱 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-169">Add a reference to the caching assembly by following these steps:</span></span>  
  
    1.  <span data-ttu-id="cf5d4-170">마우스 오른쪽 단추로 클릭는 **참조** 폴더와 클릭 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-170">Right-click the **References** folder and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="cf5d4-171">선택 된 **.NET** 탭을 `System.Runtime.Caching`, 클릭 하 고 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>  
  
## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="cf5d4-172">WPF 창에 단추 추가</span><span class="sxs-lookup"><span data-stu-id="cf5d4-172">Adding a Button to the WPF Window</span></span>  
 <span data-ttu-id="cf5d4-173">다음으로 button 컨트롤을 추가 하 고 단추의 대 한 이벤트 처리기를 만들고 `Click` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="cf5d4-174">나중에 텍스트 파일의 내용을 캐시 되어 표시 단추를 클릭할 때 되므로 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>  
  
#### <a name="to-add-a-button-control"></a><span data-ttu-id="cf5d4-175">단추 컨트롤을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="cf5d4-175">To add a button control</span></span>  
  
1.  <span data-ttu-id="cf5d4-176">**솔루션 탐색기**를 열려는 MainWindow.xaml 파일을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>  
  
2.  <span data-ttu-id="cf5d4-177">**도구 상자**아래에서 **공용 WPF 컨트롤**를 끌어 한 `Button` 컨트롤을 `MainWindow` 창.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>  
  
3.  <span data-ttu-id="cf5d4-178">에 **속성** 창의 설정는 `Content` 속성은 `Button` 컨트롤을 **캐시 가져오기**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>  
  
## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="cf5d4-179">캐시를 초기화 하 고 엔트리 캐싱</span><span class="sxs-lookup"><span data-stu-id="cf5d4-179">Initializing the Cache and Caching an Entry</span></span>  
 <span data-ttu-id="cf5d4-180">다음으로, 다음 작업을 수행 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-180">Next, you will add the code to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="cf5d4-181">캐시 클래스의 인스턴스를 만들고-즉, 인스턴스화 새 <xref:System.Runtime.Caching.MemoryCache> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>  
  
-   <span data-ttu-id="cf5d4-182">캐시에서 사용 하도록 지정할는 <xref:System.Runtime.Caching.HostFileChangeMonitor> 텍스트 파일에 변경 사항을 모니터링 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>  
  
-   <span data-ttu-id="cf5d4-183">텍스트 파일을 읽고 캐시 엔트리로 해당 콘텐츠를 캐시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-183">Read the text file and cache its contents as a cache entry.</span></span>  
  
-   <span data-ttu-id="cf5d4-184">캐시 된 텍스트 파일의 내용을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-184">Display the contents of the cached text file.</span></span>  
  
#### <a name="to-create-the-cache-object"></a><span data-ttu-id="cf5d4-185">캐시 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="cf5d4-185">To create the cache object</span></span>  
  
1.  <span data-ttu-id="cf5d4-186">MainWindow.Xaml.vb 또는 MainWindow.xaml.cs 파일에 이벤트 처리기를 만들기 위해 방금 추가한 단추를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>  
  
2.  <span data-ttu-id="cf5d4-187">클래스 선언) (이전 파일 맨 위에 있는 다음 추가 `Imports` (Visual Basic) 또는 `using` (C#) 문을:</span><span class="sxs-lookup"><span data-stu-id="cf5d4-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>  
  
    ```csharp  
    using System.Runtime.Caching;  
    using System.IO;  
    ```  
  
    ```vb  
    Imports System.Runtime.Caching  
    Imports System.IO  
    ```  
  
3.  <span data-ttu-id="cf5d4-188">이벤트 처리기에서 캐시 개체를 인스턴스화하는 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-188">In the event handler, add the following code to instantiate the cache object:</span></span>  
  
    ```csharp  
    ObjectCache cache = MemoryCache.Default;  
    ```  
  
    ```vb  
    Dim cache As ObjectCache = MemoryCache.Default  
    ```  
  
     <span data-ttu-id="cf5d4-189"><xref:System.Runtime.Caching.ObjectCache> 클래스는 메모리 내 개체 캐시를 제공 하는 기본 제공 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>  
  
4.  <span data-ttu-id="cf5d4-190">명명 된 캐시 항목의 내용을 다음 코드를 추가 `filecontents`:</span><span class="sxs-lookup"><span data-stu-id="cf5d4-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>  
  
    ```vb  
    Dim fileContents As String = TryCast(cache("filecontents"), String)  
    ```  
  
    ```csharp  
    string fileContents = cache["filecontents"] as string;  
    ```  
  
5.  <span data-ttu-id="cf5d4-191">라는 캐시 엔트리가 있는지 여부를 확인 하려면 다음 코드를 추가 `filecontents` 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>  
  
    ```vb  
    If fileContents Is Nothing Then  
  
    End If  
    ```  
  
    ```csharp  
    if (fileContents == null)  
    {  
  
    }  
    ```  
  
     <span data-ttu-id="cf5d4-192">지정된 된 캐시 엔트리가 없는 경우 텍스트 파일 읽고 캐시에 캐시 항목으로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>  
  
6.  <span data-ttu-id="cf5d4-193">에 `if/then` 블록을 새로 만들려면 다음 코드를 추가 <xref:System.Runtime.Caching.CacheItemPolicy> 10 초 후에 캐시 엔트리가 만료 되도록 지정 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>  
  
    ```vb  
    Dim policy As New CacheItemPolicy()  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)  
    ```  
  
    ```csharp  
    CacheItemPolicy policy = new CacheItemPolicy();  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);  
    ```  
  
     <span data-ttu-id="cf5d4-194">제공 된 제거 또는 만료 정보가 없는 경우 기본값은 <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, 절대 시간에 대해서만 기준으로 만료 되지 않도록 캐시 항목을 의미 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="cf5d4-195">대신 캐시 항목 만료는 메모리 압박이 있는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="cf5d4-196">모범 사례로, 절대 또는 상대 (siding) 만료 항상 명시적으로 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-196">As a best practice, you should always explicitly provide either an absolute or a siding expiration.</span></span>  
  
7.  <span data-ttu-id="cf5d4-197">내에서 `if/then` 차단 하 고 다음 이전 단계에서 추가한 코드를 모니터링 하 고 컬렉션에 텍스트 파일의 경로 추가 하려면 원하는 파일 경로 대 한 컬렉션을 만들려면 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>  
  
    ```vb  
    Dim filePaths As New List(Of String)()  
    filePaths.Add("c:\cache\cacheText.txt")  
    ```  
  
    ```csharp  
    List<string> filePaths = new List<string>();  
    filePaths.Add("c:\\cache\\cacheText.txt");  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="cf5d4-198">사용 하려는 텍스트 파일 없으면 `c:\cache\cacheText.txt`, 텍스트 파일을 사용 하려면 하는 있는 경로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>  
  
8.  <span data-ttu-id="cf5d4-199">다음 코드를 새 추가 추가 이전 단계에서 추가한 코드 뒤 <xref:System.Runtime.Caching.HostFileChangeMonitor> 캐시 항목에 대 한 변경의 컬렉션 개체를 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>  
  
    ```vb  
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))  
    ```  
  
    ```csharp  
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));  
    ```  
  
     <span data-ttu-id="cf5d4-200"><xref:System.Runtime.Caching.HostFileChangeMonitor> 개체는 텍스트 파일의 경로 모니터링 하 고 변경 될 경우에 캐시를에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="cf5d4-201">이 예제에서는 캐시 항목에는 파일의 내용이 변경 되 면 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-201">In this example, the cache entry will expire if the content of the file changes.</span></span>  
  
9. <span data-ttu-id="cf5d4-202">다음 이전 단계에서 추가한 코드를 텍스트 파일의 내용을 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>  
  
    ```vb  
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()  
    ```  
  
    ```csharp  
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + + "\n" + DateTime.Now;   
    ```  
  
     <span data-ttu-id="cf5d4-203">캐시 엔트리가 만료 될 때 표시 될 수 있도록 날짜 및 시간 타임 스탬프가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>  
  
10. <span data-ttu-id="cf5d4-204">파일의 내용을으로 캐시 개체에 삽입 하려면 다음 코드를 추가 이전 단계에서 추가한 코드 뒤에 <xref:System.Runtime.Caching.CacheItem> 인스턴스:</span><span class="sxs-lookup"><span data-stu-id="cf5d4-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>  
  
    ```vb  
    cache.Set("filecontents", fileContents, policy)  
    ```  
  
    ```csharp  
    cache.Set("filecontents", fileContents, policy);  
    ```  
  
     <span data-ttu-id="cf5d4-205">전달 하 여 캐시 엔트리를 제거 하는 방법에 대 한 정보를 지정 된 <xref:System.Runtime.Caching.CacheItemPolicy> 매개 변수로 앞에서 만든 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>  
  
11. <span data-ttu-id="cf5d4-206">후의 `if/then` 블록에서 메시지 상자에 캐시 된 파일 내용을 표시 하려면 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>  
  
    ```vb  
    MessageBox.Show(fileContents)  
    ```  
  
    ```csharp  
    MessageBox.Show(fileContents);  
    ```  
  
12. <span data-ttu-id="cf5d4-207">에 **빌드** 메뉴를 클릭 하 여 **WPFCaching 빌드** 프로젝트를 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>  
  
## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="cf5d4-208">WPF 응용 프로그램에서 캐싱 테스트</span><span class="sxs-lookup"><span data-stu-id="cf5d4-208">Testing Caching in the WPF Application</span></span>  
 <span data-ttu-id="cf5d4-209">이제 응용 프로그램을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-209">You can now test the application.</span></span>  
  
#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="cf5d4-210">WPF 응용 프로그램의 캐싱 기능을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="cf5d4-210">To test caching in the WPF application</span></span>  
  
1.  <span data-ttu-id="cf5d4-211">Ctrl+F5를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-211">Press CTRL+F5 to run the application.</span></span>  
  
     <span data-ttu-id="cf5d4-212">`MainWindow` 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-212">The `MainWindow` window is displayed.</span></span>  
  
2.  <span data-ttu-id="cf5d4-213">클릭 **캐시 가져오기**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-213">Click **Get Cache**.</span></span>  
  
     <span data-ttu-id="cf5d4-214">텍스트 파일에서 캐시 된 콘텐츠는 메시지 상자에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="cf5d4-215">파일에 타임 스탬프를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-215">Notice the timestamp on the file.</span></span>  
  
3.  <span data-ttu-id="cf5d4-216">메시지 상자를 닫은 다음 클릭 **캐시 가져오기** 다시**합니다.**</span><span class="sxs-lookup"><span data-stu-id="cf5d4-216">Close the message box and then click **Get Cache** again**.**</span></span>  
  
     <span data-ttu-id="cf5d4-217">타임 스탬프가 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-217">The timestamp is unchanged.</span></span> <span data-ttu-id="cf5d4-218">이 캐시 된 내용을 표시 하는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-218">This indicates the cached content is displayed.</span></span>  
  
4.  <span data-ttu-id="cf5d4-219">10 초 이상 기다린 후 클릭 **캐시 가져오기** 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>  
  
     <span data-ttu-id="cf5d4-220">이 시간에 새로운 타임 스탬프가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="cf5d4-221">이 캐시 항목 만료 하도록 정책을 설정 하 고 새 캐시 된 콘텐츠 표시 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>  
  
5.  <span data-ttu-id="cf5d4-222">텍스트 편집기에서 만든 텍스트 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="cf5d4-223">변경 내용을 아직 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-223">Do not make any changes yet.</span></span>  
  
6.  <span data-ttu-id="cf5d4-224">메시지 상자를 닫은 다음 클릭 **캐시 가져오기** 다시**합니다.**</span><span class="sxs-lookup"><span data-stu-id="cf5d4-224">Close the message box and then click **Get Cache** again**.**</span></span>  
  
     <span data-ttu-id="cf5d4-225">타임 스탬프를 다시 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-225">Notice the timestamp again.</span></span>  
  
7.  <span data-ttu-id="cf5d4-226">텍스트 파일을 변경 하 고 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-226">Make a change to the text file and then save the file.</span></span>  
  
8.  <span data-ttu-id="cf5d4-227">메시지 상자를 닫은 다음 클릭 **캐시 가져오기** 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-227">Close the message box and then click **Get Cache** again.</span></span>  
  
     <span data-ttu-id="cf5d4-228">이 메시지 상자 텍스트 파일 및 새 타임 스탬프에서 업데이트 된 콘텐츠를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="cf5d4-229">이 제거 했음을 나타냅니다 호스트 파일 변경 모니터 캐시 항목 파일을 변경한 경우 즉시 절대 제한 시간이 만료 되지 않은 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cf5d4-230">제거 시간 20 초 이상으로 파일에서 변경할 수 있습니다 더 많은 시간을 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>  
  
## <a name="code-example"></a><span data-ttu-id="cf5d4-231">코드 예제</span><span class="sxs-lookup"><span data-stu-id="cf5d4-231">Code Example</span></span>  
 <span data-ttu-id="cf5d4-232">이 연습을 완료 한 후 다음 예제를 만든 프로젝트에 대 한 코드와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5d4-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>  
  
 [!code-csharp[CachingWPFApplications#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cf5d4-233">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf5d4-233">See Also</span></span>  
 <xref:System.Runtime.Caching.MemoryCache>  
 <xref:System.Runtime.Caching.ObjectCache>  
 <xref:System.Runtime.Caching>  
 [<span data-ttu-id="cf5d4-234">.NET Framework 응용 프로그램에서 캐시</span><span class="sxs-lookup"><span data-stu-id="cf5d4-234">Caching in .NET Framework Applications</span></span>](../../../../docs/framework/performance/caching-in-net-framework-applications.md)
