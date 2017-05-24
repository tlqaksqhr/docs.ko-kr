---
title: ".NET Framework 4.6.1의 대상 다시 지정 변경 내용 | Microsoft 문서"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes, .NET Framework
- retargeting changes, .NET Framework 4.6.1
- application compatibility
ms.assetid: 411ad548-30fa-43da-8716-10eccfc839e6
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0adc4a6cae566b6a15c5fa492620abb74b47335b
ms.lasthandoff: 04/18/2017

---
# <a name="retargeting-changes-in-the-net-framework-461"></a>.NET Framework 4.6.1의 변경 내용 대상 변경
드문 경우지만 대상 다시 지정 변경 내용은 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 다시 컴파일되는 앱에 영향을 줄 수 있습니다. 달리 지정된 경우가 아니면 이러한 변경 내용은 이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서 실행되는 이진 파일에 영향을 주지 않습니다.  
  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]의 다음 영역에 대상 다시 지정 변경 내용이 포함되어 있습니다.  
  
-   [핵심](#Core)  
  
-   [코드 계약](#Contracts)  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
<a name="Core"></a>   
## <a name="core"></a>핵심  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|<xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName>|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 및 이후 버전을 대상으로 하는 앱의 경우 <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName> 메서드의 오버로드로 생성된 <xref:System.IO.Compression.ZipArchiveEntry> 개체의 <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A> 속성에서 경로 구분 기호 문자가 백슬래시("\\")에서 슬래시("/")로 변경되었습니다.|이 변경으로 인해 .NET 구현은 [.ZIP 파일 형식 사양](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT)의 섹션 4.4.17.1과 일치하게 되고 비 Windows 시스템에서.ZIP 아카이브의 압축이 풀리게 됩니다.<br /><br /> 그러나 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 및 이후 버전을 대상으로 하는 앱은 이 동작을 옵트아웃(opt out)할 수 있습니다. 자세한 내용은 [완화: ZipArchiveEntry.FullName 경로 구분 기호](../../../docs/framework/migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md)를 참조하십시오.|Microsoft Edge|  
  
<a name="Contracts"></a>   
## <a name="code-contracts"></a>코드 계약  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|<xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=fullName> 및 <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=fullName>, <xref:System.String.IsNullOrEmpty%2A?displayProperty=fullName>에 대한 호출|.NET Framework 4.6.1을 대상으로 하는 앱의 경우 재작성기에서 CC1036 컴파일러 경고 "메서드에서 [Pure] 없이 'System.String.IsNullOrWhiteSpace(System.String)' 메서드에 대한 호출이 감지됨..."을 내보냅니다.|이는 컴파일러 오류가 아닌 컴파일러 경고입니다.<br /><br /> 이 동작에서는 [GitHub 문제 #339](https://github.com/Microsoft/CodeContracts/issues/339)가 해결되었습니다. 이 경고를 제거하려면 [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md)에서 코드 계약 도구에 대한 소스 코드를 다운로드 및 컴파일할 수 있습니다. 다운로드 정보는 페이지 하단에서 찾을 수 있습니다.|사소함|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation"></a>Windows Communication Foundation  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName><br /><br /> (<xref:System.IdentityModel.Claims> namespace)|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 앱에서 X509 클레임 집합이 해당 SAN 필드에 여러 DNS 항목이 있는 인증서로부터 초기화되는 경우 <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A> 메서드가 `claimType` 인수를 모든 DNS 항목과 일치시키려고 합니다.<br /><br /> 이전 버전의 .NET Framework를 대상으로 하는 앱의 경우, <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A> 메서드는 `claimType` 인수가 마지막 DNS 항목에만 일치하도록 시도합니다.|이러한 변경은 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 모든 앱에 영향을 줍니다. 이전 버전의 .NET Framework를 대상으로 하는 앱은 영향을 받지 않습니다.<br /><br /> 그러나 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 앱은 이 동작을 옵트아웃(opt out)할 수 있습니다. 또한 이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서 실행되는 앱은 이 동작을 사용하지 않을 수 있습니다. 자세한 내용은 [완화: X509CertificateClaimSet.FindClaims 메서드](../../../docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md)를 참조하십시오.|사소함|  
  
<a name="WinForms"></a>   
## <a name="windows-forms"></a>Windows Forms  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|<xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> 메서드(<xref:System.Windows.Forms> 네임스페이스)|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 Windows Forms 앱에서 사용자 지정 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> 구현은 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> 구현이 다음을 수행하는 경우 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> 메서드가 호출될 때 안전하게 메시지를 필터링할 수 있습니다.<br /><br /> <ul><li>다음 중 하나 또는 두 가지 모두를 수행합니다.<br /><br /> <ul><li><xref:System.Windows.Forms.Application.AddMessageFilter%2A> 메서드를 호출하여 메시지 필터를 추가합니다.</li><li><xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> 메서드를 호출하여 메시지 필터를 제거합니다. 메서드를 재정의합니다.</li></ul></li><li>**또한** <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName> 메서드를 호출하여 메시지를 펌핑합니다.</li></ul><br /> 경우에 따라 이전 버전의 .NET Framework를 대상으로 하는 Windows Forms 앱의 이러한 구현은 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> 메서드가 호출될 때 <xref:System.IndexOutOfRangeException> 예외를 throw합니다.|이러한 변경은 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 모든 앱에 영향을 줍니다. 이전 버전의 .NET Framework를 대상으로 하는 앱은 영향을 받지 않습니다.<br /><br /> 그러나 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]을 대상으로 하는 앱은 이 동작을 옵트아웃(opt out)할 수 있습니다. 또한 이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서 실행되는 앱은 이 동작을 사용하지 않을 수 있습니다. 자세한 내용은 [완화: 사용자 지정 IMessageFilter.PreFilterMessage 구현](../../../docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)을 참조하십시오.|Microsoft Edge|  
  
## <a name="see-also"></a>참고 항목  
 [4.6.1의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
