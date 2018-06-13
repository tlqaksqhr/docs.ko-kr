---
title: '연습: 혼합 응용 프로그램 지역화'
ms.date: 03/30/2017
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 010c8f75a1151f5606be5ffa63d60fca364bdb59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549174"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="9954c-102">연습: 혼합 응용 프로그램 지역화</span><span class="sxs-lookup"><span data-stu-id="9954c-102">Walkthrough: Localizing a Hybrid Application</span></span>
<span data-ttu-id="9954c-103">이 연습에서는 지역화 하는 방법을 보여 줍니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 의 요소는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-하이브리드 응용 프로그램을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-based hybrid application.</span></span>  
  
 <span data-ttu-id="9954c-104">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="9954c-105">만들기는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 호스트 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="9954c-105">Creating the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] host project.</span></span>  
  
-   <span data-ttu-id="9954c-106">지역화 가능한 콘텐츠 추가.</span><span class="sxs-lookup"><span data-stu-id="9954c-106">Adding localizable content.</span></span>  
  
-   <span data-ttu-id="9954c-107">지역화 사용.</span><span class="sxs-lookup"><span data-stu-id="9954c-107">Enabling localization.</span></span>  
  
-   <span data-ttu-id="9954c-108">리소스 식별자 할당.</span><span class="sxs-lookup"><span data-stu-id="9954c-108">Assigning resource identifiers.</span></span>  
  
-   <span data-ttu-id="9954c-109">LocBaml 도구를 사용하여 위성 어셈블리 생성.</span><span class="sxs-lookup"><span data-stu-id="9954c-109">Using the LocBaml tool to produce a satellite assembly.</span></span>  
  
 <span data-ttu-id="9954c-110">이 연습에서 설명 하는 작업의 전체 코드 목록을 보려면 [하이브리드 응용 프로그램 샘플 지역화](http://go.microsoft.com/fwlink/?LinkID=160015)합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](http://go.microsoft.com/fwlink/?LinkID=160015).</span></span>  
  
 <span data-ttu-id="9954c-111">위의 작업을 완료하면 지역화된 하이브리드 응용 프로그램이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-111">When you are finished, you will have a localized hybrid application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9954c-112">전제 조건</span><span class="sxs-lookup"><span data-stu-id="9954c-112">Prerequisites</span></span>  
 <span data-ttu-id="9954c-113">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-113">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="9954c-114">.</span><span class="sxs-lookup"><span data-stu-id="9954c-114">.</span></span>  
  
## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="9954c-115">Windows Forms 호스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="9954c-115">Creating the Windows Forms Host Project</span></span>  
 <span data-ttu-id="9954c-116">첫 번째 단계를 만드는 것은 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 응용 프로그램 프로젝트 및 추가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 지역화 됩니다 하는 콘텐츠가 있는 요소의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-116">The first step is to create the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>  
  
#### <a name="to-create-the-host-project"></a><span data-ttu-id="9954c-117">호스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="9954c-117">To create the host project</span></span>  
  
1.  <span data-ttu-id="9954c-118">이라는 WPF 응용 프로그램 프로젝트 만들기 `LocalizingWpfInWf`합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-118">Create a WPF Application project named `LocalizingWpfInWf`.</span></span> <span data-ttu-id="9954c-119">자세한 내용은 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9954c-119">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="9954c-120">추가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> 라는 이름의 요소 `SimpleControl` 프로젝트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>  
  
3.  <span data-ttu-id="9954c-121">사용 하 여는 <xref:System.Windows.Forms.Integration.ElementHost> 배치할은 `SimpleControl` 요소를 폼에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="9954c-122">자세한 내용은 참조 [연습: Windows Forms에서 WPF 3 차원 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-122">For more information, see [Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>  
  
## <a name="adding-localizable-content"></a><span data-ttu-id="9954c-123">지역화 가능한 콘텐츠 추가</span><span class="sxs-lookup"><span data-stu-id="9954c-123">Adding Localizable Content</span></span>  
 <span data-ttu-id="9954c-124">추가한 다음으로 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 레이블 지정 및 설정는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 지역화 가능한 문자열 요소의 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-124">Next, you will add a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>  
  
#### <a name="to-add-localizable-content"></a><span data-ttu-id="9954c-125">지역화 가능한 콘텐츠를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="9954c-125">To add localizable content</span></span>  
  
1.  <span data-ttu-id="9954c-126">솔루션 탐색기에서 두 번 클릭 **SimpleControl.xaml** 에서 열려는 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-126">In Solution Explorer, double-click **SimpleControl.xaml** to open it in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
2.  <span data-ttu-id="9954c-127">설정의 콘텐츠는 <xref:System.Windows.Controls.Button> 다음 코드를 사용 하 여 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>  
  
     [!code-xaml[LocalizingWpfInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]  
  
3.  <span data-ttu-id="9954c-128">솔루션 탐색기에서 두 번 클릭 **Form1** Windows Forms 디자이너에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-128">In Solution Explorer, double-click **Form1** to open it in the Windows Forms Designer.</span></span>  
  
4.  <span data-ttu-id="9954c-129">도구 상자를 열고 두 번 클릭 **레이블** 를 양식에 레이블 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-129">Open the Toolbox and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="9954c-130"><xref:System.Windows.Forms.Control.Text%2A> 속성의 값을 `"Hello"`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>  
  
5.  <span data-ttu-id="9954c-131">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-131">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="9954c-132">두는 `SimpleControl` 요소와 레이블 컨트롤에 텍스트 표시 **"Hello"** 합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>  
  
## <a name="enabling-localization"></a><span data-ttu-id="9954c-133">지역화 사용</span><span class="sxs-lookup"><span data-stu-id="9954c-133">Enabling Localization</span></span>  
 <span data-ttu-id="9954c-134">Windows Forms 디자이너에서는 위성 어셈블리에서 지역화를 사용하도록 설정하기 위한 설정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>  
  
#### <a name="to-enable-localization"></a><span data-ttu-id="9954c-135">지역화를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="9954c-135">To enable localization</span></span>  
  
1.  <span data-ttu-id="9954c-136">솔루션 탐색기에서 두 번 클릭 **Form1.cs** Windows Forms 디자이너에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-136">In Solution Explorer, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="9954c-137">속성 창에서 폼의 값을 설정 **Localizable** 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-137">In the Properties window, set the value of the form's **Localizable** property to `true`.</span></span>  
  
3.  <span data-ttu-id="9954c-138">속성 창에서 설정의 값은 **언어** 속성을 **스페인어 (스페인)** 합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-138">In the Properties window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>  
  
4.  <span data-ttu-id="9954c-139">Windows Forms 디자이너에서 레이블 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-139">In the Windows Forms Designer, select the label control.</span></span>  
  
5.  <span data-ttu-id="9954c-140">속성 창에서 설정의 값은 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `"Hola"`합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-140">In the Properties window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>  
  
     <span data-ttu-id="9954c-141">Form1.es-ES.resx라는 새 리소스 파일이 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>  
  
6.  <span data-ttu-id="9954c-142">솔루션 탐색기에서 마우스 오른쪽 단추로 클릭 **Form1.cs** 클릭 **코드 보기** 코드 편집기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-142">In Solution Explorer, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>  
  
7.  <span data-ttu-id="9954c-143">다음 코드를 복사는 `Form1` 생성자를 호출 하기 `InitializeComponent`합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>  
  
     [!code-csharp[LocalizingWpfInWf#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]  
  
8.  <span data-ttu-id="9954c-144">솔루션 탐색기에서 마우스 오른쪽 단추로 클릭 **LocalizingWpfInWf** 클릭 **프로젝트 언로드**합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-144">In Solution Explorer, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>  
  
     <span data-ttu-id="9954c-145">프로젝트 이름 레이블이 **(사용 불가)** 합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-145">The project name is labeled **(unavailable)**.</span></span>  
  
9. <span data-ttu-id="9954c-146">마우스 오른쪽 단추로 클릭 **LocalizingWpfInWf**를 클릭 하 고 **편집 LocalizingWpfInWf.csproj**합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>  
  
     <span data-ttu-id="9954c-147">프로젝트 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-147">The project file opens in the Code Editor.</span></span>  
  
10. <span data-ttu-id="9954c-148">다음 줄을 첫 번째 복사 `PropertyGroup` 프로젝트 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>  
  
    ```xml  
    <UICulture>en-US</UICulture>   
    ```  
  
11. <span data-ttu-id="9954c-149">프로젝트 파일을 저장하고 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-149">Save the project file and close it.</span></span>  
  
12. <span data-ttu-id="9954c-150">솔루션 탐색기에서 마우스 오른쪽 단추로 클릭 **LocalizingWpfInWf** 클릭 **프로젝트 다시 로드**합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-150">In Solution Explorer, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>  
  
## <a name="assigning-resource-identifiers"></a><span data-ttu-id="9954c-151">리소스 식별자 할당</span><span class="sxs-lookup"><span data-stu-id="9954c-151">Assigning Resource Identifiers</span></span>  
 <span data-ttu-id="9954c-152">리소스 식별자를 사용하여 리소스 어셈블리에 지역화 가능한 콘텐츠를 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="9954c-153">지정 하는 경우 MsBuild.exe 응용 프로그램 리소스 식별자를 자동으로 할당 된 `updateuid` 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>  
  
#### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="9954c-154">리소스 식별자를 할당하려면</span><span class="sxs-lookup"><span data-stu-id="9954c-154">To assign resource identifiers</span></span>  
  
1.  <span data-ttu-id="9954c-155">시작 메뉴에서 Visual Studio 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-155">From the Start Menu, open the Visual Studio Command Prompt.</span></span>  
  
2.  <span data-ttu-id="9954c-156">다음 명령을 사용하여 지역화 가능한 콘텐츠에 리소스 식별자를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-156">Use the following command to assign resource identifiers to your localizable content.</span></span>  
  
    ```  
    msbuild /t:updateuid LocalizingWpfInWf.csproj  
    ```  
  
3.  <span data-ttu-id="9954c-157">솔루션 탐색기에서 두 번 클릭 **SimpleControl.xaml** 코드 편집기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-157">In Solution Explorer, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="9954c-158">가 표시 됩니다는 `msbuild` 명령에 추가 `Uid` 모든 요소에 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="9954c-159">따라서 리소스 식별자 할당을 통해 지역화가 용이해집니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-159">This facilitates localization through the assignment of resource identifiers.</span></span>  
  
     [!code-xaml[LocalizingWpfInWf#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]  
  
4.  <span data-ttu-id="9954c-160">F6 키를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-160">Press F6 to build the solution.</span></span>  
  
## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="9954c-161">LocBaml을 사용하여 위성 어셈블리 생성</span><span class="sxs-lookup"><span data-stu-id="9954c-161">Using LocBaml to Produce a Satellite Assembly</span></span>  
 <span data-ttu-id="9954c-162">리소스 전용에 지역화 된 콘텐츠 저장 됩니다 *위성 어셈블리*합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="9954c-163">에 대 한 지역화 된 어셈블리를 생성 하기 LocBaml.exe 명령줄 도구를 사용 하 여 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>  
  
#### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="9954c-164">위성 어셈블리를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="9954c-164">To produce a satellite assembly</span></span>  
  
1.  <span data-ttu-id="9954c-165">LocBaml.exe를 프로젝트의 obj\Debug 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="9954c-166">자세한 내용은 참조 [응용 프로그램 지역화](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-166">For more information, see [Localize an Application](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).</span></span>  
  
2.  <span data-ttu-id="9954c-167">[명령 프롬프트] 창에서 다음 명령을 사용하여 리소스 문자열을 임시 파일로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>  
  
    ```  
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv  
    ```  
  
3.  <span data-ttu-id="9954c-168">Visual Studio 또는 다른 텍스트 편집기와 함께 사용 하 여 temp.csv 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="9954c-169">문자열 `"Hello"` 해당 스페인어 번역 된 `"Hola"`합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>  
  
4.  <span data-ttu-id="9954c-170">temp.csv 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-170">Save the temp.csv file.</span></span>  
  
5.  <span data-ttu-id="9954c-171">다음 명령을 사용하여 지역화된 리소스 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-171">Use the following command to generate the localized resource file.</span></span>  
  
    ```  
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES  
    ```  
  
     <span data-ttu-id="9954c-172">LocalizingWpfInWf.g.es-ES.resources 파일이 obj\Debug 폴더에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>  
  
6.  <span data-ttu-id="9954c-173">다음 명령을 사용하여 지역화된 위성 어셈블리를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-173">Use the following command to build the localized satellite assembly.</span></span>  
  
    ```  
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources  
    ```  
  
     <span data-ttu-id="9954c-174">LocalizingWpfInWf.resources.dll 파일이 obj\Debug 폴더에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>  
  
7.  <span data-ttu-id="9954c-175">LocalizingWpfInWf.resources.dll 파일을 프로젝트의 bin\Debug\es-ES 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="9954c-176">기존 파일을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-176">Replace the existing file.</span></span>  
  
8.  <span data-ttu-id="9954c-177">프로젝트의 bin\Debug 폴더에 있는 LocalizingWpfInWf.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="9954c-178">응용 프로그램을 다시 빌드하지 마세요. 다시 빌드하면 위성 어셈블리가 덮어 쓰입니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>  
  
     <span data-ttu-id="9954c-179">응용 프로그램에서 영어 문자열 대신 지역화된 문자열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9954c-179">The application shows the localized strings instead of the English strings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9954c-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9954c-180">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="9954c-181">응용 프로그램 지역화</span><span class="sxs-lookup"><span data-stu-id="9954c-181">Localize an Application</span></span>](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)  
 [<span data-ttu-id="9954c-182">연습: Windows Forms 지역화</span><span class="sxs-lookup"><span data-stu-id="9954c-182">Walkthrough: Localizing Windows Forms</span></span>](http://msdn.microsoft.com/library/9a96220d-a19b-4de0-9f48-01e5d82679e5)  
 [<span data-ttu-id="9954c-183">WPF 디자이너</span><span class="sxs-lookup"><span data-stu-id="9954c-183">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
