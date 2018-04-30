---
title: '방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 00df44a3f87e5a3fc3374f1429f6b427e0d3d76e
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a><span data-ttu-id="69909-102">방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="69909-102">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>
<span data-ttu-id="69909-103">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]에서 웹 서비스를 호스트할 때 권한 부여 관리자를 응용 프로그램에 통합하여 서비스에 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69909-103">When [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hosts a Web service, you can integrate Authorization Manager into the application to provide authorization to the service.</span></span> <span data-ttu-id="69909-104">응용 프로그램 개발자는 권한 부여 관리자를 사용하여 개별 작업을 정의할 수 있습니다. 개별 작업은 그룹으로 분류되어 작업을 형성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69909-104">Authorization Manager enables an application developer to define individual operations, which can be grouped together to form tasks.</span></span> <span data-ttu-id="69909-105">관리자는 역할에 특정 작업 또는 개별 작업을 수행할 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69909-105">An administrator can then authorize roles to perform specific tasks or individual operations.</span></span> <span data-ttu-id="69909-106">권한 부여 관리자는 역할, 작업 및 사용자를 관리할 수 있도록 MMC(Microsoft Management Console) 스냅인과 같은 관리 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="69909-106">Authorization Manager provides an administration tool as a Microsoft Management Console (MMC) snap-in to manage roles, tasks, operations, and users.</span></span> <span data-ttu-id="69909-107">관리자는 XML 파일, Active Directory 또는 ADAM(Active Directory Application Mode) 저장소에서 권한 부여 관리자 정책 저장소를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="69909-107">Administrators configure an Authorization Manager policy store in an XML file, Active Directory, or in an Active Directory Application Mode (ADAM) store.</span></span>  
  
 <span data-ttu-id="69909-108">웹 서비스를 호스트하는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램에 대한 권한 부여 관리자 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자를 구성하여 권한 부여 관리자를 응용 프로그램에 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="69909-108">Authorization Manager is Integrated into the application by configuring the Authorization Manager [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider for the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application that is hosting the Web service.</span></span> <span data-ttu-id="69909-109">다른 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자와 마찬가지로 권한 부여 관리자 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자도 <`providers`> 요소를 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="69909-109">Like other [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role providers, the Authorization Manager [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider is configured using the <`providers`> element.</span></span>  
  
 <span data-ttu-id="69909-110">다음 코드 예제는 권한 부여 관리자를 응용 프로그램에 통합하는 웹 서비스에 대한 구성 파일의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="69909-110">The following code example is a portion of a configuration file for a Web service that is integrating Authorization Manager into the application.</span></span>  
  
```xml  
<system.web>  
    <roleManager enabled="true" defaultProvider="AzManRoleProvider">  
      <providers>  
        <add name="AzManRoleProvider"  
             type="System.Web.Security.AuthorizationStoreRoleProvider, System.Web, Version=2.0.0.0, Culture=neutral, publicKeyToken=b03f5f7f11d50a3a"  
             connectionStringName="AzManPolicyStoreConnectionString"   
             applicationName="SecureService"/>  
      </providers>  
    </roleManager>  
</system.web>  
```  
  
 <span data-ttu-id="69909-111">통합에 대 한 자세한 내용은 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 역할 공급자를는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램 참조 [하는 방법: ASP.NET 역할 공급자를 사용 하 여 서비스와](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69909-111">For more information about integrating an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span> <span data-ttu-id="69909-112">권한 부여 관리자를 사용 하는 방법에 대 한 자세한 내용은 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], 참조 [하는 방법: ASP.NET 2.0과 함께 사용 하 여 권한 부여 관리자 (AzMan)](http://go.microsoft.com/fwlink/?LinkId=71303)합니다.</span><span class="sxs-lookup"><span data-stu-id="69909-112">For more information about using Authorization Manager with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], see [How to: Use Authorization Manager (AzMan) with ASP.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=71303).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69909-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69909-113">See Also</span></span>  
 [<span data-ttu-id="69909-114">방법: 서비스에서 ASP.NET 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="69909-114">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
