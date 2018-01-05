---
title: "그래픽 렌더링 레지스트리 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- rendering graphics [WPF], registry settings
- rendering graphics [WPF]
- rendering graphics [WPF], troubleshooting
- troubleshooting graphics rendering [WPF]
- graphics [WPF], rendering
ms.assetid: f4b41b42-327d-407c-b398-3ed5f505df8b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a760f910bfd9e64fddfe2e7db3bb380cf744719d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="graphics-rendering-registry-settings"></a><span data-ttu-id="93e14-102">그래픽 렌더링 레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="93e14-102">Graphics Rendering Registry Settings</span></span>
<span data-ttu-id="93e14-103">이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 영향을 미치는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 그래픽 렌더링 레지스트리 설정에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-103">This topic provides an overview of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] graphics rendering registry settings that affect [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span>  
  

  
<a name="overview"></a>   
## <a name="when-to-use-graphics-rendering-registry-settings"></a><span data-ttu-id="93e14-104">그래픽 렌더링 레지스트리 설정을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="93e14-104">When to Use Graphics Rendering Registry Settings</span></span>  
 <span data-ttu-id="93e14-105">이러한 레지스트리 설정은 문제 해결, 디버깅 및 제품 지원 목적으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-105">These registry settings are provided for troubleshooting, debugging, and product support purposes.</span></span> <span data-ttu-id="93e14-106">레지스트리를 변경하면 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 영향을 주기 때문에 응용 프로그램은 자동으로 또는 설치 중에 이러한 레지스트리 키를 변경하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-106">Because changes to the registry affect all [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, your application should never alter these registry keys automatically, or during installation.</span></span>  
  
<a name="xpdmandwddm"></a>   
## <a name="what-are-xpdm-and-wddm"></a><span data-ttu-id="93e14-107">XPDM 및 WDDM이란?</span><span class="sxs-lookup"><span data-stu-id="93e14-107">What are XPDM and WDDM?</span></span>  
 <span data-ttu-id="93e14-108">일부 그래픽 렌더링 레지스트리 설정은 비디오 카드가 XPDM 드라이버를 사용하는지 또는 WDDM 드라이버를 사용하는지에 따라 기본값이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-108">Some of the graphics rendering registry settings have different default values, depending on whether your video card uses an XPDM or WDDM driver.</span></span> <span data-ttu-id="93e14-109">XPDM은 [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] 디스플레이 드라이버 모델이고 WDDM은 Windows 디스플레이 드라이버 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-109">XPDM is the [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] Display Driver Model and WDDM is the Windows Display Driver Model.</span></span> <span data-ttu-id="93e14-110">WDDM은 [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] 및 [!INCLUDE[win7](../../../../includes/win7-md.md)]이 실행되는 컴퓨터에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-110">WDDM is available on computers running [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] and [!INCLUDE[win7](../../../../includes/win7-md.md)].</span></span> <span data-ttu-id="93e14-111">XPDM은 [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)], [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] 및 [!INCLUDE[TLA#tla_winnetsvrfam](../../../../includes/tlasharptla-winnetsvrfam-md.md)]이 실행되는 컴퓨터에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-111">XPDM is available on computers running [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)], [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)], and [!INCLUDE[TLA#tla_winnetsvrfam](../../../../includes/tlasharptla-winnetsvrfam-md.md)].</span></span> <span data-ttu-id="93e14-112">WDDM에 대한 자세한 내용은 [Windows Vista 디스플레이 드라이버 모델 디자인 가이드](http://go.microsoft.com/fwlink/?LinkId=178394)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93e14-112">For more information about WDDM, see [Windows Vista Display Driver Model Design Guide](http://go.microsoft.com/fwlink/?LinkId=178394).</span></span>  
  
<a name="registry_settings"></a>   
## <a name="registry-settings"></a><span data-ttu-id="93e14-113">레지스트리 설정</span><span class="sxs-lookup"><span data-stu-id="93e14-113">Registry Settings</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="93e14-114">에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 렌더링을 제어하는 다음 네 개의 레지스트리 설정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-114"> provides four registry settings for controlling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] rendering:</span></span>  
  
|<span data-ttu-id="93e14-115">설정</span><span class="sxs-lookup"><span data-stu-id="93e14-115">Setting</span></span>|<span data-ttu-id="93e14-116">설명</span><span class="sxs-lookup"><span data-stu-id="93e14-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="93e14-117">**하드웨어 가속 옵션 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="93e14-117">**Disable Hardware Acceleration Option**</span></span>|<span data-ttu-id="93e14-118">하드웨어 가속을 사용해야 하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-118">Specifies whether hardware acceleration should be enabled.</span></span>|  
|<span data-ttu-id="93e14-119">**최대 다중 샘플 값**</span><span class="sxs-lookup"><span data-stu-id="93e14-119">**Maximum Multisample Value**</span></span>|<span data-ttu-id="93e14-120">[!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 콘텐츠를 앤티앨리어싱하는 데 사용할 다중 샘플링의 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-120">Specifies the degree of multisampling for antialiasing [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] content.</span></span>|  
|<span data-ttu-id="93e14-121">**필수 비디오 드라이버 날짜 설정**</span><span class="sxs-lookup"><span data-stu-id="93e14-121">**Required Video Driver Date Setting**</span></span>|<span data-ttu-id="93e14-122">시스템에서 2004년 11월 이전에 릴리스된 드라이버의 하드웨어 가속을 사용하지 않게 설정할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-122">Specifies whether the system disables hardware acceleration for drivers released before November 2004.</span></span>|  
|<span data-ttu-id="93e14-123">**참조 래스터라이저 옵션 사용**</span><span class="sxs-lookup"><span data-stu-id="93e14-123">**Use Reference Rasterizer Option**</span></span>|<span data-ttu-id="93e14-124">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 참조 래스터라이저를 사용해야 하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-124">Specifies whether [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] should use the reference rasterizer.</span></span>|  
  
 <span data-ttu-id="93e14-125">이러한 설정은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레지스트리 설정을 참조하는 방법을 아는 외부 구성 유틸리티에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-125">These settings can be accessed by any external configuration utility that knows how to reference the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] registry settings.</span></span> <span data-ttu-id="93e14-126">이러한 설정은 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 레지스트리 편집기를 통해 직접 값에 액세스하여 만들거나 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-126">These settings can also be created or modified by accessing the values directly by using the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Registry Editor.</span></span>  
  
<a name="disablehardwareacceleration"></a>   
## <a name="disable-hardware-acceleration-option"></a><span data-ttu-id="93e14-127">하드웨어 가속 옵션 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="93e14-127">Disable Hardware Acceleration Option</span></span>  
  
|<span data-ttu-id="93e14-128">레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="93e14-128">Registry key</span></span>|<span data-ttu-id="93e14-129">값 형식</span><span class="sxs-lookup"><span data-stu-id="93e14-129">Value type</span></span>|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\DisableHWAcceleration`|<span data-ttu-id="93e14-130">DWORD</span><span class="sxs-lookup"><span data-stu-id="93e14-130">DWORD</span></span>|  
  
 <span data-ttu-id="93e14-131">**하드웨어 가속 옵션 사용 안 함**을 사용하여 디버깅 및 테스트 목적으로 하드웨어 가속을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-131">The **disable hardware acceleration option** enables you to turn off hardware acceleration for debugging and test purposes.</span></span> <span data-ttu-id="93e14-132">응용 프로그램에서 렌더링 아티팩트를 표시되면 하드웨어 가속을 해제하세요.</span><span class="sxs-lookup"><span data-stu-id="93e14-132">When you see rendering artifacts in an application, try turning off hardware acceleration.</span></span> <span data-ttu-id="93e14-133">아티팩트가 사라지면 비디오 드라이버에 문제가 있는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-133">If the artifact disappears, the problem might be with your video driver.</span></span>  
  
 <span data-ttu-id="93e14-134">**하드웨어 가속 옵션 사용 안 함**은 0 또는 1의 DWORD 값입니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-134">The **disable hardware acceleration option** is a DWORD value that is either 0 or 1.</span></span> <span data-ttu-id="93e14-135">이 값이 1이면 하드웨어 가속이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-135">A value of 1 disables hardware acceleration.</span></span> <span data-ttu-id="93e14-136">이 값이 0이면 시스템이 하드웨어 가속 요구를 충족할 경우 하드웨어 가속이 사용됩니다. 자세한 내용은 [그래픽 렌더링 계층](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93e14-136">A value of 0 enables hardware acceleration, provided the system meets hardware acceleration requirements; for more information, see [Graphics Rendering Tiers](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).</span></span>  
  
<a name="maxmultisample"></a>   
## <a name="maximum-multisample-value"></a><span data-ttu-id="93e14-137">최대 다중 샘플 값</span><span class="sxs-lookup"><span data-stu-id="93e14-137">Maximum Multisample Value</span></span>  
  
|<span data-ttu-id="93e14-138">레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="93e14-138">Registry key</span></span>|<span data-ttu-id="93e14-139">값 형식</span><span class="sxs-lookup"><span data-stu-id="93e14-139">Value type</span></span>|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\MaxMultisampleType`|<span data-ttu-id="93e14-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="93e14-140">DWORD</span></span>|  
  
 <span data-ttu-id="93e14-141">**최대 다중 샘플 값**을 사용하여 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 콘텐츠의 앤티앨리어싱 최대 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-141">The **maximum multisample value** enables you to adjust the maximum amount of antialiasing of [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] content.</span></span> <span data-ttu-id="93e14-142">이 수준을 사용하여 [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)]에서 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 앤티앨리어싱을 사용하지 않도록 설정하거나 [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]에서 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-142">Use this level to disable [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] antialiasing in [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] or enable it in [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)].</span></span>  
  
 <span data-ttu-id="93e14-143">**최대 다중 샘플 값**은 0~16 사이의 DWORD 값입니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-143">The **maximum multisample value** is a DWORD value that ranges from 0 to 16.</span></span> <span data-ttu-id="93e14-144">값 0은 3차원 콘텐츠의 다중 샘플 앤티앨리어싱을 사용 안 함으로 설정하도록 지정하고, 값 16은 비디오 카드에서 지원할 경우 최대 16배의 다중 샘플 앤티앨리어싱을 사용하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-144">A value of 0 specifies that multisample antialiasing of 3-D content should be disabled, and a value of 16 will attempt to use up to 16x multisample antialiasing, if supported by the video card.</span></span> <span data-ttu-id="93e14-145">XPDM 드라이버를 사용하는 컴퓨터에서 이 레지스트리 키 값을 설정하면 응용 프로그램이 많은 양의 추가 비디오 메모리를 사용하고, [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 렌더링 성능이 저하되고, 렌더링 오류 및 안정성 문제가 발생할 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-145">Beware that setting this registry key value on computers using XPDM drivers will cause applications to use a large amount of additional video memory, decrease the performance of [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] rendering, and has the potential to introduce rendering errors and stability problems.</span></span>  
  
 <span data-ttu-id="93e14-146">이 레지스트리 키가 설정되지 않았으면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기본값은 XPDM 드라이버의 경우 0, WDDM 드라이버의 경우 4입니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-146">When this registry key is not set, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] defaults to 0 for XPDM drivers and 4 for WDDM drivers.</span></span>  
  
<a name="requiredvideodriverdatesetting"></a>   
## <a name="required-video-driver-date-setting"></a><span data-ttu-id="93e14-147">필수 비디오 드라이버 날짜 설정</span><span class="sxs-lookup"><span data-stu-id="93e14-147">Required Video Driver Date Setting</span></span>  
  
|<span data-ttu-id="93e14-148">레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="93e14-148">Registry key</span></span>|<span data-ttu-id="93e14-149">값 형식</span><span class="sxs-lookup"><span data-stu-id="93e14-149">Value type</span></span>|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\RequiredVideoDriverDate`|<span data-ttu-id="93e14-150">문자열</span><span class="sxs-lookup"><span data-stu-id="93e14-150">String</span></span>|  
  
 <span data-ttu-id="93e14-151">2004년 11월에 [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)]는 새 버전의 드라이버 테스트 지침을 발표했습니다. 이 날짜 이후에 작성된 드라이버는 더 나은 안정성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-151">In November, 2004, [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] released a new version of the driver testing guidelines; the drivers written after this date offer better stability.</span></span> <span data-ttu-id="93e14-152">기본적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 이러한 드라이버에 대해 하드웨어 가속 파이프라인을 사용하며, 이 날짜 이전에 게시된 XPDM 드라이버용 소프트웨어 렌더링으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-152">By default, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] will use the hardware acceleration pipeline for these drivers and will fall back to software rendering for XPDM drivers published before this date.</span></span>  
  
 <span data-ttu-id="93e14-153">**필수 비디오 드라이버 날짜 설정**을 통해 XPDM 드라이버에 대한 대체 최소 날짜를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-153">The **required video driver date setting** enables you to specify an alternate minimum date for XPDM drivers.</span></span> <span data-ttu-id="93e14-154">비디오 드라이버가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 지원하기에 충분히 안정적인 경우에만 2004년 11월 이전 날짜를 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-154">You should only specify a date earlier than November, 2004 if you are confident that your video driver is stable enough to support [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="93e14-155">필수 비디오 드라이버 설정은 다음 형식의 문자열을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-155">The required video driver setting takes a string of the following format:</span></span>  
  
||  
|-|  
|<span data-ttu-id="93e14-156">*YYYY* `/` *MM* `/` *DD*</span><span class="sxs-lookup"><span data-stu-id="93e14-156">*YYYY* `/` *MM* `/` *DD*</span></span>|  
  
 <span data-ttu-id="93e14-157">여기서 *YYYY*는 4자리 연도이고, *MM*은 2자리 월이고, *DD*는 2자리 일입니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-157">Where *YYYY* is the four-digit year, *MM* is the two-digit month, and *DD* is the two digit day.</span></span> <span data-ttu-id="93e14-158">이 값을 설정하지 않으면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 필수 비디오 드라이버 날짜로 2004년 11월을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-158">When this value is unset, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] uses November, 2004 as its required video driver date.</span></span>  
  
<a name="usereferencerasterizeroption"></a>   
## <a name="use-reference-rasterizer-option"></a><span data-ttu-id="93e14-159">참조 래스터라이저 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="93e14-159">Use Reference Rasterizer Option</span></span>  
  
|<span data-ttu-id="93e14-160">레지스트리 키</span><span class="sxs-lookup"><span data-stu-id="93e14-160">Registry key</span></span>|<span data-ttu-id="93e14-161">값 형식</span><span class="sxs-lookup"><span data-stu-id="93e14-161">Value type</span></span>|  
|------------------|----------------|  
|`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Avalon.Graphics\UseReferenceRasterizer`|<span data-ttu-id="93e14-162">DWORD</span><span class="sxs-lookup"><span data-stu-id="93e14-162">DWORD</span></span>|  
  
 <span data-ttu-id="93e14-163">**참조 래스터라이저 옵션 사용**을 사용하여 강제로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 디버깅을 위한 시뮬레이트된 하드웨어 렌더링 모드로 전환할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 하드웨어 모드로 전환되지만 실제 하드웨어 장치 대신 [!INCLUDE[TLA#tla_d3d](../../../../includes/tlasharptla-d3d-md.md)] 참조 소프트웨어 래스터라이저인 d3dref9.dll을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-163">The **use reference rasterizer option** enables you to force [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] into a simulated hardware rendering mode for debugging: [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] goes into hardware mode, but uses the [!INCLUDE[TLA#tla_d3d](../../../../includes/tlasharptla-d3d-md.md)] reference software rasterizer, d3dref9.dll, instead of an actual hardware device.</span></span>  
  
 <span data-ttu-id="93e14-164">참조 래스터라이저는 매우 느리지만 비디오 드라이버를 우회하여 드라이버 문제로 인한 렌더링 문제를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-164">The reference rasterizer is very slow, but bypasses your video driver to avoid any rendering issues caused by driver problems.</span></span> <span data-ttu-id="93e14-165">이러한 이유로 참조 래스터라이저를 사용하여 렌더링 문제가 비디오 드라이버로 인한 것인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-165">For this reason, you can use the reference rasterizer to determine if rendering issues are caused by the video driver.</span></span> <span data-ttu-id="93e14-166">d3dref9.dll 파일은 시스템 경로의 위치나 응용 프로그램의 로컬 디렉터리 같이 응용 프로그램이 액세스할 수 있는 위치에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-166">The d3dref9.dll file must be in a location where the application can access it, such as in any location in the system path or in the local directory of the application.</span></span>  
  
 <span data-ttu-id="93e14-167">**참조 래스터라이저 옵션 사용**은 DWORD 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-167">The **use reference rasterizer option** takes a DWORD value.</span></span> <span data-ttu-id="93e14-168">값이 0이면 참조 래스터라이저가 사용되지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-168">A value of 0 indicates that the reference rasterizer is not used.</span></span> <span data-ttu-id="93e14-169">0이 아닌 값을 지정하면 강제로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 참조 래스터라이저를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93e14-169">Any other non-zero value forces [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to use the reference rasterizer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93e14-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93e14-170">See Also</span></span>  
 [<span data-ttu-id="93e14-171">그래픽 렌더링 계층</span><span class="sxs-lookup"><span data-stu-id="93e14-171">Graphics Rendering Tiers</span></span>](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)  
 [<span data-ttu-id="93e14-172">WPF 그래픽 렌더링 개요</span><span class="sxs-lookup"><span data-stu-id="93e14-172">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
