---
title: "완화: ClaimsIdentity 생성자"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 946903f1-0fbf-4f67-805b-1eb48352024d
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a50cbd69aa1f2c72adc9fc4d10a070f5faa0cf54
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-claimsidentity-constructor"></a>완화: ClaimsIdentity 생성자
[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]부터 <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> 생성자가 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> 속성을 설정하는 방법이 변경됩니다. <xref:System.Security.Principal.IIdentity> 인수가 <xref:System.Security.Claims.ClaimsIdentity> 개체이고 해당 <xref:System.Security.Claims.ClaimsIdentity> 개체의 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> 속성이 `null`이 아닌 경우 <xref:System.Security.Claims.ClaimsIdentity.Clone%2A?displayProperty=fullName> 메서드를 사용하여 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> 속성이 연결됩니다. [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서는 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> 속성이 기존 참조로 연결됩니다.  
  
## <a name="impact"></a>영향  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]부터 새 <xref:System.Security.Claims.ClaimsIdentity> 개체의 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> 속성은 생성자의 <xref:System.Security.Principal.IIdentity> 인수의 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> 속성과 동일하지 않습니다. [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 및 이전 버전에서는 같습니다.  
  
## <a name="mitigation"></a>완화  
 이 동작을 원치 않을 경우 응용 프로그램 구성 파일에서 `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` 스위치를 `true`로 설정하여 이전 동작을 복원할 수 있습니다. 이렇게 하려면 web.config 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음을 추가해야 합니다.  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

