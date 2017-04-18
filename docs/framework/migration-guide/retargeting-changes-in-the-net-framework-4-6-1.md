---
title: ".NET Framework 4.6.1의 변경 내용 대상 변경 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 411ad548-30fa-43da-8716-10eccfc839e6
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# .NET Framework 4.6.1의 변경 내용 대상 변경
드문 경우지만 대상 다시 지정 변경 내용은 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 다시 컴파일되는 앱에 영향을 줄 수 있습니다. 달리 지정된 경우가 아니면 이러한 변경 내용은 이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서 실행되는 이진 파일에 영향을 주지 않습니다.  
  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]의 다음 영역에 대상 다시 지정 변경 내용이 포함되어 있습니다.  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
<a name="WCF"></a>   
## Windows Communication Foundation  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName><br /><br /> \(<xref:System.IdentityModel.Claims> 네임스페이스\)|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 앱에서 X509 클레임 집합이 해당 SAN 필드에 여러 DNS 항목이 있는 인증서로부터 초기화되는 경우 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A> 메서드가 `claimType` 인수를 모든 DNS 항목과 일치시키려고 합니다.<br /><br /> 이전 버전의 .NET Framework를 대상으로 하는 앱의 경우에는 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A> 메서드가 `claimType` 인수를 마지막 DNS 항목만 일치시키려고 합니다.|이러한 변경은 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 모든 앱에 영향을 줍니다. 이전 버전의 .NET Framework를 대상으로 하는 앱은 영향을 받지 않습니다.<br /><br /> 그러나 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 앱은 이 동작을 옵트아웃\(opt out\)할 수 있습니다. 또한 이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서 실행되는 앱은 이 동작을 사용하지 않을 수 있습니다. 자세한 내용은 [완화: X509CertificiateClaimSet.FindClaims 메서드](../../../docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md)을 참조하세요.|사소함|  
  
<a name="WinForms"></a>   
## Windows Forms  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|<xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> 메서드\(<xref:System.Windows.Forms> 네임스페이스\)|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 Windows Forms 앱에서 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> 구현이 다음과 같은 경우 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> 메서드가 호출될 때 사용자 지정 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> 구현이 메시지를 안전하게 필터링할 수 있습니다.<br /><br /> <ul><li>다음 중 하나 또는 두 가지 모두를 수행합니다.<br /><br /> <ul><li><xref:System.Windows.Forms.Application.AddMessageFilter%2A> 메서드를 호출하여 메시지 필터를 추가합니다.</li><li><xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> 메서드를 호출하여 메시지 필터를 제거합니다. 메서드를 재정의합니다.</li></ul></li><li>**또한** <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName> 메서드를 호출하여 메시지를 펌핑합니다.</li></ul><br /> 일부 경우 이전 버전의 .NET Framework를 대상으로 하는 Windows Forms 앱에서 이러한 구현은 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> 메서드가 호출될 때 <xref:System.IndexOutOfRangeException> 예외를 throw합니다.|이러한 변경은 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 모든 앱에 영향을 줍니다. 이전 버전의 .NET Framework를 대상으로 하는 앱은 영향을 받지 않습니다.<br /><br /> 그러나 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 앱은 이 동작을 옵트아웃\(opt out\)할 수 있습니다. 또한 이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서 실행되는 앱은 이 동작을 사용하지 않을 수 있습니다. 자세한 내용은 [완화: 사용자 지정 IMessageFilter.PreFilterMessage 구현](../../../docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)을 참조하세요.|가장자리|  
  
## 참고 항목  
 [4.6.1의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)