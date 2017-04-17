---
title: ".NET Framework 4.6의 런타임 변경 내용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5262bcfa-6e48-416b-8972-69cb4002d386
caps.latest.revision: 34
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# .NET Framework 4.6의 런타임 변경 내용
드문 경우지만 런타임 변경 내용이 이전 버전의 .NET Framework를 대상으로 하지만 이후 버전의 .NET Framework 런타임에서 실행되는 기존 앱에 영향을 줄 수 있습니다. 서로 다른 .NET Framework 런타임 환경에서 실행되는 응용 프로그램 간의 동작 차이도 포함됩니다. 다음 영역에 이러한 변경 내용이 포함되어 있습니다.  
  
-   [핵심](#Core)  
  
-   [네트워킹](#Networking)  
  
-   [WPF\(Windows Presentation Foundation\)](#WPF)  
  
-   [설치 및 배포](#Setup)  
  
-   [ClickOnce](#ClickOnce)  
  
-   [새로운 64비트 JIT 컴파일러](#RyuJIT)  
  
<a name="Core"></a>   
## 핵심  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|<xref:System.Globalization.PersianCalendar?displayProperty=fullName>|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]부터 <xref:System.Globalization.PersianCalendar> 클래스는 회교식 양력 알고리즘을 사용합니다.|회교식 양력 알고리즘은 이란과 아프가니스탄에서 현재 사용 중인 페르시아력과 같은 결과를 생성합니다. 또한 일반 달력의 1800년부터 일반 달력의 2023년까지의 날짜에 대한 이전 알고리즘과 동일한 결과를 생성합니다.<xref:System.Globalization.PersianCalendar> 클래스가 날짜 변환\(예: 일반 달력의 날짜와 페르시아력의 날짜 간 변환\)을 수행하거나 특정 연도가 윤년인지 여부를 결정하는 데 사용된 경우 범위를 벗어난 날짜가 영향을 받을 수 있습니다.<br /><br /> 이 변경으로 인해 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]이 설치된 시스템의 경우 <xref:System.Globalization.PersianCalendar.MinSupportedDateTime%2A?displayProperty=fullName> 속성 값이 0622년 3월 21일에서 0622년 3월 22일로 변경되었습니다.<br /><br /> 자세한 내용은 <xref:System.Globalization.PersianCalendar> 항목을 참조하세요.|사소함|  
|<xref:System.Runtime.Versioning.TargetFrameworkAttribute>|기본 응용 프로그램 도메인에서 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 속성 값은 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 속성에 이름을 할당하여 명시적으로 정의되지 않은 경우 <xref:System.Runtime.Versioning.TargetFrameworkAttribute>에서 파생됩니다\(있는 경우\).  이전 버전의 .NET Framework에서는 많은 특수 코드 경로가 실행되거나 해당 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 속성에 대상 프레임워크를 명시적으로 지정하지 않고 기본이 아닌 앱 도메인을 만든 경우가 아니면 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 특성 값은 `null`입니다.<br /><br /> 기본이 아닌 응용 프로그램 도메인의 경우 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 속성 값이 결정되는 방식이 변경되지 않습니다.<xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName> 속성에 값이 명시적으로 할당되지 않은 경우 기본이 아닌 앱 도메인은 기본 응용 프로그램 도메인에서 대상 프레임워크 이름을 상속합니다.|기본 응용 프로그램 도메인의 경우 <xref:System.AppDomainSetup.TargetFrameworkName%2A?displayProperty=fullName>에서 이전에 `null`이 반환된 경우에 null이 아닌 값이 반환될 수 있습니다. 이는 정상적인 동작입니다.|가장자리|  
|<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString%28System.Boolean%29?displayProperty=fullName>|시스템에 설치된 인증서가 .NET Framework에서 지원되지 않는 경우 `verbose` 인수에 대해 `True` 값을 전달하면 유효한 문자열이 반환됩니다. 이전 버전의 .NET Framework에서는 지원되지 않는 인증서의 공개 키 정보에 액세스하려고 할 때 예외가 발생하는 경우가 있습니다.|이 방법은 정보 제공 목적으로만 사용되며, .NET Framework 버전에 따라 출력이 달라질 수 있다고 설명서에 표시됩니다. 이 변경 내용은 `ToString(True)` 메서드를 호출하고 .NET Framework에서 지원되지 않는 인증서를 설치한 앱에만 영향을 줍니다. 이 변경으로 인해 예외가 발생하지 않고 문자열이 반환되므로 메서드가 보다 강력해집니다.|가장자리|  
|리플렉션 및 DCOM\(분산 COM\)|더이상 리플렉션 개체를 관리 코드에서 out\-of\-process DCOM 클라이언트로 전달할 수 없습니다.<xref:System.Reflection.Assembly>; <xref:System.Reflection.MemberInfo> 및 파생 형식\(<xref:System.Reflection.FieldInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Type>, <xref:System.Reflection.TypeInfo> 포함\), <xref:System.Reflection.MethodBody>, <xref:System.Reflection.Module> 및 <xref:System.Reflection.ParameterInfo> 형식이 영향을 받습니다.|개체에 대한 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707.aspx)을 호출하면 `E_NOINTERFACE`를 반환합니다.|사소함|  
  
<a name="Networking"></a>   
## 네트워킹  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|<xref:System.Net.Mime.ContentDisposition?displayProperty=fullName> 클래스의 날짜 및 시간 값|[RFC822](http://www.ietf.org/rfc/rfc0822.txt) 및 [RFC2822](http://www.ietf.org/rfc/rfc2822.txt)를 준수하기 위해 형식이 지정된 날짜 및 시간 값이 이제 2자릿수 시간으로 설정됩니다. 이전에는 오전 10:00 이전 값에 1자리 시간이 포함되었습니다.|이 변경 내용은 다음과 같은 사용 시나리오에 영향을 줍니다.<br /><br /> -   .NET Framework 버전 간에 직렬화된 <xref:System.Net.Mime.ContentDisposition> 개체의 길이 또는 해시 코드 비교<br />-   .NET Framework 버전 간에 <xref:System.Net.Mime.ContentDisposition.ToString%2A> 메서드의 반환 값 또는 <xref:System.Net.Mime.ContentDisposition> 날짜 및 시간 속성 값의 문자열 표현 비교|부|  
  
<a name="WPF"></a>   
## WPF\(Windows Presentation Foundation\)  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|다중 모니터 시나리오에서 창 렌더링|다중 모니터 시나리오에서 전체 창이 디스플레이를 벗어나 확장되는 경우 클리핑 없이 렌더링됩니다.|[완화: WPF 창 렌더링](../../../docs/framework/migration-guide/mitigation-wpf-window-rendering.md)을 참조하세요.|사소함|  
|WPF 텍스트 사용 컨트롤의 맞춤법 검사기|Windows 10에서 실행 중인 경우 입력 언어 목록에 있는 언어에 대해서만 플랫폼 맞춤법 검사 기능을 사용할 수 있으므로 맞춤법 검사기가 작동하지 않을 수 있습니다.|Windows 10에서 사용 가능한 키보드 목록에 언어를 추가하면 Windows가 맞춤법 검사 기능을 제공하는 해당 FOD\(주문형 기능\) 패키지를 자동으로 다운로드하고 설치합니다. 입력 언어 목록에 언어를 추가하면 맞춤법 검사기가 지원됩니다.|부|  
  
<a name="Setup"></a>   
## 설치 및 배포  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|제품 버전 관리|제품 버전 관리가 .NET Framework의 이전 릴리스와 특히, .NET Framework 4, 4.5, 4.5.1 및 4.5.2에서 변경되었습니다. 자세한 내용은 [완화: 제품 버전 관리](../../../docs/framework/migration-guide/mitigation-product-versioning.md)을 참조하십시오.|[완화: 제품 버전 관리](../../../docs/framework/migration-guide/mitigation-product-versioning.md)을 참조하세요.|중간|  
  
<a name="ClickOnce"></a>   
## ClickOnce  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|SHA\-256 코드 서명 인증서를 사용하는 ClickOnce로 게시된 앱|[!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 또는 이전 버전을 대상으로 하고 SHA\-256 인증서로 서명된 ClickOnce가 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 이상 버전에서는 더 이상 런타임 종속성이 없습니다.|이전에는 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 또는 이전 버전을 대상으로 하는 ClickOnce 앱을 SHA\-256 인증서로 서명하려면 대상 시스템에 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 이상 버전이 있어야 했습니다. 이러한 버전이 없을 경우 오류가 발생했습니다. 이 변경 내용은 해당 종속성을 제거하고 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 및 이전 버전을 대상으로 하는 ClickOnce 앱을 SHA\-256 인증서로 서명할 수 있게 합니다.|부|  
  
<a name="RyuJIT"></a>   
## 새로운 64비트 JIT 컴파일러  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|예외 처리\(`try` 영역에서 반환\)|이전 JIT64 Just\-In\-Time 컴파일러와 달리 새 64비트 JIT 컴파일러는 `try` 영역에서 IL [ret](http://msdn.microsoft.com/library/system.reflection.emit.opcodes.ret.aspx) 명령을 허용하지 않습니다.|`try` 영역에서 반환은 ECMA\-335 사양에서 허용되지 않으며 이러한 IL을 생성하는 알려진 관리 컴파일러는 없습니다. 그러나 이러한 IL이 리플렉션 내보내기를 사용하여 생성된 경우에는 JIT64 컴파일러에서 실행됩니다.|가장자리|