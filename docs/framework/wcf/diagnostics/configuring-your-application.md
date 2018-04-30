---
title: 응용 프로그램 구성
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 170583239ed357904e723aebdaef9809938b5123
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="configuring-your-application"></a><span data-ttu-id="cf3eb-102">응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="cf3eb-102">Configuring Your Application</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="cf3eb-103">에서는 .NET 구성 시스템이 사용되며 컴퓨터와 응용 프로그램 범위 모두에서 서비스를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf3eb-103"> uses the .NET configuration system and allows you to configure services at both the machine and application scope.</span></span>  
  
 <span data-ttu-id="cf3eb-104">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 정의한 구성 설정은 `<system.serviceModel>` 섹션 그룹에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf3eb-104">Configuration settings defined by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are located in the `<system.serviceModel>` section group.</span></span> <span data-ttu-id="cf3eb-105">구성 하는 방법에 대 한 자세한 내용은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cf3eb-105">For more information about how to configure a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, see the following topics:</span></span>  
  
-   [<span data-ttu-id="cf3eb-106">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="cf3eb-106">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [<span data-ttu-id="cf3eb-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cf3eb-107">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 <span data-ttu-id="cf3eb-108">응용 프로그램에서 정의한 구성 설정은 `<appSettings>` 섹션 그룹에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf3eb-108">Application-defined configurations settings are defined in the `<appSettings>` section group.</span></span> <span data-ttu-id="cf3eb-109">.NET 구성 파일에서 응용 프로그램 설정에 대 한 자세한 내용은 참조 [ \<g s >](http://go.microsoft.com/fwlink/?LinkId=95159)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf3eb-109">For more information about application settings in .NET configuration files, see [\<appSettings>](http://go.microsoft.com/fwlink/?LinkId=95159).</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="cf3eb-110">Configuration Editor 사용</span><span class="sxs-lookup"><span data-stu-id="cf3eb-110">Using the Configuration Editor</span></span>  
 <span data-ttu-id="cf3eb-111">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] [Configuration Editor 도구 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) 관리자와 개발자가 생성 및 구성 설정을 수정할 수 있습니다 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 그래픽 사용자 인터페이스를 사용 하 여 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="cf3eb-111">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)][Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) allows administrators and developers to create and modify configuration settings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services using a graphical user interface.</span></span> <span data-ttu-id="cf3eb-112">이 도구를 사용하면 XML 구성 파일을 직접 수정하지 않고도 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 바인딩, 동작, 서비스 및 진단에 대한 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf3eb-112">With this tool, you can manage settings for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bindings, behaviors, services, and diagnostics without directly editing XML configuration files.</span></span>  
  
## <a name="editing-configuration-files-in-visual-studio"></a><span data-ttu-id="cf3eb-113">Visual Studio에서 구성 파일 편집</span><span class="sxs-lookup"><span data-stu-id="cf3eb-113">Editing Configuration Files in Visual Studio</span></span>  
 <span data-ttu-id="cf3eb-114">구성 파일을 편집 하려면는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Visual Studio에서 프로젝트 서비스를 마우스 오른쪽 단추로 클릭에서 **솔루션 탐색기** 선택 하 고는 **WCF 구성 편집** 상황에 맞는 메뉴 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="cf3eb-114">To edit the configuration file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service project in Visual Studio, right click it in **Solution Explorer** and choose the **Edit WCF Config** context menu item.</span></span> <span data-ttu-id="cf3eb-115">그러면는 [Configuration Editor 도구 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf3eb-115">This launches the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf3eb-116">구성 파일을 편집 하는 경우는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 에서 마우스 오른쪽 단추로 클릭 하 여 Visual Studio에서 웹 서비스 프로젝트 **솔루션 탐색기**, 다음에 유의 **WCF 구성 편집** 상황에 맞는 메뉴 항목이 누락 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cf3eb-116">If you edit the configuration file of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web Service project in Visual Studio by right-clicking it in **Solution Explorer**, notice that the **Edit WCF Config** context menu item is missing.</span></span> <span data-ttu-id="cf3eb-117">이 문제를 해결 하려면, 클릭는 **도구** 메뉴 선택 **WCF 서비스 구성 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="cf3eb-117">To workaround this issue, click the **Tools** menu, and choose **WCF Service Config Editor**.</span></span> <span data-ttu-id="cf3eb-118">그런 다음 구성 파일을 마우스 오른쪽 단추로 클릭 하 사용할 수는 **WCF 구성 편집** 상황에 맞는 메뉴 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="cf3eb-118">After that, you can right-click a configuration file and use the **Edit WCF Config** context menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf3eb-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf3eb-119">See Also</span></span>  
 [<span data-ttu-id="cf3eb-120">Configuration Editor 도구(SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="cf3eb-120">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [<span data-ttu-id="cf3eb-121">서비스 구성</span><span class="sxs-lookup"><span data-stu-id="cf3eb-121">Configuring Services</span></span>](../../../../docs/framework/wcf/configuring-services.md)  
 [<span data-ttu-id="cf3eb-122">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cf3eb-122">\<system.serviceModel></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
