---
title: "완화: X509CertificateClaimSet.FindClaims 메서드 | Microsoft 문서"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee356e3b-f932-48f5-875a-5e42340bee63
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c234d6ddeda50dfefff8c49a2e14d623cdd8d861
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-x509certificateclaimsetfindclaims-method"></a>완화: X509CertificateClaimSet.FindClaims 메서드
[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]이 대상인 응용 프로그램으로 시작하면 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> 메서드는 `claimType` 인수를 SAN 필드에 있는 모든 DNS 항목과 일치하도록 시도합니다.  
  
## <a name="impact"></a>영향  
 이 변경은 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]로 시작하는 .NET Framework 버전을 대상으로 하는 응용 프로그램에만 영향을 줍니다.  
  
 .NET Framework의 이전 버전이 대상인 응용 프로그램의 경우,  <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName> 메서드는 `claimType` 인수가 마지막 DNS 항목에만 일치하도록 시도합니다.  
  
## <a name="mitigation"></a>완화  
 이러한 변경을 원치 않는 경우 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]로 시작하는 .NET Framework 버전을 대상으로 하는 앱은 앱 구성 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 사용하지 않을 수 있습니다.  
  
```xml  
  
<runtime>  
   <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=true" />   
</runtime>  
  
```  
  
 또한 이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 및 이후 버전에서 실행되는 앱은 앱 구성 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 옵트인(opt in)할 수 있습니다.  
  
```xml  
  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IdentityModel.DisableMultipleDNSEntriesInSANCertificate=false" />   
</runtime>  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)
