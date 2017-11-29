---
title: "설치 문제 해결"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1644f885-c408-4d5f-a5c7-a1a907bc8acd
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7c7d4dcd5e10d04ef8d43a7581860d94ef970341
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="troubleshooting-setup-issues"></a><span data-ttu-id="bfc41-102">설치 문제 해결</span><span class="sxs-lookup"><span data-stu-id="bfc41-102">Troubleshooting Setup Issues</span></span>
<span data-ttu-id="bfc41-103">이 항목에서는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 설치 문제를 해결하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-103">This topic describes how to troubleshoot [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] set up issues.</span></span>  
  
## <a name="some-windows-communication-foundation-registry-keys-are-not-repaired-by-performing-an-msi-repair-operation-on-the-net-framework-30"></a><span data-ttu-id="bfc41-104">일부 Windows Communication Foundation 레지스트리 키를 .NET Framework 3.0에서 MSI 복구 작업을 수행하여 복구할 수 없음</span><span class="sxs-lookup"><span data-stu-id="bfc41-104">Some Windows Communication Foundation Registry Keys are not Repaired by Performing an MSI Repair Operation on the .NET Framework 3.0</span></span>  
 <span data-ttu-id="bfc41-105">다음과 같은 레지스트리 키를 삭제한 경우 이 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-105">If you delete any of the following registry keys:</span></span>  
  
-   <span data-ttu-id="bfc41-106">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="bfc41-106">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelService 3.0.0.0</span></span>  
  
-   <span data-ttu-id="bfc41-107">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="bfc41-107">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelOperation 3.0.0.0</span></span>  
  
-   <span data-ttu-id="bfc41-108">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="bfc41-108">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\ServiceModelEndpoint 3.0.0.0</span></span>  
  
-   <span data-ttu-id="bfc41-109">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="bfc41-109">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SMSvcHost 3.0.0.0</span></span>  
  
-   <span data-ttu-id="bfc41-110">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0</span><span class="sxs-lookup"><span data-stu-id="bfc41-110">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MSDTC Bridge 3.0.0.0</span></span>  
  
 <span data-ttu-id="bfc41-111">시작 하는.NET Framework 3.0 설치 관리자를 사용 하 여 복구를 실행 하는 경우에 키 다시 생성 되지 않습니다는 **프로그램 추가/제거** 애플릿을 **제어판**합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-111">The keys are not re-created if you run repair by using the .NET Framework 3.0 installer launched from the **Add/Remove Programs** applet in **Control Panel**.</span></span> <span data-ttu-id="bfc41-112">해당 키를 다시 만들려면 .NET Framework 3.0을 제거하고 다시 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-112">To recreate these keys correctly, the user must uninstall and reinstall the .NET Framework 3.0.</span></span>  
  
## <a name="wmi-service-corruption-blocks-installation-of-the-windows-communication-foundation-wmi-provider-during-installation-of-net-framework-30-package"></a><span data-ttu-id="bfc41-113">.NET Framework 3.0 패키지 설치 시 WMI 서비스 손상으로 인해 Windows Communication Foundation WMI 공급자가 설치되지 않음</span><span class="sxs-lookup"><span data-stu-id="bfc41-113">WMI Service Corruption Blocks Installation of the Windows Communication Foundation WMI provider during installation of .NET Framework 3.0 package</span></span>  
 <span data-ttu-id="bfc41-114">WMI 서비스 손상으로 인해 Windows Communication Foundation WMI 공급자가 설치되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-114">WMI Service Corruption may block the installation of the Windows Communication Foundation WMI provider.</span></span> <span data-ttu-id="bfc41-115">설치 시 Windows Communication Foundation 설치 관리자가 mofcomp.exe 구성 요소를 사용하여 WCF .mof 파일을 등록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-115">During installation the Windows Communication Foundation installer is unable to register the WCF .mof file using the mofcomp.exe component.</span></span> <span data-ttu-id="bfc41-116">다음과 같은 증상이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-116">The following is a list of symptoms:</span></span>  
  
1.  <span data-ttu-id="bfc41-117">.NET Framework 3.0 설치를 완료했지만 WCF WMI 공급자가 등록되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-117">.NET Framework 3.0 installation completes successfully, but the WCF WMI provider is not registered.</span></span>  
  
2.  <span data-ttu-id="bfc41-118">오류 이벤트가 WCF의 WMI 공급자 등록이나 mofcomp.exe 실행에 관련된 문제를 참조하는 응용 프로그램 이벤트 로그에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-118">An error event appears in the application event log that references problems registering the WMI provider for WCF, or running mofcomp.exe.</span></span>  
  
3.  <span data-ttu-id="bfc41-119">사용자의 %temp% 디렉터리에 있는 이름이 dd_wcf_retCA*인 설치 로그 파일에 WCF WMI 공급자 등록 실패에 대한 참조가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-119">The setup log file named dd_wcf_retCA* in the user's %temp% directory contains references to failure to register the WCF WMI provider.</span></span>  
  
4.  <span data-ttu-id="bfc41-120">다음과 같은 예외가 이벤트 로그나 설치 추적 로그 파일에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-120">An exception such as one the following may be listed in the event log or setup trace log file:</span></span>  
  
     <span data-ttu-id="bfc41-121">ServiceModelReg [11:09:59:046]: System.ApplicationException: "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"을(를) 통해 E:\WINDOWS\system32\wbem\mofcomp.exe을(를) 실행하는 동안 예기치 않은 3 결과가 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-121">ServiceModelReg [11:09:59:046]: System.ApplicationException: Unexpected result 3 executing E:\WINDOWS\system32\wbem\mofcomp.exe with "E:\WINDOWS\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModel.mof"</span></span>  
  
     <span data-ttu-id="bfc41-122">또는</span><span class="sxs-lookup"><span data-stu-id="bfc41-122">or:</span></span>  
  
     <span data-ttu-id="bfc41-123">ServiceModelReg [07:19:33:843]: System.TypeInitializationException: 'System.Management.ManagementPath'의 형식 이니셜라이저에서 예외를 throw했습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-123">ServiceModelReg [07:19:33:843]: System.TypeInitializationException: The type initializer for 'System.Management.ManagementPath' threw an exception.</span></span> <span data-ttu-id="bfc41-124">---> System.Runtime.InteropServices.COMException (0x80040154): 80040154 오류로 인해 CLSID가 {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA}인 구성 요소의 COM 클래스 팩터리를 검색하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-124">---> System.Runtime.InteropServices.COMException (0x80040154): Retrieving the COM class factory for component with CLSID {CF4CC405-E2C5-4DDD-B3CE-5E7582D8C9FA} failed due to the following error: 80040154.</span></span>  
  
     <span data-ttu-id="bfc41-125">또는</span><span class="sxs-lookup"><span data-stu-id="bfc41-125">or:</span></span>  
  
     <span data-ttu-id="bfc41-126">ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: 파일이나 어셈블리 'C:\WINDOWS\system32\wbem\mofcomp.exe' 또는 여기에 종속되어 있는 파일이나 어셈블리 중 하나를 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-126">ServiceModelReg [07:19:32:750]: System.IO.FileNotFoundException: Could not load file or assembly 'C:\WINDOWS\system32\wbem\mofcomp.exe' or one of its dependencies.</span></span> <span data-ttu-id="bfc41-127">지정한 파일을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-127">The system cannot find the file specified.</span></span>  
  
     <span data-ttu-id="bfc41-128">파일 이름: 'C:\WINDOWS\system32\wbem\mofcomp.exe</span><span class="sxs-lookup"><span data-stu-id="bfc41-128">File name: 'C:\WINDOWS\system32\wbem\mofcomp.exe</span></span>  
  
 <span data-ttu-id="bfc41-129">위에 설명한 문제를 해결하려면 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-129">The following steps must be followed to resolve the problem described previously.</span></span>  
  
1.  <span data-ttu-id="bfc41-130">실행 [WMI 진단 유틸리티의 버전 2.0](http://go.microsoft.com/fwlink/?LinkId=94685) WMI 서비스를 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-130">Run [the WMI Diagnosis Utility, version 2.0](http://go.microsoft.com/fwlink/?LinkId=94685) to repair the WMI service.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="bfc41-131">이 도구를 사용 하 여 참조는 [WMI 진단 유틸리티](http://go.microsoft.com/fwlink/?LinkId=94686) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-131"> using this tool, see the [WMI Diagnosis Utility](http://go.microsoft.com/fwlink/?LinkId=94686) topic.</span></span>  
  
 <span data-ttu-id="bfc41-132">사용 하 여.NET Framework 3.0 설치를 복구는 **프로그램 추가/제거** 에 애플릿을 **제어판**,.NET Framework 3.0를 제거/다시 설치 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-132">Repair the .NET Framework 3.0 installation by using the **Add/Remove Programs** applet located in **Control Panel**, or uninstall/reinstall the .NET Framework 3.0.</span></span>  
  
## <a name="repairing-net-framework-30-after-net-framework-35-installation-removes-configuration-elements-introduced-by-net-framework-35-in-machineconfig"></a><span data-ttu-id="bfc41-133">.NET Framework 3.5 설치 후 .NET Framework 3.0을 복구하면 machine.config에서 .NET Framework 3.5에 의해 추가된 구성 요소가 제거됨</span><span class="sxs-lookup"><span data-stu-id="bfc41-133">Repairing .NET Framework 3.0 after .NET Framework 3.5 Installation Removes Configuration Elements Introduced by .NET Framework 3.5 in machine.config</span></span>  
 <span data-ttu-id="bfc41-134">[!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]를 설치한 후 .NET Framework 3.0을 복구하면 machine.config에서 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]에 의해 추가된 구성 요소가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-134">If you do a repair of .NET Framework 3.0 after you installed [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)], configuration elements introduced by [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] in machine.config are removed.</span></span> <span data-ttu-id="bfc41-135">그러나 web.config는 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-135">However, the web.config remains intact.</span></span> <span data-ttu-id="bfc41-136">해결 방법은 복구 하는 것 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] ARP, 또는 사용을 통해 이후에 [워크플로 서비스 등록 도구 (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) 와 `/c` 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-136">The workaround is to repair [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] after this via ARP, or use the [WorkFlow Service Registration Tool (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) with the `/c` switch.</span></span>  
  
 <span data-ttu-id="bfc41-137">[워크플로 서비스 등록 도구 (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) %windir%\Microsoft.NET\framework\v3.5\ 또는 %windir%\Microsoft.NET\framework64\v3.5\에서 찾을 수</span><span class="sxs-lookup"><span data-stu-id="bfc41-137">[WorkFlow Service Registration Tool (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) can be found at %windir%\Microsoft.NET\framework\v3.5\ or %windir%\Microsoft.NET\framework64\v3.5\\</span></span>  
  
## <a name="configure-iis-properly-for-wcfwf-webhost-after-installing-net-framework-35"></a><span data-ttu-id="bfc41-138">.NET Framework 3.5 설치 후 WCF/WF Webhost에 대해 IIS를 올바로 구성</span><span class="sxs-lookup"><span data-stu-id="bfc41-138">Configure IIS Properly for WCF/WF Webhost after Installing .NET Framework 3.5</span></span>  
 <span data-ttu-id="bfc41-139">[!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]를 설치하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 관련 추가 IIS 구성 설정을 구성하지 못한 경우 설치 로그에 오류가 계속 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-139">When [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] installation fails to configure additional [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-related IIS configuration settings, it logs an error in the installation log and continues.</span></span> <span data-ttu-id="bfc41-140">필요한 구성 설정이 없기 때문에 WorkflowServices 응용 프로그램을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-140">Any attempt to run WorkflowServices applications will fail, since the required configuration settings are missing.</span></span> <span data-ttu-id="bfc41-141">예를 들어 xoml 또는 규칙 서비스를 로드하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-141">For example, loading xoml or rules service can fail.</span></span>  
  
 <span data-ttu-id="bfc41-142">문제를 해결 하려면 사용 하 여가이 문제는 [워크플로 서비스 등록 도구 (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) 와 `/c` 컴퓨터에서 IIS 스크립트 맵을 구성 하는 스위치입니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-142">To workaround this problem, use the [WorkFlow Service Registration Tool (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) with the `/c` switch to properly configure IIS script maps on the machine.</span></span> <span data-ttu-id="bfc41-143">[워크플로 서비스 등록 도구 (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) %windir%\Microsoft.NET\framework\v3.5\ 또는 %windir%\Microsoft.NET\framework64\v3.5\에서 찾을 수</span><span class="sxs-lookup"><span data-stu-id="bfc41-143">[WorkFlow Service Registration Tool (WFServicesReg.exe)](../../../docs/framework/wcf/workflow-service-registration-tool-wfservicesreg-exe.md) can be found at %windir%\Microsoft.NET\framework\v3.5\ or %windir%\Microsoft.NET\framework64\v3.5\\</span></span>  
  
## <a name="could-not-load-type-systemservicemodelactivationhttpmodule-from-assembly-systemservicemodel-version-3000-cultureneutral-publickeytokenb77a5c561934e089"></a><span data-ttu-id="bfc41-144">‘System.ServiceModel, Version 3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089’ 어셈블리에서 ‘System.ServiceModel.Activation.HttpModule’ 형식을 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-144">Could not load type ‘System.ServiceModel.Activation.HttpModule’ from assembly ‘System.ServiceModel, Version 3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089’</span></span>  
 <span data-ttu-id="bfc41-145">이 오류는 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]을 설치한 다음 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)][!INCLUDE[indigo2](../../../includes/indigo2-md.md)] HTTP 활성화를 사용하도록 설정한 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-145">This error occurs if [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] is installed and then [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)][!INCLUDE[indigo2](../../../includes/indigo2-md.md)] HTTP Activation is enabled.</span></span> <span data-ttu-id="bfc41-146">이 문제를 해결하려면 [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] 명령 프롬프트에서 다음 명령줄을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc41-146">To resolve the issue run the following command-line from inside the [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] Command Prompt:</span></span>  
  
```Output  
aspnet_regiis.exe -i -enable  
```  
  
## <a name="see-also"></a><span data-ttu-id="bfc41-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfc41-147">See Also</span></span>  
 [<span data-ttu-id="bfc41-148">설치 지침</span><span class="sxs-lookup"><span data-stu-id="bfc41-148">Set-Up Instructions</span></span>](../../../docs/framework/wcf/samples/set-up-instructions.md)
