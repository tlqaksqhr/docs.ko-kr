---
title: "연습: Win32에서 WPF 시계 호스팅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: caf652f8a80da8e927a74ffc012d09b2389b1b09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="92893-102">연습: Win32에서 WPF 시계 호스팅</span><span class="sxs-lookup"><span data-stu-id="92893-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>
<span data-ttu-id="92893-103">넣을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 내 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 응용 프로그램을 사용 하 여 <xref:System.Windows.Interop.HwndSource>를 포함 하는 HWND를 제공 하는 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="92893-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="92893-104">먼저 만듭니다는 <xref:System.Windows.Interop.HwndSource>, CreateWindow 유사한 매개 변수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span>  <span data-ttu-id="92893-105">그런는 <xref:System.Windows.Interop.HwndSource> 에 대 한는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 내부 원하는 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="92893-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span>  <span data-ttu-id="92893-106">HWND를 얻게 마지막으로 <xref:System.Windows.Interop.HwndSource>합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="92893-107">이 연습에는 혼합 만드는 방법을 보여 주는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 내 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 운영 체제 상자 응용 프로그램 **날짜 및 시간 속성** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="92893-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="92893-108">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="92893-108">Prerequisites</span></span>  
 <span data-ttu-id="92893-109">참조 [WPF 및 Win32 상호 운용](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-109">See [WPF and Win32 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).</span></span>  
  
## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="92893-110">이 자습서를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="92893-110">How to Use This Tutorial</span></span>  
 <span data-ttu-id="92893-111">이 자습서는 상호 운용 응용 프로그램을 생성하는 중요한 단계에 대해 중점적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="92893-112">이 자습서는 샘플을 뒷받침 되며 [Win32 클록의 상호 운용 샘플](http://go.microsoft.com/fwlink/?LinkID=160051)했지만 해당 샘플은 최종 제품의 반사입니다.</span><span class="sxs-lookup"><span data-stu-id="92893-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="92893-113">시작 하 여 기존 하는 경우이 자습서의 단계에 설명 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 자신만의 프로젝트 및 아마도 기존 프로젝트를 추가 하는 호스팅된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92893-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="92893-114">포함 된 최종 제품을 비교할 수 [Win32 클록의 상호 운용 샘플](http://go.microsoft.com/fwlink/?LinkID=160051)합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-114">You can compare your end product with [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051).</span></span>  
  
## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="92893-115">Win32 내에서 Windows Presentation Framework의 연습(HwndSource)</span><span class="sxs-lookup"><span data-stu-id="92893-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>  
 <span data-ttu-id="92893-116">다음 그래픽에서는 이 자습서의 의도된 최종 제품을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92893-116">The following graphic shows the intended end product of this tutorial:</span></span>  
  
 <span data-ttu-id="92893-117">![날짜 및 시간 속성 대화 상자](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")</span><span class="sxs-lookup"><span data-stu-id="92893-117">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")</span></span>  
  
 <span data-ttu-id="92893-118">C + +를 만들어서이 대화 상자를 다시 만들 수 있습니다 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로젝트에서 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], 대화 상자 편집기를 사용 하 여 다음을 만들려고 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92893-118">You can recreate this dialog by creating C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], and using the dialog editor to create the following:</span></span>  
  
 <span data-ttu-id="92893-119">![날짜 및 시간 속성 대화 상자](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")</span><span class="sxs-lookup"><span data-stu-id="92893-119">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")</span></span>  
  
 <span data-ttu-id="92893-120">(사용할 필요가 없습니다 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 사용할 <xref:System.Windows.Interop.HwndSource>, c + +를 사용 하 여 쓸 필요가 없습니다 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로그램을 검사 하지만이 수행 하는 일반적인 방식 이며 자습서의 단계별 설명에 적합).</span><span class="sxs-lookup"><span data-stu-id="92893-120">(You do not need to use [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>  
  
 <span data-ttu-id="92893-121">배치 하기 위해 5 개의 특정 하위 단계를 수행 해야 할는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록 대화 상자에:</span><span class="sxs-lookup"><span data-stu-id="92893-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>  
  
1.  <span data-ttu-id="92893-122">사용 하도록 설정 하면 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 관리 되는 코드를 호출 하는 프로젝트 (**/clr**)에서 프로젝트 설정을 변경 하 여 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span></span>  
  
2.  <span data-ttu-id="92893-123">만들기는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> 별도 dll에서입니다.</span><span class="sxs-lookup"><span data-stu-id="92893-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>  
  
3.  <span data-ttu-id="92893-124">넣습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> 내는 <xref:System.Windows.Interop.HwndSource>합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>  
  
4.  <span data-ttu-id="92893-125">HWND는에 대 한 가져오기 <xref:System.Windows.Controls.Page> 를 사용 하는 <xref:System.Windows.Interop.HwndSource.Handle%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="92893-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>  
  
5.  <span data-ttu-id="92893-126">사용 하 여 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 내 더 큰 숫자에서 HWND를 배치할 위치를 결정할 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="92893-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>  
  
## <a name="clr"></a><span data-ttu-id="92893-127">/clr</span><span class="sxs-lookup"><span data-stu-id="92893-127">/clr</span></span>  
 <span data-ttu-id="92893-128">이 관리 되지 않는 첫 번째 단계는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로젝트를 호출할 수 있는 관리 되는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="92893-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span>  <span data-ttu-id="92893-129">/Clr 컴파일러 옵션을 사용 하 고 Main 메서드를 사용 하기 위해 조정 하려는 필요한 Dll을 연결할을 사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="92893-130">C + + 프로젝트 내에서 관리 코드를 사용 하도록 설정 하려면: win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span>  <span data-ttu-id="92893-131">에 **일반** 속성 페이지 (기본값) 이면 변경 하려면 공용 언어 런타임 지원 `/clr`합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>  
  
 <span data-ttu-id="92893-132">다음으로 데 필요한 Dll에 대 한 참조를 추가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll 및 UIAutomationTypes.dll 합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="92893-133">다음 지침에서는 운영 체제가 C: 드라이브에 설치되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>  
  
1.  <span data-ttu-id="92893-134">Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **참조 중...** , 및 대화 상자 내부:</span><span class="sxs-lookup"><span data-stu-id="92893-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>  
  
2.  <span data-ttu-id="92893-135">Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **참조 중...** .</span><span class="sxs-lookup"><span data-stu-id="92893-135">Right-click win32clock project and select **References...**.</span></span>  
  
3.  <span data-ttu-id="92893-136">클릭 **새 참조 추가**찾아보기 탭을 클릭, C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll 입력 및 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>  
  
4.  <span data-ttu-id="92893-137">PresentationFramework.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll)에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>  
  
5.  <span data-ttu-id="92893-138">WindowsBase.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll)에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>  
  
6.  <span data-ttu-id="92893-139">UIAutomationTypes.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll)에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>  
  
7.  <span data-ttu-id="92893-140">UIAutomationProvider.dll(C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll)에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>  
  
8.  <span data-ttu-id="92893-141">클릭 **새 참조 추가**, System.dll을 선택 하 고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>  
  
9. <span data-ttu-id="92893-142">클릭 **확인** 참조를 추가 하기 위한 win32clock 속성 페이지를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>  
  
 <span data-ttu-id="92893-143">마지막으로 추가 된 `STAThreadAttribute` 에 `_tWinMain` 을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="92893-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 <span data-ttu-id="92893-144">이 특성은 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 하을 초기화할 때 [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], 하는데 필요한 단일 스레드 아파트 모델 (STA)를 사용 해야 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="92893-144">This attribute tells the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] that when it initializes [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>  
  
## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="92893-145">Windows Presentation Framework 페이지 만들기</span><span class="sxs-lookup"><span data-stu-id="92893-145">Create a Windows Presentation Framework Page</span></span>  
 <span data-ttu-id="92893-146">다음으로 정의 하는 DLL을 만듭니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="92893-147">만드는 가장 쉬운 방식은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> 독립 실행형 응용 프로그램 및 쓰기 및 디버그로는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이렇게 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="92893-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span>  <span data-ttu-id="92893-148">클릭 하 고 프로젝트를 마우스 오른쪽 단추로 클릭 함으로써 DLL로 해당 프로젝트를 변환할 수 완료 되 면 **속성**는 응용 프로그램으로 이동 하 고 출력 형식을 Windows 클래스 라이브러리로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>  
  
 <span data-ttu-id="92893-149">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll 프로젝트와 결합할 수 있습니다는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 선택 솔루션을 마우스 오른쪽 단추로 클릭 (하나의 솔루션에 두 개의 프로젝트가 포함 된) – 프로젝트 **Add\Existing 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>  
  
 <span data-ttu-id="92893-150">해당 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서 dll의 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 에 대 한 참조를 추가 해야 프로젝트를:</span><span class="sxs-lookup"><span data-stu-id="92893-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>  
  
1.  <span data-ttu-id="92893-151">Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **참조 중...** .</span><span class="sxs-lookup"><span data-stu-id="92893-151">Right-click win32clock project and select **References...**.</span></span>  
  
2.  <span data-ttu-id="92893-152">클릭 **새 참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-152">Click **Add New Reference**.</span></span>  
  
3.  <span data-ttu-id="92893-153">**프로젝트** 탭을 클릭합니다.  WPFClock을 선택하고 [확인]을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-153">Click the **Projects** tab.  Select WPFClock, click OK.</span></span>  
  
4.  <span data-ttu-id="92893-154">클릭 **확인** 참조를 추가 하기 위한 win32clock 속성 페이지를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>  
  
## <a name="hwndsource"></a><span data-ttu-id="92893-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="92893-155">HwndSource</span></span>  
 <span data-ttu-id="92893-156">다음을 사용 하 여 <xref:System.Windows.Interop.HwndSource> 있도록는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> HWND 같습니다.</span><span class="sxs-lookup"><span data-stu-id="92893-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span>  <span data-ttu-id="92893-157">다음 코드 블록을 C++ 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-157">You add this block of code to a C++ file:</span></span>  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
  
    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
        HwndSource^ source = gcnew HwndSource(  
            0, // class style  
            WS_VISIBLE | WS_CHILD, // style  
            0, // exstyle  
            x, y, width, height,  
            "hi", // NAME  
            IntPtr(parent)        // parent window   
            );  
  
        UIElement^ page = gcnew WPFClock::Clock();  
        source->RootVisual = page;  
        return (HWND) source->Handle.ToPointer();  
    }  
}  
}  
```  
  
 <span data-ttu-id="92893-158">다음은 약간의 설명이 필요할 수 있는 긴 코드 조각입니다.</span><span class="sxs-lookup"><span data-stu-id="92893-158">This is a long piece of code that could use some explanation.</span></span>  <span data-ttu-id="92893-159">첫 번째 부분은 다양한 절이어서 모든 호출을 정규화할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92893-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 <span data-ttu-id="92893-160">만드는 함수를 정의한 다음는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 넣습니다는 <xref:System.Windows.Interop.HwndSource> 주위 HWND 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 <span data-ttu-id="92893-161">먼저 만듭니다는 <xref:System.Windows.Interop.HwndSource>, 매개 변수를 가진 CreateWindow 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>  
  
```  
HwndSource^ source = gcnew HwndSource(  
    0, // class style  
    WS_VISIBLE | WS_CHILD, // style  
    0, // exstyle  
    x, y, width, height,  
    "hi", // NAME  
    IntPtr(parent) // parent window   
    );  
```  
  
 <span data-ttu-id="92893-162">다음 만듭니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 클래스의 생성자를 호출 하 여:</span><span class="sxs-lookup"><span data-stu-id="92893-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 <span data-ttu-id="92893-163">다음에 해당 페이지를 연결 된 <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="92893-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>  
  
```  
source->RootVisual = page;  
```  
  
 <span data-ttu-id="92893-164">마지막 줄에 대 한 HWND를 반환 하 고는 <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="92893-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## <a name="positioning-the-hwnd"></a><span data-ttu-id="92893-165">Hwnd 위치 지정</span><span class="sxs-lookup"><span data-stu-id="92893-165">Positioning the Hwnd</span></span>  
 <span data-ttu-id="92893-166">포함 하는 HWND를 마쳤으므로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 내 HWND를 배치 해야 하는 클록의 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="92893-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span>  <span data-ttu-id="92893-167">HWND를 배치할 위치를 알고 있는 경우 전달 하면 해당 크기와 위치는 `GetHwnd` 앞에서 정의한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="92893-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span>  <span data-ttu-id="92893-168">그러나 리소스 파일을 사용하여 대화 상자를 정의했으므로 HWND를 배치할 위치를 정확하게 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92893-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span>  <span data-ttu-id="92893-169">사용할 수 있습니다는 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 배치 하는 대화 상자 편집기는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 정적 클록 이동 하려는 위치를 제어 ("Insert 클록 여기")를 배치에 사용할는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록입니다.</span><span class="sxs-lookup"><span data-stu-id="92893-169">You can use the [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>  
  
 <span data-ttu-id="92893-170">WM_INITDIALOG를 처리 하면 위치도 사용 하 여 `GetDlgItem` 자리 표시자 정적 HWND를 검색할 수:</span><span class="sxs-lookup"><span data-stu-id="92893-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 <span data-ttu-id="92893-171">계산한 다음 크기와 위치 자리 표시자 정적 행과의 활용할 수 있도록는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>  
  
 <span data-ttu-id="92893-172">RECT 사각형의 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="92893-172">RECT rectangle;</span></span>  
  
```  
GetWindowRect(placeholder, &rectangle);  
int width = rectangle.right - rectangle.left;  
int height = rectangle.bottom - rectangle.top;  
POINT point;  
point.x = rectangle.left;  
point.y = rectangle.top;  
result = MapWindowPoints(NULL, hDlg, &point, 1);  
```  
  
 <span data-ttu-id="92893-173">그런 다음 자리 표시자 STATIC을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="92893-173">Then you hide the placeholder STATIC:</span></span>  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 <span data-ttu-id="92893-174">만들고는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계 그 위치에는 HWND:</span><span class="sxs-lookup"><span data-stu-id="92893-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 <span data-ttu-id="92893-175">자습서를 재미 및 실제 생성을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록 있습니다 작성 해야 합니다는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이 시점에서 시계 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="92893-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="92893-176">코드 숨김에서 몇 개의 이벤트 처리기만 사용하여 태그에서 거의 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92893-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="92893-177">이 자습서의 상호 운용 하는 방법에 대 한 저장소와 컨트롤 디자인 대해서는 알아보지 때문 전체에 대 한 코드는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록은 제공 코드 블록 작성 하거나 각 부분의 의미에 대 한 개별적인 지침이 설명 없이 여기 합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="92893-178">이 코드를 자유롭게 사용하여 컨트롤의 모양과 느낌 또는 기능을 변경해 보세요.</span><span class="sxs-lookup"><span data-stu-id="92893-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>  
  
 <span data-ttu-id="92893-179">다음은 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="92893-179">Here is the markup:</span></span>  
  
 [!code-xaml[Win32Clock#AllClockXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 <span data-ttu-id="92893-180">다음은 함께 제공되는 코드 숨김입니다.</span><span class="sxs-lookup"><span data-stu-id="92893-180">And here is the accompanying code-behind:</span></span>  
  
 [!code-csharp[Win32Clock#AllClockCS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 <span data-ttu-id="92893-181">최종 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="92893-181">The final result looks like:</span></span>  
  
 <span data-ttu-id="92893-182">![날짜 및 시간 속성 대화 상자](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")</span><span class="sxs-lookup"><span data-stu-id="92893-182">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")</span></span>  
  
 <span data-ttu-id="92893-183">이 스크린 샷을 생성 하는 코드를 최종 결과 비교 하려면 참조 [Win32 클록의 상호 운용 샘플](http://go.microsoft.com/fwlink/?LinkID=160051)합니다.</span><span class="sxs-lookup"><span data-stu-id="92893-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=160051).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92893-184">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92893-184">See Also</span></span>  
 <xref:System.Windows.Interop.HwndSource>  
 [<span data-ttu-id="92893-185">WPF 및 Win32 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="92893-185">WPF and Win32 Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [<span data-ttu-id="92893-186">Win32 시계 상호 운용 샘플</span><span class="sxs-lookup"><span data-stu-id="92893-186">Win32 Clock Interoperation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160051)
