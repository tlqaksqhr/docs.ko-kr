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
# <a name="mitigation-claimsidentity-constructor"></a><span data-ttu-id="918f8-102">완화: ClaimsIdentity 생성자</span><span class="sxs-lookup"><span data-stu-id="918f8-102">Mitigation: ClaimsIdentity Constructor</span></span>
<span data-ttu-id="918f8-103">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]부터 <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> 생성자가 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> 속성을 설정하는 방법이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="918f8-103">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], there is change in how the <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> constructor sets the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property.</span></span> <span data-ttu-id="918f8-104"><xref:System.Security.Principal.IIdentity> 인수가 <xref:System.Security.Claims.ClaimsIdentity> 개체이고 해당 <xref:System.Security.Claims.ClaimsIdentity> 개체의 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> 속성이 `null`이 아닌 경우 <xref:System.Security.Claims.ClaimsIdentity.Clone%2A?displayProperty=fullName> 메서드를 사용하여 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> 속성이 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="918f8-104">If the <xref:System.Security.Principal.IIdentity> argument is a <xref:System.Security.Claims.ClaimsIdentity> object, and the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property of that <xref:System.Security.Claims.ClaimsIdentity> object is not `null`, the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property is attached by using the <xref:System.Security.Claims.ClaimsIdentity.Clone%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="918f8-105">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서는 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> 속성이 기존 참조로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="918f8-105">In the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property is attached as a  existing reference.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="918f8-106">영향</span><span class="sxs-lookup"><span data-stu-id="918f8-106">Impact</span></span>  
 <span data-ttu-id="918f8-107">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]부터 새 <xref:System.Security.Claims.ClaimsIdentity> 개체의 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> 속성은 생성자의 <xref:System.Security.Principal.IIdentity> 인수의 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> 속성과 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="918f8-107">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property of the new <xref:System.Security.Claims.ClaimsIdentity> object is not equal to the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property of the constructor's <xref:System.Security.Principal.IIdentity> argument.</span></span> <span data-ttu-id="918f8-108">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 및 이전 버전에서는 같습니다.</span><span class="sxs-lookup"><span data-stu-id="918f8-108">In the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions, it is equal.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="918f8-109">완화</span><span class="sxs-lookup"><span data-stu-id="918f8-109">Mitigation</span></span>  
 <span data-ttu-id="918f8-110">이 동작을 원치 않을 경우 응용 프로그램 구성 파일에서 `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` 스위치를 `true`로 설정하여 이전 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="918f8-110">If this behavior is undesirable, you can restore the previous behavior by setting the `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` switch in your application configuration file to `true`.</span></span> <span data-ttu-id="918f8-111">이렇게 하려면 web.config 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="918f8-111">This requires that you add the following to  the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your web.config file:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="918f8-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="918f8-112">See Also</span></span>  
 [<span data-ttu-id="918f8-113">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="918f8-113">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

