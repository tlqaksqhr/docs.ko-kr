---
title: ".NET Framework 4.7의 대상 다시 지정 변경 내용 | Microsoft Docs"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes,.NET Framework
- retargeting changes,.NET Framework 4.7
- application compatibility
ms.assetid: d98bf1e3-0017-4933-8e7b-191ac3542fcc
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2881049ee490bf0abdd8b2f0651ca3703ccae76a
ms.lasthandoff: 04/18/2017

---
# <a name="retargeting-changes-in-the-net-framework-47"></a>.NET Framework 4.7의 변경 내용 대상 변경

드문 경우지만 대상 다시 지정 변경 내용은 .NET Framework 4.7을 대상으로 다시 컴파일되는 앱에 영향을 줄 수 있습니다. 이러한 변경 내용은 이전 버전의 .NET Framework를 대상으로 하지만 버전 4.7에서 실행되는 이진 파일에 영향을 주지 않습니다. .NET Framework 4.7의 다음과 같은 영역에 대상 다시 지정 변경 내용이 포함되어 있습니다.  

-   [핵심](#Core)  
-   [ASP.NET](#asp) 
-   [WCF(Windows Communication Foundation)](#WCF)  
-   [WPF(Windows Presentation Foundation)](#WPF)
 
 다음 테이블의 범위 열에는 각 변경 내용의 영향력이 지정되어 있습니다.  
  
-   주요함 다수의 앱에 영향을 주거나 코드를 대폭 수정해야 하는 중요한 변경 내용입니다. 이 범주에 속한 대상 다시 지정 변경 내용은 없습니다.  
  
-   사소함 소수의 앱에 영향을 주거나 코드를 약간만 수정해야 하는 변경 내용입니다.  
  
-   특별한 경우 일반적이지 않은 매우 특별한 시나리오의 앱에 영향을 주는 변경 내용입니다.  
  
-   투명 앱 개발자나 사용자에게 뚜렷한 영향을 주지 않는 변경 내용입니다. 이 변경 내용으로 인한 앱 수정은 필요하지 않습니다.  
  
## <a name="a-namecore--core"></a><a name="Core" /> Core

| 기능 | 변경 | 영향 | 범위 |
|----|----|----|----|
|<xref:System.Security.Cryptography.CspParameters.ParentWindowHandle%2A> | .NET Framework 4.6.2 및 이전 버전을 대상으로 하는 응용 프로그램에서는 이 속성에 할당된 값이 메모리에서 HWND 값이 있는 지정된 위치에 대한 </xref:System.IntPtr>일 것으로 예상합니다.<br/></br>.NET Framework 4.7을 대상으로 하는 앱부터 다음과 같은 코드를 사용하여 Windows Forms 응용 프로그램에서 이 속성의 값을 설정할 수 있습니다. <br/><br/>` cspParameters.ParentWindowHandle = form.Handle; ` | 이러한 동작 변경이 불편하다고 확인된 앱은 새 동작을 옵트아웃(opt out)할 수 있습니다. 마찬가지로 이전 버전의 .NET Framework를 대상으로 하지만 .NET Framework 4.7에서 실행되는 앱은 이러한 새 동작을 opt in(옵트인)할 수 있습니다. 자세한 내용은 [완화: CspParameters.ParentWindowHandle에 HWND 필요](../../../docs/framework/migration-guide/mitigation-cspparameters-parentwindowhandle-expects-an-hwnd.md)를 참조하세요. | 부 |
| <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용한 serialization | .NET Framework 4.7을 대상으로 하는 앱부터 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 사용한 제어 문자 serialization이 이제 ECMAScript V6 및 V8과 호환됩니다. | 이 변경 내용은 ECMAScript 표준을 준수하며 거의 영향을 미치지 않아야 합니다. 영향을 미치는 경우 호환성 스위치를 사용하여 이전 동작을 복원할 수 있습니다. 자세한 내용은 [완화: DataContractJsonSerializer로 제어 문자 serialization](../../../docs/framework/migration-guide/mitigation-serialization-control-characters.md)을 참조하세요.  | Microsoft Edge |

## <a name="a-nameasp--aspnet"></a><a name="asp" /> ASP.NET

| 기능  |변경  |영향 | 범위 | 
---------|---------|---------|-----|
세션당 동시 요청 수 조절 | .NET Framework 4.6.2 이전에서 ASP.NET은 동일한 <xref:System.Web.SessionState.HttpSessionState.SessionID%2A>를 사용해서 순차적으로 요청을 실행하고 ASP.NET은 기본적으로 항상 쿠키를 통해 <xref:System.Web.SessionState.HttpSessionState.SessionID%2A>를 실행합니다. 페이지를 로드하는 데 시간이 오래 걸릴 경우 브라우저의 <kbd>F5</kbd> 키를 누르면 서버 성능이 크게 저하됩니다.<br/><br/>.NET Framework 4.7부터는 카운터는 큐에 대기 중인 요청을 추적하고 지정된 한도를 초과할 때 요청을 종료합니다. 기본값은 50입니다. 이 제한에 도달하면 이벤트 로그에 경고가 기록되고 HTTP 500 응답이 IIS 로그에 기록될 수 있습니다.|이러한 변경은 전반적인 서버 성능을 향상시킬 수 있습니다.<br/><br/>이전 동작을 복원하려면 web.config 파일에 다음 설정을 추가하여 새 동작을 옵트아웃(opt out)할 수 있습니다.<br/><br/>`<appSettings>`<br/>&nbsp;&nbsp;&nbsp;`<add key="aspnet:RequestQueueLimitPerSession" value="2147483647"/>`<br/>`</appSettings>` | Microsoft Edge |

## <a name="a-namewcf--windows-communication-foundation"></a><a name="WCF" /> Windows Communication Foundation

| 기능  |변경  |영향 | 범위 | 
---------|---------|---------|-----|
| WCF 메시지 보안 | .NET Framework 4.7 이상에서 실행되는 앱은 응용 프로그램 구성 설정을 통해 WCF 메시지 보안에서 TLS 1.1 및 TLS 1.2를 사용할 수 있습니다. 이것은 옵트인(opt in) 기능입니다. 기본적으로 WCF 메시지 보안에서 TLS 1.1 및 TLS 1.2에 대한 지원은 사용되지 않도록 설정됩니다. | WCF 메시지 보안의 기본 동작은 변경되지 않습니다. <br/><br/> TLS 1.1 및 TLS 1.2에 대한 지원을 사용하도록 설정하려면 `app.config` 또는 `web.config` 파일의 [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가합니다.  <br/><br/>`<runtime>` <br/> &nbsp;&nbsp;&nbsp;`<AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;`<br/>&nbsp;&nbsp;&nbsp;`Switch.System.Net.DontEnableSchUseStrongCrypto=false" />`<br/>`</runtime>` | Microsoft Edge |         

## <a name="a-namewpf--windows-presentation-foundation-wpf"></a><a name="WPF" /> WPF(Windows Presentation Foundation)  

| 기능 | 변경 | 영향 | 범위 |
|---|---|---|---|
| 별 열에 대한 <xref:System.Windows.Controls.Grid> 컨트롤 공간 할당 | .NET Framework 4.7을 대상으로 하는 앱부터 WPF는 <xref:System.Windows.Controls.Grid> 컨트롤이 \*-columns.md에 공간을 할당하는 데 사용하는 알고리즘을 대신합니다. | .NET Framework 4.7 이상 버전을 대상으로 하는 응용 프로그램에서 많은 경우에 이러한 변경 내용이 \* 열에 할당된 실제 너비에 영향을 미칩니다. 이러한 변경을 원치 않을 경우 응용 프로그램 구성 파일에 항목을 추가하여 이전 알고리즘을 계속 적용할 수 있습니다. 자세한 내용은 [완화: Grid 컨트롤의 별 열 공간 할당](../../../docs/framework/migration-guide/mitigation-grid-control.md)을 참조하세요. | 부 |
| <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom%2A> | .NET Framework 4.6.2 및 이전 버전을 대상으로 하는 응용 프로그램에서는 <xref:System.Windows.Media.ImageSourceConverter.ConvertFrom%2A> 메서드에 대한 예외 처리 코드는 의도한 예외(예: [DirectoryNotFoundException](assetId:///T:System.IO.DirectoryNotFoundException) 또는 [FileNotFoundException](assetId:///T:System.IO.FileNotFoundException)) 대신 [NullReferenceException](assetId:///T:System.NullReferenceException]이 throw되도록 합니다.<br/><br/>.NET Framework 4.7을 대상으로 하는 앱부터 올바른 예외가 throw됩니다.  | .NET Framework 4.7 대상으로 하고 [NullReferenceException](assetId:///T:System.NullReferenceException) 처리에 종속되는 응용 프로그램은 `app.config` 파일의 [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이전 동작을 복원할 수 있습니다. <br/><br/>`<runtime>`<br/>&nbsp;&nbsp;&nbsp;`<AppContextSwitchOverrides value="Switch.System.Windows.Media.ImageSourceConverter.OverrideExceptionWithNullReferenceException=true"/>`<br/>`</runtime>`| Microsoft Edge | 
| `WM_POINTER` 기반 터치/스타일러스 스택에 대한 옵트인 지원 | .NET Framework 4.7을 대상으로 하는 앱부터 WPF는 선택적 `WM_POINTER 기반 터치에 대한 지원을 추가합니다.  | 이것은 Windows 10 작성자 업데이트 이상의 Windows 시스템에서 사용할 수 있는 옵트인 기능입니다. 포인터 기반 터치/스타일러스는 지원을 명시적으로 옵트인하지 않는 WPF 앱은 영향을 받지 않습니다. 자세한 내용은 [완화: 포인터 기반 터치 및 스타일러스 지원](../Topic/Mitigation:%20Pointer-based%20Touch%20and%20Stylus%20Support.md)을 참조하세요. | Microsoft Edge |
| [PrintQueue](assetId:///T:System.Printing.PrintQueue) 클래스 | .NET Framework 4.7부터 기본적으로 [PrintQueue](assetId:///T:System.Printing.PrintQueue)를 사용하는 WPF 인쇄 API는 더 이상 사용되지 않는 XPS 인쇄 API가 아닌 Windows 인쇄 문서 패키지 API를 호출합니다.<br/><br/>이전 인쇄 스택은 계속 이전 Windows 버전처럼 작동합니다. | 사용자와 개발자 모두 동작이나 API 사용에서 달라진 내용을 알 수 없습니다. <br/><br/>Windows 10 작성자 업데이트에서 이전 스택을 사용하려면 `HKEY_CURRENT_USER\Software\Microsoft.NETFramework\Windows Presentation Foundation\Printing` 레지스트리 키의 `UseXpsOMPrinting` `REG_DWORD` 값을 1로 설정합니다. | Microsoft Edge | 
## <a name="see-also"></a>참고 항목
[.NET Framework 4.7의 응용 프로그램 호환성](Application%20Compatibility%20in%20the%20.NET%20Framework%204.7.md)

