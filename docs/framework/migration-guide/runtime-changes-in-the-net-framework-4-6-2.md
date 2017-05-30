---
title: ".NET Framework 4.6.2의 런타임 변경 내용 | Microsoft Docs"
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
- runtime changes, .NET Framework
- runtime changes, .NET Framework 4.6.2
- application compatibility
ms.assetid: 23bf3a87-6fa1-4b5e-b92c-a39867a06e7f
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: da809955776b5a5cd3776898ecc4c97db74ceb0e
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="runtime-changes-in-the-net-framework-462"></a>.NET Framework 4.6.2의 런타임 변경 내용
드문 경우지만 런타임 변경 내용이 이전 버전의 .NET Framework를 대상으로 하지만 이후 버전의 .NET Framework 런타임에서 실행되는 기존 앱에 영향을 줄 수 있습니다. 서로 다른 .NET Framework 런타임 환경에서 실행되는 응용 프로그램 간의 동작 차이도 포함됩니다. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]의 다음 영역에 이러한 변경 내용이 포함되어 있습니다.  
  
-   [핵심](#Core)  
  
-   [ASP.NET](#ASP)

-   [Data](#Data)  
  
-   [WCF(Windows Communication Foundation)](#WCF)  
  
-   [WPF(Windows Presentation Foundation)](#WPF)  
  
-   [XML 서명 및 유효성 검사](#XML)  
  
<a name="Core"></a>   
## <a name="core"></a>핵심  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|<xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName><br /><br /> <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory%2A?displayProperty=fullName>|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]의 문자 범주는 유니코드 버전 8.0을 기준으로 합니다. .NET Framework 버전 4.5 ~ 4.6.1에서는 통해 유니코드 버전 6.3을 기준으로 유니코드 문자를 분류합니다.<br /><br /> 문자 비교 및 정렬은 이러한 변경에 의해 영향을 받지 않습니다. 자세한 내용은 <xref:System.String> 클래스 항목의 "문자열과 유니코드 표준" 섹션을 참조하세요.|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]의 문자 범주가 이전 버전의 .NET Framework의 문자 범주와 일치하지 않을 수 있습니다. 이러한 변경은 주로 체로키어 음절 및 신타이 루에 모음 기호와 성조 표시에 영향을 미칩니다.<br /><br /> 이 변경은 해결하기 위해서는 코드를 검토하고 하드 코드된 유니코드 문자 범주에 의존하는 논리를 제거하거나 변경해야 합니다.|부|  
|<xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=fullName>, <xref:System.Security.Cryptography.RSACng.ImportParameters%2A?displayProperty=fullName>, <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A?displayProperty=fullName>, <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=fullName>|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]부터 이러한 메서드는 RSA 인증서에 대한 비표준 키 크기를 갖는 키에 액세스할 수 있습니다. [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 이하 버전에서는 이러한 키에 액세스하려고 하면 <xref:System.Security.Cryptography.CryptographicException>이 throw됩니다.|비표준 키 크기를 사용할 때 예외 처리 논리가 <xref:System.Security.Cryptography.CryptographicException>을 사용하는 경우에는 해당 논리를 제거해야 합니다.|Microsoft Edge|  
|<xref:System.Security.Cryptography.RSACng.VerifyHash%2A?displayProperty=fullName>|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]부터 이 메서드는 서명 자체의 형식이 잘못된 경우 `false`를 반환합니다. 이제는 확인 실패가 있을 때 `false`를 반환합니다.<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 및 4.6.1에서는 서명 자체의 형식이 잘못된 경우 메서드가 <xref:System.Security.Cryptography.CryptographicException>을 throw합니다.|유효성 검사가 실패하고 이 메서드가 `false`를 반환하는 경우에는 실행 시 <xref:System.Security.Cryptography.CryptographicException>을 사용하는 코드를 대신 실행해야 합니다.|부|  
  
## <a name="a-nameasp--aspnet"></a><a name="ASP" /> ASP.NET

|기능|변경|영향|범위| 
|-------------|------------|------------|-----------|  
| <xref:System.Web.HttpRuntime.AppDomainApopPath%2A> | .NET framework 4.6.2에서는 null 문자가 포함된 <xref:System.Web.HttpRuntime.AppDomainAppPath%2A> 값을 검색하면 런타임에서 <xref:System.NullReferenceException>이 throw됩니다. .NET Framework 4.6.1 이하 버전에서는 <xref:System.ArgumentNullException>이 throw됩니다.  | 이러한 변경에 대처하기 위해 다음을 수행할 수 있습니다. <br/> - 응용 프로그램을 .NET Framework 4.6.2에서 실행 중인 경우 <xref:System.NullReferenceException>을 처리합니다. <br /> - .NET Framework 4.7로 업그레이드합니다. 그러면 이전 동작이 복원되고 <xref:System.ArgumentNullException>이 throw됩니다. | Microsoft Edge |

<a name="Data"></a>   
## <a name="data"></a>데이터  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|Azure SQL 데이터베이스에 대한 연결 풀 차단 기간|알려진 Azure SQL 데이터베이스에 대한 연결 열기 요청의 경우 연결 풀 차단 기간이 제거됩니다.|연결 열기 요청 다시 시도는 일시적인 연결 오류 발생 직후에 수행됩니다. 자세한 내용은 [완화: 풀 차단 기간](~/docs/framework/migration-guide/mitigation-pool-blocking-period.md)을 참조하세요.|부|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>WCF(Windows Communication Foundation)  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=fullName> <br /> <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=fullName>|전송 보안 및 자격 증명 유형의 인증서를 지원하는 NetTcp를 사용할 경우 SSL 3 프로토콜은 더 이상 보안 연결을 협상하는 데 사용되는 기본 프로토콜이 아닙니다.|대부분의 경우 TLS 1.0이 항상 NetTcp에 대한 프로토콜 목록에 포함되어 있으므로 기존 앱에는 영향을 주지 않습니다. 모든 기존 클라이언트에서는 TLS 1.0 이상을 사용하여 연결을 협상할 수 있습니다.<br /><br /> Ssl3가 필요한 경우 다음 구성 메커니즘 중 하나를 사용하여 협상된 프로토콜 목록에 Ssl3를 추가할 수 있습니다.<br /><br /> -   <xref:System.ServiceModel.TcpTransportSecurity?displayProperty=fullName> 속성<br />-   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=fullName> 속성<br />-   [\<netTcpBinding>](~/docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)의 [\<transport>](~/docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md) 섹션<br />-   [\<customBinding>](~/docs/framework/configure-apps/file-schema/wcf/custombinding.md)의 [\<sslStreamSecurity>](~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) 섹션|Microsoft Edge|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>WPF(Windows Presentation Foundation)  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|<xref:System.Windows.Controls.TextBlock> 컨트롤 부모의 `IsEnabled` 속성|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]부터 <xref:System.Windows.Controls.TextBlock> 컨트롤 부모의 `IsEnabled` 속성을 변경하면 <xref:System.Windows.Controls.TextBlock> 컨트롤의 자식 컨트롤(예: 하이퍼링크 및 단추)에 영향을 미칩니다.<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 이하 버전의 .NET Framework에서는 <xref:System.Windows.Controls.TextBlock> 내의 컨트롤이 <xref:System.Windows.Controls.TextBlock> 부모의 `IsEnabled` 속성 상태를 항상 반영하지는 않았습니다.|이 변경은 <xref:System.Windows.Controls.TextBlock> 컨트롤 내부에 있는 컨트롤의 정상적인 동작을 따릅니다.|부|  
|가로 스크롤, 가상화 및 <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName>|주 스크롤 방향의 직각 방향으로 자체 가상화를 수행하는 <xref:System.Windows.Controls.ItemsControl>에 대한 스크롤 작업의 동작이 변경되었습니다.|이 변경으로 인해 최종 사용자가 오프셋을 더욱 쉽게 예측할 수 있는 직관적인 환경이 생성됩니다. 하지만 가로 스크롤 이후 <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName>의 정확한 값에 따라 동작이 달라지는 앱에 영향을 줄 수 있습니다. 자세한 내용은 [완화: 가로 스크롤 및 가상화](~/docs/framework/migration-guide/mitigation-horizontal-scrolling-and-virtualization.md)를 참조하세요.|부|  
|WPF 맞춤법 검사기(<xref:System.Windows.Controls.SpellCheck?displayProperty=fullName> 클래스)|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서 실행될 때 WPF 맞춤법 검사에서 확인된 다음과 같은 세 가지 문제가 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]에서는 해결되었습니다.<br /><br /> -   [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서 [ISpellChecker](https://msdn.microsoft.com/library/windows/desktop/hh869767\(v=vs.85\).aspx) 또는 [ISpellCheckerFactory](https://msdn.microsoft.com/library/windows/desktop/hh869770\(v=vs.85\).aspx) 메서드를 호출할 때 맞춤법 검사기가 경우에 따라 <xref:System.Runtime.InteropServices.COMException>을 throw합니다. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]에서는 이러한 예외가 제거되었습니다.<br />-   [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서 맞춤법 검사기가 독일어의 "Hausnummer"와 같은 복합어의 맞춤법 오류를 제대로 식별하지 못합니다. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]에서 맞춤법 검사기는 복합어를 올바르게 처리합니다.<br />-   [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서 "다른 사용자로 실행"을 사용하여 응용 프로그램을 시작할 때 맞춤법 검사기가 <xref:System.UnauthorizedAccessException>을 throw합니다. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]에서는 이 시나리오가 지원되지 않으며, 맞춤법 검사기는 사용되지 않도록 자동으로 설정됩니다.|이러한 변경 내용은 맞춤법 검사기의 견고성을 향상시킵니다.  또한 응용 프로그램 코드가 throw되는 예외에 의존하지 않는 한, 응용 프로그램에도 나쁜 영향을 주지 않습니다.|Microsoft Edge|  
| [DataGridCellsPanel.BringIndexIntoView](xref:System.Windows.Controls.DataGridCellsPanel.BringIndexInfoView(System.Int32)) 메서드 | NET Framework 4.6.2에서 **BringIndexIntoView** 메서드는 열 가상화가 사용되도록 설정되어 있으나 열 너비를 결정되지 않았을 때 비동기적으로 실행됩니다. 그러나 비동기 작업이 완료된 후에 열이 제거되면 [ArgumentOutOfRangeException](xref:System.ArgumentOutOfRangeException)이 발생할 수 있습니다.<br/></br>.NET Framework 4.7 부터는 이 시나리오에서 더 이상 예외가 throw되지 않습니다. | 예외 발생을 방지하기 위해 다음 중 하나를 수행할 수 있습니다. <br/> - .NET Framework 4.7로 업그레이드 <br/> 1 .NET Framework 4.6.2에 대한 최신 서비스 패치를 설치합니다. <br/> - [DataGrid.ScrollIntoView](xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)) 메서드에 대한 비동기 응답이 완료될 때까지 열이 제거되지 않도록 합니다. | Microsoft Edge | 
  
<a name="XML"></a>   
## <a name="signed-xml-verification-requirements"></a>서명된 XML 확인 요구 사항  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|<xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> 및 <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName>|외부 리소스 로드가 사용되지 않도록 설정되고 모호한 ID-대상은 잘못된 것으로 간주됩니다.|다음을 비롯한 여러 경우에서 예외가 throw됩니다.<br /><br /> -   ID 특성으로 요소를 식별하고 동일한 식별자를 사용하여 두 번째 요소 정의<br />-   올바른 `NCName` 값이 아닌 식별자 정의<br />-   외부 URI 참조<br /><br /> 다음과 같은 문서에 대해 <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A?displayProperty=fullName>는 항상 `false`를 반환합니다.<br /><br /> -   XPath 참조 변환을 사용하는 문서<br />-   XSLT 참조 변환을 사용하는 문서<br /><br /> 문서 수신 <xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=fullName> 및 <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>과 <xref:System.Security.Cryptography.Xml.Transform?displayProperty=fullName>에서 파생된 형식의 사용을 검토해야 합니다. 문서 수신기가 이러한 사용을 처리하지 못할 수도 있기 때문입니다.<br /><br /> 자세한 내용은 [보안 업데이트 3141780을 적용한 후에 .NET Framework 응용 프로그램에서 SignedXml을 포함하는 파일을 처리하는 동안 예외 오류 또는 예기치 않은 실패가 발생함](https://support.microsoft.com/en-us/kb/3148821)을 참조하세요.|부|  
  
## <a name="see-also"></a>참고 항목  
 [4.6.2의 응용 프로그램 호환성](~/docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)
