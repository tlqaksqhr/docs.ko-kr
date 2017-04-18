---
title: ".NET Framework 4.6의 변경 내용 대상 변경 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fa849255-f90f-4bf1-b0ff-b173c12110d7
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# .NET Framework 4.6의 변경 내용 대상 변경
드문 경우지만 대상 다시 지정 변경 내용은 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]을 대상으로 다시 컴파일되는 앱에 영향을 줄 수 있습니다. 달리 지정된 경우가 아니면 이러한 변경 내용은 이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에서 실행되는 이진 파일에 영향을 주지 않습니다.  
  
 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]의 다음 영역에 대상 다시 지정 변경 내용이 포함되어 있습니다.  
  
-   [ASP.NET](#ASP)  
  
-   [네트워킹](#Net)  
  
-   [WCF\(Windows Communications Foundation\)](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
-   [WPF\(Windows Presentation Foundation\)](#WPF)  
  
-   [XML](#XML)  
  
<a name="ASP"></a>   
## ASP.NET  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|<xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName>의 `tagKey` 값을 사용하는 <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName>|HTML 표준에 맞게 <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName> 메서드가 이제는 <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName>를 HTML 응답의 닫지 않는 태그로 렌더링합니다.|BR 태그가 이제는 줄 바꿈 하나를 생성합니다. 이전에는 줄 바꿈 두 개를 생성했습니다.<br /><br /> `<BR>` 태그에 종속되어 줄 바꿈 두 개를 생성하는 앱은 추가 호출을 <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName> 인수를 사용하는 <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName> 메서드에 추가하여 이전 동작을 복원할 수 있습니다.|사소함|  
  
<a name="Net"></a>   
## 네트워킹  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|<xref:System.Net.ServicePointManager?displayProperty=fullName> 및 <xref:System.Net.Security.SslStream?displayProperty=fullName>|.NET Framework 4.6을 대상으로 하는 앱부터 <xref:System.Net.ServicePointManager?displayProperty=fullName> 및 <xref:System.Net.Security.SslStream?displayProperty=fullName> 클래스에서 Tls1.0, Tls1.1 또는 Tls 1.2 프로토콜 중 하나를 사용할 수 있습니다.<br /><br /> NET Framework 4.6에서 실행되더라도 NET Framework의 이전 버전을 대상으로 하는 앱은 영향을 받지 않습니다.|이 변경 사항은 .NET Framework 4.6을 대상으로 하고 HTTPS 서버 또는 <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> 및 <xref:System.Net.Security.SslStream> 형식 중 하나를 사용하는 소켓 서버와 통신하는 데 SSL을 사용하는 모든 앱에 영향을 미칩니다.  자세한 내용은 [완화: TLS 프로토콜](../../../docs/framework/migration-guide/mitigation-tls-protocols.md)을 참조하세요.|사소함|  
  
<a name="WCF"></a>   
## WCF\(Windows Communications Foundation\)  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%2A?displayProperty=fullName>|`null` `authorizationPolicies` 인수가 있는 <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29>에 대한 호출에서 반환한 <xref:System.IdentityModel.Policy.AuthorizationContext> 구현이 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에서 해당 구현을 변경했습니다.|드문 경우이지만 사용자 지정 인증을 사용하는 WCF 앱은 다르게 동작할 수 있습니다. 이전 동작이 필요한 경우 [완화: 기본 AuthorizationContext](../../../docs/framework/migration-guide/mitigation-default-authorizationcontext.md)를 참조하세요.|사소함|  
  
<a name="WinForms"></a>   
## Windows Forms  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName>|.NET Framework 4.6을 대상으로 하는 앱부터 <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> 메서드는 PNG 프레임이 있는 아이콘을 <xref:System.Drawing.Bitmap> 개체로 변환합니다.<br /><br /> .NET Framework 4.5.2 및 이전 버전을 대상으로 하는 앱에서는 <xref:System.Drawing.Icon> 개체에 PNG 프레임이 있는 경우 <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> 메서드가 <xref:System.ArgumentOutOfRangeException> 예외를 throw합니다.|이러한 변경은 .NET Framework 4.6을 대상으로 다시 컴파일되고 <xref:System.Drawing.Icon> 개체에 PNG 프레임이 있는 경우 throw되는 <xref:System.ArgumentOutOfRangeException> 예외에 특별한 처리를 제공하는 앱에 영향을 줍니다. 이 동작을 원치 않는 경우 구성 스위치가 이전 동작을 복원합니다. 자세한 내용은 [완화: 아이콘 개체의 PNG 프레임](../../../docs/framework/migration-guide/mitigation-png-frames-in-icon-objects.md)을 참조하십시오.|사소함|  
  
<a name="WPF"></a>   
## WPF\(Windows Presentation Foundation\)  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|높은 DPI에서 레이아웃 반올림|여백이 반올림되는 방식과 그 안의 테두리 및 배경이 변경되었습니다.|WPF 컨트롤의 레이아웃은 약간 변경될 수 있습니다. 자세한 내용은 [완화: WPF 레이아웃](../../../docs/framework/migration-guide/mitigation-wpf-layout.md)을 참조하십시오.|사소함|  
  
<a name="XML"></a>   
## XML  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|XSD 스키마 유효성 검사|.NET Framework 4.6부터 복합 키를 사용하고 한 개의 키가 비어 있는 경우 XSD 스키마 유효성 검사가 고유한 제약 조건 위반을 검색합니다.|[완화: XML 스키마 유효성 검사](../../../docs/framework/migration-guide/mitigation-xml-schema-validation.md)을 참조하세요.|사소함|  
|<xref:System.Xml.XmlWriter>|.NET Framework 4.5.2 또는 이전 버전을 대상으로 하는 앱의 경우 예외 대체\(fallback\) 처리를 사용하여 잘못된 서로게이트 쌍을 작성해도 항상 예외가 발생하지는 않습니다.<br /><br /> [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]를 대상으로 하는 앱의 경우 잘못된 서로게이트 쌍을 작성하려고 하면 <xref:System.ArgumentException> 예외가 발생합니다.|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]를 대상으로 하도록 다시 컴파일된 앱이 잘못된 서로게이트 쌍을 작성하는 경우 이전과 달리 예외가 발생합니다.|가장자리|