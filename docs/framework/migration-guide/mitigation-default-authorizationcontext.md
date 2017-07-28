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
# <a name="mitigation-default-authorizationcontext"></a>완화: 기본 AuthorizationContext
`null``authorizationPolicies` 인수가 있는 <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29>에 대한 호출에서 반환한 <xref:System.IdentityModel.Policy.AuthorizationContext> 구현이 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에서 해당 구현을 변경했습니다.  
  
## <a name="impact"></a>영향  
 드문 경우이지만 사용자 지정 인증을 사용하는 WCF 앱은 다르게 동작할 수 있습니다.  
  
## <a name="mitigation"></a>완화  
 다음 두 가지 방법 중 하나로 이전 동작을 복원할 수 있습니다.  
  
-   4.6 이전 버전의 .NET Framework를 대상으로 사용하도록 앱을 다시 컴파일합니다. IIS 호스트 서비스의 경우 이전 버전의.NET Framework를 대상으로 하는 `<httpRuntime targetFramework="x.x" />` 요소를 사용합니다.  
  
-   다음 줄을 app.config 파일의 `<appSettings>` 섹션에 추가합니다.  
  
    ```xml  
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

