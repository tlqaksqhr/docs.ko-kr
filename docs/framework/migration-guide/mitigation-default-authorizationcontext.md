---
title: "완화: 기본 AuthorizationContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cfeee63-b148-429a-a7e6-6fe9b0cb7610
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 48363d0f8e515b703e49761a763379566e217844
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-default-authorizationcontext"></a><span data-ttu-id="8e262-102">완화: 기본 AuthorizationContext</span><span class="sxs-lookup"><span data-stu-id="8e262-102">Mitigation: Default AuthorizationContext</span></span>
<span data-ttu-id="8e262-103">`null``authorizationPolicies` 인수가 있는 <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29>에 대한 호출에서 반환한 <xref:System.IdentityModel.Policy.AuthorizationContext> 구현이 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에서 해당 구현을 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="8e262-103">The implementation of the <xref:System.IdentityModel.Policy.AuthorizationContext> returned by a call to the <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> with a `null``authorizationPolicies` argument has changed its implementation in the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].</span></span>  
  
## <a name="impact"></a><span data-ttu-id="8e262-104">영향</span><span class="sxs-lookup"><span data-stu-id="8e262-104">Impact</span></span>  
 <span data-ttu-id="8e262-105">드문 경우이지만 사용자 지정 인증을 사용하는 WCF 앱은 다르게 동작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e262-105">In rare cases, WCF apps that use custom authentication may see behavioral differences.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="8e262-106">완화</span><span class="sxs-lookup"><span data-stu-id="8e262-106">Mitigation</span></span>  
 <span data-ttu-id="8e262-107">다음 두 가지 방법 중 하나로 이전 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e262-107">You can restore the previous behavior in either of two ways:</span></span>  
  
-   <span data-ttu-id="8e262-108">4.6 이전 버전의 .NET Framework를 대상으로 사용하도록 앱을 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="8e262-108">Recompile your app to target an earlier version of the .NET Framework than 4.6.</span></span> <span data-ttu-id="8e262-109">IIS 호스트 서비스의 경우 이전 버전의.NET Framework를 대상으로 하는 `<httpRuntime targetFramework="x.x" />` 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8e262-109">For IIS-hosted services, use the `<httpRuntime targetFramework="x.x" />` element to target an earlier version of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="8e262-110">다음 줄을 app.config 파일의 `<appSettings>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8e262-110">Add the following line to the `<appSettings>` section of your app.config file:</span></span>  
  
    ```xml  
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8e262-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e262-111">See Also</span></span>  
 [<span data-ttu-id="8e262-112">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="8e262-112">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

