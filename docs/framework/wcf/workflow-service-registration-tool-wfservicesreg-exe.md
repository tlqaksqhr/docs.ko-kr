---
title: 워크플로 서비스 등록 도구(WFServicesReg.exe)
ms.date: 03/30/2017
ms.assetid: 9e92c87b-99c5-4e8d-9d53-7944cc2b47d3
ms.openlocfilehash: 3ea0f737cc050ec3f918044e0e105a41011a3e25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33506563"
---
# <a name="workflow-service-registration-tool-wfservicesregexe"></a><span data-ttu-id="4dcd0-102">워크플로 서비스 등록 도구(WFServicesReg.exe)</span><span class="sxs-lookup"><span data-stu-id="4dcd0-102">WorkFlow Service Registration Tool (WFServicesReg.exe)</span></span>
<span data-ttu-id="4dcd0-103">워크플로 서비스 등록 도구(WFServicesReg.exe)는 Windows WF(Workflow Foundation) 서비스의 구성 요소를 추가, 제거 또는 복구하는 데 사용할 수 있는 독립 실행형 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-103">Workflow Services Registration tool (WFServicesReg.exe) is a stand-alone tool that can be used to add, remove, or repair the configuration elements for Windows Workflow Foundation (WF) services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dcd0-104">구문</span><span class="sxs-lookup"><span data-stu-id="4dcd0-104">Syntax</span></span>  
  
```  
WFServicesReg.exe [-c | -r | -v | -m | -i]  
```  
  
## <a name="remarks"></a><span data-ttu-id="4dcd0-105">설명</span><span class="sxs-lookup"><span data-stu-id="4dcd0-105">Remarks</span></span>  
 <span data-ttu-id="4dcd0-106">이 도구는 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 설치 위치(특히 %windir%\Microsoft.NET\Framework\v3.5) 또는 %windir%\Microsoft.NET\Framework64\v3.5(64비트 시스템의 경우)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-106">The tool can be found at the [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] installation location, specifically, %windir%\Microsoft.NET\Framework\v3.5, or at %windir%\Microsoft.NET\Framework64\v3.5 in 64-bit machines.</span></span>  
  
 <span data-ttu-id="4dcd0-107">다음 표에서는 워크플로 서비스 등록 도구(WFServicesReg.exe)에서 사용할 수 있는 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-107">The following tables describe the options that can be used with the Workflow Services Registration tool (WFServicesReg.exe).</span></span>  
  
|<span data-ttu-id="4dcd0-108">옵션</span><span class="sxs-lookup"><span data-stu-id="4dcd0-108">Option</span></span>|<span data-ttu-id="4dcd0-109">설명</span><span class="sxs-lookup"><span data-stu-id="4dcd0-109">Description</span></span>|  
|------------|-----------------|  
|`/c`|<span data-ttu-id="4dcd0-110">Windows Workflow Services를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-110">Configures Windows Workflow Services.</span></span> <span data-ttu-id="4dcd0-111">설치 및 복구 시나리오에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-111">Used in install and repair scenarios.</span></span>|  
|`/r`|<span data-ttu-id="4dcd0-112">Windows Workflow Services 구성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-112">Removes Windows Workflow Services Configuration.</span></span>|  
|`/v`|<span data-ttu-id="4dcd0-113">구성 또는 제거에 대한 자세한 정보를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-113">Print verbose information (for either configuration or removal).</span></span>|  
|`/m`|<span data-ttu-id="4dcd0-114">MSI 로깅 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-114">Enables MSI logging format.</span></span>|  
|`/i`|<span data-ttu-id="4dcd0-115">응용 프로그램이 실행될 때 창을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-115">Minimizes the window when the application runs.</span></span>|  
  
## <a name="registration"></a><span data-ttu-id="4dcd0-116">등록</span><span class="sxs-lookup"><span data-stu-id="4dcd0-116">Registration</span></span>  
 <span data-ttu-id="4dcd0-117">이 도구는 Web.config 파일을 검사하고 다음을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-117">The tool inspects the Web.config file and registers the following:</span></span>  
  
-   [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]<span data-ttu-id="4dcd0-118"> 참조 어셈블리</span><span class="sxs-lookup"><span data-stu-id="4dcd0-118"> reference assemblies.</span></span>  
  
-   <span data-ttu-id="4dcd0-119">.xoml 파일의 빌드 공급자</span><span class="sxs-lookup"><span data-stu-id="4dcd0-119">A build provider for .xoml files.</span></span>  
  
-   <span data-ttu-id="4dcd0-120">.xoml 및 .rules 파일의 HTTP 처리기</span><span class="sxs-lookup"><span data-stu-id="4dcd0-120">HTTP handlers for .xoml and .rules files.</span></span>  
  
 <span data-ttu-id="4dcd0-121">이 도구는 Machine.config 파일을 검사하고 다음 확장을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-121">The tool inspects the Machine.config file and registers the following extensions:</span></span>  
  
-   <span data-ttu-id="4dcd0-122">behaviorExtensions</span><span class="sxs-lookup"><span data-stu-id="4dcd0-122">behaviorExtensions</span></span>  
  
-   <span data-ttu-id="4dcd0-123">bindingElementExtensions</span><span class="sxs-lookup"><span data-stu-id="4dcd0-123">bindingElementExtensions</span></span>  
  
-   <span data-ttu-id="4dcd0-124">bindingExtensions</span><span class="sxs-lookup"><span data-stu-id="4dcd0-124">bindingExtensions</span></span>  
  
 <span data-ttu-id="4dcd0-125">또한 다음과 같은 클라이언트 메타데이터 가져오기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-125">The tool also registers the following client metadata importers:</span></span>  
  
-   <span data-ttu-id="4dcd0-126">policyImporters</span><span class="sxs-lookup"><span data-stu-id="4dcd0-126">policyImporters</span></span>  
  
-   <span data-ttu-id="4dcd0-127">wsdlImporters</span><span class="sxs-lookup"><span data-stu-id="4dcd0-127">wsdlImporters</span></span>  
  
 <span data-ttu-id="4dcd0-128">이 도구는 또한 IIS 메타베이스에 .xoml과 .rules 스크립트 맵 및 처리기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-128">The tool also registers .xoml and .rules scriptmaps and handlers in the IIS metabase.</span></span>  
  
 <span data-ttu-id="4dcd0-129">[!INCLUDE[ws2003](../../../includes/ws2003-md.md)] 및 [!INCLUDE[wxp](../../../includes/wxp-md.md)] 시스템(IIS 5.1 및 [!INCLUDE[iis601](../../../includes/iis601-md.md)])에서는 .xoml과 .rules 스크립트 맵 집합 하나가 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-129">On [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] and [!INCLUDE[wxp](../../../includes/wxp-md.md)] machines (IIS 5.1 and [!INCLUDE[iis601](../../../includes/iis601-md.md)]), one set of .xoml and .rules scriptmaps are registered.</span></span>  
  
 <span data-ttu-id="4dcd0-130">64비트 시스템에서 도구는 `Enable32BitAppOnWin64` 스위치를 사용할 수 있는 경우 WOW 모드 스크립트 맵을 등록하고, `Enable32BitAppOnWin64` 스위치를 사용할 수 없는 경우 네이티브 64비트 스크립트 맵을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-130">On 64-bit machines, the tool registers WOW mode scriptmaps if the `Enable32BitAppOnWin64` switch is enabled, or native 64-bit scriptmaps if the `Enable32BitAppOnWin64` switch is disabled.</span></span>  
  
 <span data-ttu-id="4dcd0-131">[!INCLUDE[wv](../../../includes/wv-md.md)] 및 Windows Server 2008 (IIS 7.0 이상) 등록 된 컴퓨터,.xoml과.rules 처리기 집합 두: 하나는 통합된 모드 용이고 하나는 클래식 모드용입니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-131">On [!INCLUDE[wv](../../../includes/wv-md.md)] and Windows Server 2008 (IIS 7.0 and above) machines, two sets of .xoml and .rules handlers are registered: one for Integrated mode and one for Classic mode.</span></span>  
  
 <span data-ttu-id="4dcd0-132">64비트 시스템에서는 `Enable32BitAppOnWin64` 스위치의 상태에 관계없이 처리기 집합 세 개가 등록됩니다. 하나는 통합 모드용, 하나는 WOW 클래식 모드용, 하나는 네이티브 64비트 클래식 모드용입니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-132">On 64-bit machines, three sets of handlers are registered (regardless of the state of the `Enable32BitAppOnWin64` switch): one for Integrated mode, one for WOW Classic mode and one for native 64-bit Classic mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4dcd0-133">ServiceModelreg.exe와 달리 WFServicesReg.exe에서는 특정 웹 사이트에 대한 스크립트 맵이나 처리기를 추가, 제거 또는 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-133">Unlike ServiceModelreg.exe, WFServicesReg.exe does not allow adding, removing, or repairing scriptmaps or handlers for a particular Web site.</span></span> <span data-ttu-id="4dcd0-134">이러한 문제의 해결 방법에 대해서는 "스크립트 맵 복구" 단원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-134">For a workaround to this issue, see the "Repairing the Scriptmaps" section.</span></span>  
  
## <a name="usage-scenarios"></a><span data-ttu-id="4dcd0-135">사용 시나리오</span><span class="sxs-lookup"><span data-stu-id="4dcd0-135">Usage Scenarios</span></span>  
  
### <a name="installing-iis-after-net-framework-35-is-installed"></a><span data-ttu-id="4dcd0-136">.NET Framework 3.5 설치 후 IIS 설치</span><span class="sxs-lookup"><span data-stu-id="4dcd0-136">Installing IIS after .NET Framework 3.5 is installed</span></span>  
 <span data-ttu-id="4dcd0-137">[!INCLUDE[ws2003](../../../includes/ws2003-md.md)] 시스템에서는 IIS 설치 전에 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-137">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] is installed prior to IIS installation.</span></span> <span data-ttu-id="4dcd0-138">IIS를 사용할 수 없으므로 .xoml 및 .rules 스크립트 맵을 설치하지 않아도 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-138">Due to the unavailability of the IIS metabase, installation of [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] succeeds without installing .xoml and .rules scriptmaps.</span></span>  
  
 <span data-ttu-id="4dcd0-139">IIS가 설치된 후에는 `/c` 스위치와 함께 WFServicesReg.exe 도구를 사용하여 이러한 특정 스크립트 맵을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-139">After IIS is installed, you can use the WFServicesReg.exe tool with the `/c` switch to install these specific scriptmaps.</span></span>  
  
### <a name="repairing-the-scriptmaps"></a><span data-ttu-id="4dcd0-140">스크립트 맵 복구</span><span class="sxs-lookup"><span data-stu-id="4dcd0-140">Repairing the Scriptmaps</span></span>  
  
#### <a name="scriptmap-deleted-under-web-sites-node"></a><span data-ttu-id="4dcd0-141">웹 사이트 노드에서 삭제된 스크립트 맵</span><span class="sxs-lookup"><span data-stu-id="4dcd0-141">Scriptmap deleted under Web Sites node</span></span>  
 <span data-ttu-id="4dcd0-142">[!INCLUDE[ws2003](../../../includes/ws2003-md.md)] 시스템에서 .xoml이나 .rules가 웹 사이트 노드에서 실수로 삭제된 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-142">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, .xoml or .rules is accidentally deleted from the Web Sites node.</span></span> <span data-ttu-id="4dcd0-143">이런 경우 `/c` 스위치와 함께 WFServicesReg.exe 도구를 실행하여 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-143">This can be repaired by running the WFServicesReg.exe tool with the `/c` switch.</span></span>  
  
#### <a name="scriptmap-deleted-under-a-particular-web-site"></a><span data-ttu-id="4dcd0-144">특정 웹 사이트에서 삭제된 스크립트 맵</span><span class="sxs-lookup"><span data-stu-id="4dcd0-144">Scriptmap deleted under a particular Web site</span></span>  
 <span data-ttu-id="4dcd0-145">[!INCLUDE[ws2003](../../../includes/ws2003-md.md)] 시스템에서 .xoml이나 .rules가 웹 사이트 노드가 아닌 특정 웹 사이트(예: 기본 웹 사이트)에서 실수로 삭제된 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-145">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, .xoml or .rules is accidentally deleted from a particular Web site (for example, the Default Web Site) rather than from the Web Sites node.</span></span>  
  
 <span data-ttu-id="4dcd0-146">특정 웹 사이트에 대 한 삭제 된 처리기를 복구 하려면 "WFServicesReg.exe /r"을 실행 해야 모든 웹 사이트의 처리기를 제거 하려면 "WFServicesReg.exe /c"를 실행 한 다음 모든 웹 사이트에 대 한 적절 한 처리기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-146">To repair deleted handlers for a particular Web site, you should run "WFServicesReg.exe /r" to remove handlers from all Web sites, then run "WFServicesReg.exe /c" to create the appropriate handlers for all Web sites.</span></span>  
  
### <a name="configuring-handlers-after-switching-iis-mode"></a><span data-ttu-id="4dcd0-147">IIS 모드 전환 후 처리기 구성</span><span class="sxs-lookup"><span data-stu-id="4dcd0-147">Configuring handlers after switching IIS mode</span></span>  
 <span data-ttu-id="4dcd0-148">IIS가 공유 구성 모드에 있는 경우 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]를 설치하면 IIS 메타베이스가 공유 위치에 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-148">When IIS is in shared configuration mode and [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] is installed, the IIS metabase is configured under a shared location.</span></span> <span data-ttu-id="4dcd0-149">IIS를 비공유 구성 모드로 전환하면 로컬 메타베이스에 필요한 처리기가 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-149">If you switch IIS to non-shared configuration mode, the local metabase will not contain the required handlers.</span></span> <span data-ttu-id="4dcd0-150">로컬 메타 베이스를 제대로 구성 하려면 로컬 또는 실행 "WFServicesReg.exe /c", 로컬 메타 베이스를 구성 하는에 메타 베이스를 공유 하거나 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd0-150">To configure the local metabase properly, you can either import the shared metabase to local, or run "WFServicesReg.exe /c", which configures the local metabase.</span></span>
