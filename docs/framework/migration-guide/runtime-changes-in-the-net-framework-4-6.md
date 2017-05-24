---
title: ".NET Framework 4.6의 런타임 변경 내용 | Microsoft 문서"
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
- runtime changes, .NET Framework
- runtime changes, .NET Framework 4.6
- application compatibility
ms.assetid: 5262bcfa-6e48-416b-8972-69cb4002d386
caps.latest.revision: 34
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 77002c3d1b6553156c225b3efba9a2f29009915a
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-46"></a>.NET Framework 4.6의 런타임 변경 내용
드문 경우지만 런타임 변경 내용이 이전 버전의 .NET Framework를 대상으로 하지만 이후 버전의 .NET Framework 런타임에서 실행되는 기존 앱에 영향을 줄 수 있습니다. 서로 다른 .NET Framework 런타임 환경에서 실행되는 응용 프로그램 간의 동작 차이도 포함됩니다. 다음 영역에 이러한 변경 내용이 포함되어 있습니다.  
  
-   [핵심](#Core)  
  
-   [Data](#Data)  
  
-   [네트워킹](#Networking)  
  
-   [WCF(Windows Communication Foundation)](#WCF)  
  
-   [WPF(Windows Presentation Foundation)](#WPF)  
  
-   [설치 및 배포](#Setup)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [새로운 64비트 JIT 컴파일러](#RyuJIT)  
  
<a name="Core"></a>   
## <a name="core"></a>핵심  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]부터는 <xref:System.Globalization.PersianCalendar> 클래스에서 회교식 양력 알고리즘을 사용합니다.|회교식 양력 알고리즘은 이란과 아프가니스탄에서 현재 사용 중인 페르시아력과 같은 결과를 생성합니다. 또한 일반 달력의 1800년부터 일반 달력의 2023년까지의 날짜에 대한 이전 알고리즘과 동일한 결과를 생성합니다. <xref:System.Globalization.PersianCalendar> 클래스가 날짜 변환(예: 일반 달력의 날짜와 페르시아력의 날짜 간 변환)을 수행하거나 특정 연도가 윤년인지 여부를 결정하는 데 사용된 경우 범위를 벗어난 날짜가 영향을 받을 수 있습니다.<br /><br /> 이 변경으로 인해 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]이 설치된 시스템의 <xref:System.Globalization.PersianCalendar.MinSupportedDateTime%2A?displayProperty=fullName> 속성 값이 0622년 3월 21일에서 0622년 3월 22일로 변경되었습니다.<br /><br /> 자세한 내용은 <xref:System.Globalization.PersianCalendar>항목을 참조하십시오.|사소함|  
|<xref:System.Runtime.Versioning.TargetFrameworkAttribute>|기본 응용 프로그램 도메인의 경우 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 속성으로 이름을 할당하여 명시적으로 정의되지 않는 이상, <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 속성 값은(존재하는 경우) <xref:System.Runtime.Versioning.TargetFrameworkAttribute>에서 파생됩니다.  이전 버전의 .NET Framework의 경우 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 특성은 많은 특수 코드 경로가 실행되지 않거나 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 속성에서 해당 대상 프레임 워크를 명시적으로 지정하지 않고 비기본 앱 도메인이 생성되지 않는 이상 `null`이 됩니다.<br /><br /> 기본이 아닌 응용 프로그램 도메인의 경우 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>속성 값이 결정되는 방법에는 변화가 없습니다. <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 속성에 값이 명시적으로 할당되지 않은 경우 기본이 아닌 앱 도메인은 기본 응용 프로그램 도메인에서 대상 프레임워크 이름을 상속합니다.|기본 응용 프로그램 도메인의 경우 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>이 이전에 반환된 null이 아닌 값을 반환할 수 있습니다 `null`. 이는 정상적인 동작입니다.|Microsoft Edge|  
|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|시스템에 설치된 인증서가 .NET Framework에서 지원되지 않는 경우 `verbose` 인수에 대해 `True` 값을 전달하면 유효한 문자열이 반환됩니다. 이전 버전의 .NET Framework에서는 지원되지 않는 인증서의 공개 키 정보에 액세스하려고 할 때 예외가 발생하는 경우가 있습니다.|이 방법은 정보 제공 목적으로만 사용되며, .NET Framework 버전에 따라 출력이 달라질 수 있다고 설명서에 표시됩니다. 이 변경 내용은 `ToString(True)` 메서드를 호출하고 .NET Framework에서 지원되지 않는 인증서를 설치한 앱에만 영향을 줍니다. 이 변경으로 인해 예외가 발생하지 않고 문자열이 반환되므로 메서드가 보다 강력해집니다.|Microsoft Edge|  
|ETW(Windows용 이벤트 추적 - event tracing for Windows)|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 및 4.6.1의 경우 두 개의 이벤트 이름이 “Start" 또는 “Stop" 접미사만 다를 때(예: 한 이벤트는 `LogUser`, 다른 이벤트는 `LogUserStart`이라고 이름을 지정하는 경우) 런타임에서 <xref:System.ArgumentException>를 throw합니다. 이 경우 런타임에서 로깅을 발생할 수 없는 이벤트 소스를 구성할 수 없습니다.|두 개의 이벤트 이름이 "Start" 또는 "Stop" 접미사만 다른지 확인합니다.<br /><br /> 이 요구 사항에 따라 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]부터 제거됩니다. 런타임에서 "Start" 접미사만 다른 이벤트 이름의 차이를 보여줄 수 있습니다.|Microsoft Edge|  
|리플렉션 및 DCOM(분산 COM)|더이상 리플렉션 개체를 관리 코드에서 out-of-process DCOM 클라이언트로 전달할 수 없습니다. <xref:System.Reflection.Assembly>, <xref:System.Reflection.MemberInfo>및 <xref:System.Reflection.FieldInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Type> 및 <xref:System.Reflection.TypeInfo>을 비롯한 파생 형식, <xref:System.Reflection.MethodBody>, <xref:System.Reflection.Module> 및 <xref:System.Reflection.ParameterInfo> 형식이 영향을 받습니다.|개체에 대한 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707.aspx)을 호출하면 `E_NOINTERFACE`를 반환합니다.|사소함|  
  
<a name="Data"></a>   
## <a name="data"></a>데이터  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|`localhost`로 확인되는 SQL Server 데이터베이스에 TCP/IP 연결|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]부터는 "SQL Server에 연결하는 동안 네트워크 관련 오류 또는 인스턴스에 특정한 오류가 발생했습니다”라는 오류가 표시되면서 연결 시도에 실패합니다. 서버를 찾을 수 없거나 액세스할 수 없습니다. 인스턴스 이름이 올바르고 SQL Server가 원격 연결을 허용하도록 구성되어 있는지 확인합니다. (공급자: SQL 네트워크 인터페이스, 오류: 26-지정된 서버/인스턴스를 찾는 동안 오류가 발생했습니다) "|이 문제는 해결되었으며 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]에서 이전 동작이 복원되었습니다. `localhost`로 확인되는 SQL Server 데이터베이스에 연결하려면 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]로 업그레이드합니다.|사소함|  
  
<a name="Networking"></a>   
## <a name="networking"></a>네트워킹  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|<xref:System.Net.Mime.ContentDisposition?displayProperty=fullName> 클래스의 날짜와 시간 값.|[RFC822](http://www.ietf.org/rfc/rfc0822.txt) 및 [RFC2822](http://www.ietf.org/rfc/rfc2822.txt)를 준수하기 위해 형식이 지정된 날짜 및 시간 값이 이제 2자릿수 시간으로 설정됩니다. 이전에는 오전 10:00 이전 값에 1자리 시간이 포함되었습니다.|이 변경 내용은 다음과 같은 사용 시나리오에 영향을 줍니다.<br /><br /> -   .NET Framework 버전 간에 직렬화된 <xref:System.Net.Mime.ContentDisposition> 개체의 길이 또는 해시 코드 비교.<br />-   <xref:System.Net.Mime.ContentDisposition.ToString%2A>메서드의 반환 값 또는 .NET Framework 버전 간에 <xref:System.Net.Mime.ContentDisposition> 날짜 및 시간 속성 값의 문자열 표현 비교.|사소함|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>WCF(Windows Communication Foundation)  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|SSL 보안 및 인증서 인증을 통해 NETTCP를 사용하는 WCF 서비스|.NET Framework 4.6은 WCF SSL 기본 프로토콜 목록에 TLS 1.1 및 TLS 1.2를 추가합니다. 클라이언트와 서버 컴퓨터에.NET Framework 4.6 및 이후 버전이 설치되어 있으면 TLS 1.2가 협상에 사용됩니다.|TLS 1.2는 MD5 인증서 인증을 지원하지 않습니다. 결과적으로, 고객이 MD5 인증서를 사용하는 경우 WCF 클라이언트는 WCF 서비스에 연결하지 못합니다. 자세한 내용은 [완화: WCF 서비스 및 인증서 인증](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md)을 참조하십시오.|사소함|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>WPF(Windows Presentation Foundation)  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|다중 모니터 시나리오에서 창 렌더링|다중 모니터 시나리오에서 전체 창이 디스플레이를 벗어나 확장되는 경우 클리핑 없이 렌더링됩니다.|[완화: WPF 창 렌더링](../../../docs/framework/migration-guide/mitigation-wpf-window-rendering.md)을 참조하십시오.|사소함|  
|WPF 텍스트 사용 컨트롤의 맞춤법 검사기|Windows 10에서 실행 중인 경우 입력 언어 목록에 있는 언어에 대해서만 플랫폼 맞춤법 검사 기능을 사용할 수 있으므로 맞춤법 검사기가 작동하지 않을 수 있습니다.|Windows 10에서 사용 가능한 키보드 목록에 언어를 추가하면 Windows가 맞춤법 검사 기능을 제공하는 해당 FOD(주문형 기능) 패키지를 자동으로 다운로드하고 설치합니다. 입력 언어 목록에 언어를 추가하면 맞춤법 검사기가 지원됩니다.|부|  
  
<a name="Setup"></a>   
## <a name="setup-and-deployment"></a>설치 및 배포  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|제품 버전 관리|제품 버전 관리가 .NET Framework의 이전 릴리스와 특히, .NET Framework 4, 4.5, 4.5.1 및 4.5.2에서 변경되었습니다. 자세한 내용은 [완화: 제품 버전 관리](../../../docs/framework/migration-guide/mitigation-product-versioning.md)를 참조하십시오.|[완화: 제품 버전 관리](../../../docs/framework/migration-guide/mitigation-product-versioning.md)를 참조하십시오.|중간|  
  
<a name="ClickOnce"></a>   
## <a name="clickonce"></a>ClickOnce  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|SHA-256 코드 서명 인증서를 사용하는 ClickOnce로 게시된 앱|[!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 또는 이전 버전을 대상으로 하고 SHA-256 인증서로 서명된 ClickOnce가 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 이상 버전에서는 더 이상 런타임 종속성이 없습니다.|이전에는 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 또는 이전 버전을 대상으로 하는 ClickOnce 앱을 SHA-256 인증서로 서명하려면 대상 시스템에 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 이상 버전이 있어야 했습니다. 이러한 버전이 없을 경우 오류가 발생했습니다. 이 변경 내용은 해당 종속성을 제거하고 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 및 이전 버전을 대상으로 하는 ClickOnce 앱을 SHA-256 인증서로 서명할 수 있게 합니다.|부|  
  
<a name="RyuJIT"></a>   
## <a name="the-new-64-bit-jit-compiler"></a>새로운 64비트 JIT 컴파일러  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|64비트 JIT 컴파일|.NET Framework 4.6부터는 새로운 64비트 JIT 컴파일러가 Just-In-Time 컴파일에 사용됩니다. 이 변경 내용은 32비트 JIT 컴파일러에는 영향을 주지 않습니다.|경우에 따라 예기치 않은 예외가 throw되거나 32비트 컴파일러 또는 이전 64비트 JIT 컴파일러를 사용하여 앱을 실행하는 경우와 다른 동작이 관찰됩니다. **참고:** .NET Framework 4.6.2와 함께 릴리스된 새로운 64비트 컴파일러에서 이러한 모든 문제가 해결되었습니다. Windows 업데이트에 포함된 .NET Framework 4.6 및 4.6.1의 서비스 릴리스에서도 대부분의 문제가 해결되었습니다. <br /><br /> 자세한 내용은 [완화: 새로운 64비트 JIT 컴파일러](../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)를 참조하십시오.|Microsoft Edge|  
|예외 처리(`try` 영역에서 반환)|이전 JIT64 Just-In-Time 컴파일러와 달리 새 64비트 JIT 컴파일러는 `try` 영역에서 IL `ret` 명령을 허용하지 않습니다.|`try` 영역에서 반환은 ECMA-335 사양에서 허용되지 않으며 이러한 IL을 생성하는 알려진 관리 컴파일러는 없습니다. 그러나 이러한 IL이 리플렉션 내보내기를 사용하여 생성된 경우에는 JIT64 컴파일러에서 실행됩니다.<br /><br /> 해당 앱이 `try` 영역에서 `ret` opcode를 포함하는 IL을 생성하는 경우 다음을 수행할 수 있습니다.<br /><br /> -   .NET Framework 4.5를 대상으로 하거나 [\<useLegacyJIT>](../../../docs/framework/configure-apps/file-schema/runtime/uselegacyjit-element.md) 요소를 이전 JIT 컴파일러를 사용하는 응용 프로그램 구성 파일에 추가하고 변경하지 않도록 합니다.<br />-   생성된 IL을 업데이트하여 `try` 영역 다음에 반환합니다.<br />-|Microsoft Edge|
