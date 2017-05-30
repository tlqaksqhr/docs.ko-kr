---
title: ".NET Framework 4.6.2의 대상 다시 지정 변경 내용 | Microsoft Docs"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes, .NET Framework
- retargeting changes, .NET Framework 4.6.2
- application compatibility
ms.assetid: 76dc6849-8210-4e41-8731-20828c98b282
caps.latest.revision: 26
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 229ccf3fa4ff1029334641da350cfd040e4b286e
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="retargeting-changes-in-the-net-framework-462"></a>.NET Framework 4.6.2의 대상 다시 지정 변경 내용
드문 경우지만 대상 다시 지정 변경 내용은 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]을 대상으로 다시 컴파일되는 앱에 영향을 줄 수 있습니다. 이러한 변경 내용은 이전 버전의 .NET Framework를 대상으로 하지만 버전 4.6.2에서 실행되는 이진 파일에 영향을 주지 않습니다. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]의 다음 영역에 대상 다시 지정 변경 내용이 포함되어 있습니다.  
  
-   [핵심](#Core)  
  
-   [WCF(Windows Communication Foundation)](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
 다음 테이블의 범위 열에는 각 변경 내용의 영향력이 지정되어 있습니다.  
  
-   주요함 다수의 앱에 영향을 주거나 코드를 대폭 수정해야 하는 중요한 변경 내용입니다. 이 범주에 속한 대상 다시 지정 변경 내용은 없습니다.  
  
-   사소함 소수의 앱에 영향을 주거나 코드를 약간만 수정해야 하는 변경 내용입니다.  
  
-   특별한 경우 일반적이지 않은 매우 특별한 시나리오의 앱에 영향을 주는 변경 내용입니다.  
  
-   투명 앱 개발자나 사용자에게 뚜렷한 영향을 주지 않는 변경 내용입니다. 이 변경 내용으로 인한 앱 수정은 필요하지 않습니다.  
  
<a name="Core"></a>   
## <a name="core"></a>핵심  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|긴 경로 지원|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터 긴 경로(최대 32,000자)가 지원되며 260자(또는 `MAX_PATH`) 경로 길이 제한이 제거되었습니다.|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱에서는 이전에 <xref:System.IO.PathTooLongException>을 throw했던 코드 경로가 더 이상 예외를 throw하지 않을 수 있습니다. 자세한 내용은 [완화: 긴 경로 지원](~/docs/framework/migration-guide/mitigation-long-path-support.md)을 참조하세요.|부|  
|경로 표준화|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터 경로가 표준화되는 방식 때문에 운영 체제가 지연되고 DOS 장치 경로에 보다 잘 액세스할 수 있게 되었습니다.|이러한 변경으로 인해 이전에는 지원되지 않던 올바른 장치 경로에 액세스할 수 있게 되었습니다. 자세한 내용은 [완화: 경로 표준화](~/docs/framework/migration-guide/mitigation-path-normalization.md)를 참조하세요.|부|  
|<xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> 및 <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName>|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터 이전에 지원되지 않던 경로를 지원하도록 여러 가지 변경이 수행되었습니다(길이 및 형식 측면에서). 특히 적절한 드라이브 구분 기호 구문(콜론)에 대한 확인이 좀 더 정확해졌습니다.|이러한 변경으로 인해 이러한 두 메서드가 이전에 지원했던 일부 URI 경로가 차단됩니다. 자세한 내용은 [완화: 경로 표준화 검사](~/docs/framework/migration-guide/mitigation-path-colon-checks.md)를 참조하세요.|Microsoft Edge|  
|<xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> 생성자|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]부터는 <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> 메서드 호출을 통해 생성되는 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> 속성이 새 <xref:System.Security.Claims.ClaimsIdentity> 인스턴스입니다. 이전 버전의 .NET Framework에서 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A>는 기존 참조입니다.|<xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> 속성을 생성자 <xref:System.Security.Principal.IIdentity>의 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> 속성과 비교하면 다른 결과가 반환되는 경우도 있습니다.<br /><br /> 자세한 내용은 [완화: ClaimsIdentity 생성자](~/docs/framework/migration-guide/mitigation-claimsidentity-constructor.md)를 참조하세요.|Microsoft Edge|  
|<xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor%2A?displayProperty=fullName>|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터는 <xref:System.Security.Cryptography.AesCryptoServiceProvider> 암호 해독기가 재사용 가능 변환을 제공합니다.   <xref:System.Security.Cryptography.ICryptoTransform.TransformFinalBlock%2A>을 호출하고 나면 변환이 다시 초기화되므로 재사용할 수 있습니다.<br /><br /> 이전 버전 .NET Framework를 대상으로 하는 앱의 경우 <xref:System.Security.Cryptography.ICryptoTransform.TransformFinalBlock%2A>을 호출한 후에 <xref:System.Security.Cryptography.ICryptoTransform.TransformBlock%2A>을 호출하여 암호 해독기를 재사용하려고 하면 <xref:System.Security.Cryptography.CryptographicException>이 throw되거나 손상된 데이터가 생성됩니다.|이것은 예상되는 동작이므로 영향을 최소화할 수 있습니다.<br /><br /> 이전 동작에 의존하는 응용 프로그램은 응용 프로그램 구성 파일의 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 옵트아웃(opt out)할 수 있습니다.<br /><br /> `<runtime>    <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true"/> </runtime>`<br /><br /> 또한 이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]부터 시작하는 .NET Framework 버전에서 실행되는 응용 프로그램은 응용 프로그램 구성 파일의 [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 옵트인(opt in)할 수 있습니다.<br /><br /> `<runtime>    <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false"/> </runtime>`|부|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>WCF(Windows Communication Foundation)  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|CNG를 사용하여 저장한 인증서에 대한 WCF 전송 보안 지원|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터, WCF 전송 보안에서 Windows 암호화 라이브러리(CNG)를 사용하여 저장한 인증서를 지원합니다. 이 지원은 지수 길이가 32비트 이하인 공개 키로 인증서로 제한됩니다. 응용 프로그램이 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 경우 이 기능은 기본적으로 켜집니다.<br /><br /> 이전 버전의 .NET Framework에서 CSG 키 저장소 공급자와 함께 X509 인증서를 사용하려고 하면 예외가 throw됩니다.|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 및 이전 버전을 대상으로 하지만 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]에서 실행 중인 앱은 app.config 또는 web.config 파일의 runtime 섹션에 다음 줄을 추가하여 CNG 인증서에 대한 지원을 사용하도록 설정할 수 있습니다.<br /><br /> `<AppContextSwitchOverrides     value="Switch.System.ServiceModel.DisableCngCertificates=false" />`<br /><br /> 다음 코드를 사용하여 프로그래밍 방식으로 이 작업을 수행할 수도 있습니다.<br /><br /> `private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificate"; AppContext.SetSwitch(disableCngCertificates, false);`<br /><br /> `Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates" AppContext.SetSwitch(disableCngCertificates, False)`<br /><br /> 이러한 변경으로 인해 CNG 인증서와의 보안 통신을 시작하려는 시도에 종속되는 예외 처리 코드를 더 이상 실행할 수 없습니다.|부|  
  
<a name="WinForms"></a>   
## <a name="windows-forms"></a>Windows Forms  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|<xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>, `System.ComponentModel.EventDescriptor.Equals` 및 `System.ComponentModel.PropertyDescriptor.Equals`|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터는 기본 클래스 <xref:System.ComponentModel.MemberDescriptor.Equals%2A> 메서드의 구현이 변경되었습니다.|같음 테스트는 이제 예상된 결과를 생성하기 때문에 이러한 변경은 거의 영향을 미치지 않습니다.<br /><br /> 그러나 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하며 이전 동작에 의존하는 앱은 이 변경을 옵트아웃(opt out)할 수 있습니다. 마찬가지로 이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]에서 실행되는 앱은 이러한 변경을 opt in(옵트인)할 수 있습니다. 자세한 내용은 [완화: MemberDescriptor.Equals](~/docs/framework/migration-guide/mitigation-memberdescriptor-equals.md)를 참조하세요.|Microsoft Edge|  
  
## <a name="see-also"></a>참고 항목  
 [4.6.2의 응용 프로그램 호환성](~/docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)
