---
title: "WPF 부분 신뢰 보안 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "부분 신뢰 응용 프로그램 디버깅"
  - "권한 검색"
  - "보안 요구 사항 제공"
  - "권한 관리"
  - "부분 신뢰 응용 프로그램, 디버깅"
  - "부분 신뢰 보안"
  - "권한, 검색"
  - "권한, 관리"
  - "Internet Explorer의 보안 설정"
ms.assetid: ef2c0810-1dbf-4511-babd-1fab95b523b5
caps.latest.revision: 40
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 36
---
# WPF 부분 신뢰 보안
<a name="introduction"></a> 일반적으로 악의적인 손상을 방지하기 위해 인터넷 응용 프로그램은 중요한 시스템 리소스에 직접 액세스하는 것이 제한되어야 합니다.  기본적으로 [!INCLUDE[TLA#tla_html](../../../includes/tlasharptla-html-md.md)] 및 클라이언트 쪽 스크립팅 언어에서는 중요한 시스템 리소스에 직접 액세스할 수 없습니다.  브라우저에서 호스팅되는 [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] 응용 프로그램은 브라우저에서 시작할 수 있으므로 일련의 유사한 제한을 따라야 합니다.  이러한 제한을 적용하기 위해 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]는 [!INCLUDE[TLA#tla_cas](../../../includes/tlasharptla-cas-md.md)] 및 [!INCLUDE[TLA#tla_clickonce](../../../includes/tlasharptla-clickonce-md.md)]를 모두 사용합니다\([WPF 보안 전략 \- 플랫폼 보안](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md) 참조\).  기본적으로 브라우저에서 호스팅되는 응용 프로그램은 인터넷에서 시작했는지, 로컬 인트라넷에서 시작했는지, 아니면 로컬 컴퓨터에서 시작했는지에 관계없이 인터넷 영역 [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] 권한 집합을 요청합니다.  전체 권한 집합보다 적은 권한으로 실행되는 응용 프로그램을 부분 신뢰 수준으로 실행된다고 말합니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]는 부분 신뢰에서 가능한 많은 기능을 안전하게 사용할 수 있도록 광범위한 지원을 제공하며 [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)]를 함께 사용하여 부분 신뢰 프로그래밍을 위한 추가 지원을 제공합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [WPF 기능 부분 신뢰 지원](#WPF_Feature_Partial_Trust_Support)  
  
-   [부분 신뢰 프로그래밍](#Partial_Trust_Programming)  
  
-   [권한 관리](#Managing_Permissions)  
  
<a name="WPF_Feature_Partial_Trust_Support"></a>   
## WPF 기능 부분 신뢰 지원  
 다음 표에서는 인터넷 영역 권한 집합의 제한 내에서 안전하게 사용할 수 있는 [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)]의 상위 수준 기능을 보여 줍니다.  
  
 표 1: 부분 신뢰에서 안전한 WPF 기능  
  
|기능 영역|기능|  
|-----------|--------|  
|일반|브라우저 창<br /><br /> 원본 사이트 액세스<br /><br /> IsolatedStorage\(512KB 한도\)<br /><br /> UIAutomation 공급자<br /><br /> 명령<br /><br /> IME\(입력기\)<br /><br /> 태블릿 스타일러스 및 잉크<br /><br /> 마우스 캡처 및 이동 이벤트를 사용한 시뮬레이션된 끌기\/놓기<br /><br /> OpenFileDialog<br /><br /> XamlReader.Load를 통한 XAML Deserialization|  
|웹 통합|브라우저 다운로드 대화 상자<br /><br /> 사용자가 시작하는 최상위 탐색<br /><br /> mailto:links<br /><br /> Uniform Resource Identifier 매개 변수<br /><br /> HTTPWebRequest<br /><br /> IFRAME에서 호스팅되는 WPF 콘텐츠<br /><br /> 프레임을 사용하여 동일한 사이트 HTML 페이지 호스팅<br /><br /> 웹 브라우저를 사용하여 동일한 사이트 HTML 페이지 호스팅<br /><br /> 웹 서비스\(ASMX\)<br /><br /> 웹 서비스\(Windows Communication Foundation 사용\)<br /><br /> 스크립팅<br /><br /> 문서 개체 모델|  
|시각적 표시|2D 및 3D<br /><br /> 애니메이션<br /><br /> 미디어\(원본 사이트 및 크로스 도메인\)<br /><br /> 이미징\/오디오\/비디오|  
|읽기|FlowDocuments<br /><br /> XPS 문서<br /><br /> 포함 및 시스템 글꼴<br /><br /> CFF 및 트루타입 글꼴|  
|편집|맞춤법 검사<br /><br /> RichTextBox<br /><br /> 일반 텍스트 및 잉크 클립보드 지원<br /><br /> 사용자가 시작한 붙여넣기<br /><br /> 선택한 콘텐츠 복사|  
|컨트롤|일반 컨트롤|  
  
 이 표에서는 상위 수준의 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] 기능을 보여 줍니다.  [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]의 각 멤버에 필요한 권한이 문서화되어 있는 [!INCLUDE[TLA#tla_lhsdk](../../../includes/tlasharptla-lhsdk-md.md)]에서 자세한 내용을 확인할 수 있습니다.  또한 다음 기능에서는 부분 신뢰 실행과 관련된 더 자세한 정보를 제공하고 특별히 고려해야 할 사항도 설명합니다.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]\([XAML 개요\(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) 참조\)  
  
-   팝업\(<xref:System.Windows.Controls.Primitives.Popup?displayProperty=fullName> 참조\)  
  
-   끌어서 놓기\([끌어서 놓기 개요](../../../docs/framework/wpf/advanced/drag-and-drop-overview.md) 참조\)  
  
-   클립보드\(<xref:System.Windows.Clipboard?displayProperty=fullName> 참조\)  
  
-   이미징\(<xref:System.Windows.Controls.Image?displayProperty=fullName> 참조\)  
  
-   Serialization\(<xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=fullName>, <xref:System.Windows.Markup.XamlWriter.Save%2A?displayProperty=fullName> 참조\)  
  
-   파일 열기 대화 상자\(<xref:Microsoft.Win32.OpenFileDialog?displayProperty=fullName> 참조\)  
  
 다음 표에서는 인터넷 영역 권한 집합의 제한 내에서 실행하는 것이 안전하지 않은 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] 기능을 보여 줍니다.  
  
 표 2: 부분 신뢰에서 안전하지 않은 WPF 기능  
  
|기능 영역|기능|  
|-----------|--------|  
|일반|창\(응용 프로그램에서 정의한 창 및 대화 상자\)<br /><br /> SaveFileDialog<br /><br /> 파일 시스템<br /><br /> 레지스트리 액세스<br /><br /> 끌어서 놓기<br /><br /> XamlWriter.Save를 통한 XAML Serialization<br /><br /> UIAutomation 클라이언트<br /><br /> 소스 창 액세스\(HwndHost\)<br /><br /> 완전한 음성 지원<br /><br /> Windows Forms 상호 운용성|  
|시각적 표시|비트맵 효과<br /><br /> 이미지 인코딩|  
|편집|서식있는 텍스트 형식 클립보드<br /><br /> 완전한 XAML 지원|  
  
<a name="Partial_Trust_Programming"></a>   
## 부분 신뢰 프로그래밍  
 [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] 응용 프로그램의 경우 기본 권한 집합을 초과하는 코드는 보안 영역에 따라 다르게 동작하게 됩니다.  설치하려고 시도할 때 경고가 발생하는 경우도 있습니다.  사용자는 설치를 계속하거나 취소하도록 선택할 수 있습니다.  다음 표에서는 각 보안 영역에 대한 응용 프로그램 동작과 응용 프로그램에서 완전 신뢰를 받기 위해 수행해야 하는 작업에 대해 설명합니다.  
  
|보안 영역|동작|완전 신뢰 얻기|  
|-----------|--------|--------------|  
|로컬 컴퓨터|자동 완전 신뢰|아무런 작업도 수행할 필요가 없습니다.|  
|인트라넷 및 신뢰할 수 있는 사이트|완전 신뢰 확인|사용자가 프롬프트에서 소스를 볼 수 있도록 인증서로 XBAP에 서명합니다.|  
|Internet|"신뢰할 수 없음"이라는 메시지가 표시되고 실패함|인증서로 XBAP에 서명합니다.|  
  
> [!NOTE]
>  위의 표에서 설명한 동작은 신뢰할 수 있는 ClickOnce 배포 모델을 따르지 않는 완전 신뢰 XBAP에 대한 동작입니다.  
  
 일반적으로 허용되는 권한을 초과할 수 있는 코드는 독립 실행형 응용 프로그램과 브라우저에서 호스팅되는 응용 프로그램 사이에서 공유되는 공용 코드입니다.  [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] 및 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]에서는 이 시나리오를 관리하기 위한 여러 기술이 제공됩니다.  
  
<a name="Detecting_Permissions_using_CAS"></a>   
### CAS를 사용하여 권한 탐지  
 라이브러리 어셈블리의 공유 코드를 독립 실행형 응용 프로그램 및 [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] 모두에서 사용할 수 있는 경우가 있습니다.  이러한 경우 코드는 응용 프로그램의 부여된 권한 집합에서 허용되는 것보다 많은 권한이 필요한 기능을 실행할 수 있습니다.  응용 프로그램은 [!INCLUDE[TLA#tla_winfx](../../../includes/tlasharptla-winfx-md.md)] 보안을 실행하여 특정 권한을 갖고 있는지 여부를 탐지할 수 있습니다.  특히 원하는 권한의 인스턴스에서 <xref:System.Security.CodeAccessPermission.Demand%2A> 메서드를 호출하여 특정 권한을 갖고 있는지 테스트할 수 있습니다.  로컬 디스크에 파일을 저장할 수 있는 기능이 있는지 쿼리하는 다음 예제 코드에서는 이 사항을 보여 줍니다.  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode2)]  
  
 응용 프로그램에 원하는 권한이 없는 경우 <xref:System.Security.CodeAccessPermission.Demand%2A>를 호출하면 보안 예외가 throw됩니다.  그렇지 않으면 권한이 부여된 것입니다.  `IsPermissionGranted`는 이 동작을 캡슐화하고 `true` 또는 `false`를 적절히 반환합니다.  
  
<a name="Graceful_Degradation_of_Functionality"></a>   
### 기능의 점진적 저하  
 필요한 작업을 수행할 수 있는 권한이 코드에 있는지 여부를 탐지하는 것은 다른 영역에서 실행할 수 있는 코드와 관련됩니다.  영역을 탐지하는 것이 별개의 문제이지만 가능하다면 사용자에게 대체 방법을 제공하는 것이 훨씬 좋습니다.  예를 들어 일반적으로 완전 신뢰 응용 프로그램에서 사용자는 원하는 모든 곳에 파일을 만들 수 있지만 부분 신뢰 응용 프로그램에서는 격리된 저장소에만 파일을 만들 수 있습니다.  파일을 만들기 위한 코드가 완전 신뢰\(독립 실행형\) 응용 프로그램 및 부분 신뢰\(브라우저에서 호스팅된\) 응용 프로그램 모두에서 공유하는 어셈블리에 존재하고 두 응용 프로그램 모두에서 사용자가 파일을 만들 수 있게 하려면 공유된 코드는 해당 위치에서 파일을 만들기 전에 부분 신뢰 또는 완전 신뢰에서 실행 중인지 여부를 탐지해야 합니다.  다음 코드에서는 두 사항을 모두 보여 줍니다.  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode2)]  
  
 대부분의 경우 부분 신뢰 대체 방법을 찾을 수 있어야 합니다.  
  
 인트라넷과 같은 제어된 환경에서는 관리되는 사용자 지정 프레임워크를 클라이언트 기반을 경유하여 [!INCLUDE[TLA#tla_gac](../../../includes/tlasharptla-gac-md.md)]에 설치할 수 있습니다.  이러한 라이브러리는 완전 신뢰가 필요한 코드를 실행할 수 있으며 <xref:System.Security.AllowPartiallyTrustedCallersAttribute>를 사용하여 부분 신뢰에서만 허용되는 응용 프로그램에서 참조할 수 있습니다. 자세한 내용은 [보안](../../../docs/framework/wpf/security-wpf.md) 및 [WPF 보안 전략 \- 플랫폼 보안](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)을 참조하십시오.  
  
<a name="Browser_Host_Detection"></a>   
### 브라우저 호스트 탐지  
 [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)]를 사용하여 권한을 검사하는 것은 권한 단위로 검사해야 할 경우 적합한 기술입니다.  그러나 이 기술은 표준 처리의 일부를 예외로 catch하는 것에 의존하므로 일반적으로 권장되지 않으며 성능 문제를 일으킬 수 있습니다.  대신에 인터넷 영역 샌드박스 내에서만 [!INCLUDE[TLA#tla_xbap](../../../includes/tlasharptla-xbap-md.md)]가 실행되는 경우 [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)]에 대해 true를 반환하는 <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=fullName> 속성을 사용할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A>는 응용 프로그램이 실행될 때 사용하는 권한 집합이 아니라 응용 프로그램이 브라우저에서 실행 중인지 여부만 구별합니다.  
  
<a name="Managing_Permissions"></a>   
## 권한 관리  
 기본적으로 [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)]는 부분 신뢰 수준에서 실행됩니다\(기본 인터넷 영역 권한 집합\).  그러나 응용 프로그램의 요구 사항에 따라 권한 집합을 기본값에서 변경할 수 있습니다.  예를 들어 [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)]가 로컬 인트라넷에서 시작될 경우 다음 표와 같이 늘어난 권한 집합을 활용할 수 있습니다.  
  
 표 3: LocalIntranet 및 Internet 권한  
  
|권한|특성|LocalIntranet|Internet|  
|--------|--------|-------------------|--------------|  
|DNS|DNS 서버 액세스|예|아니요|  
|환경 변수|Read|예|아니요|  
|파일 대화 상자|를 엽니다.|예|예|  
|파일 대화 상자|무제한|예|아니요|  
|격리된 저장소|사용자별 어셈블리 격리|예|아니요|  
|격리된 저장소|알 수 없는 격리|예|예|  
|격리된 저장소|제한되지 않은 사용자 할당량|예|아니요|  
|미디어|안전한 오디오, 비디오 및 이미지|예|예|  
|인쇄|기본 인쇄|예|아니요|  
|인쇄|안전한 인쇄|예|예|  
|리플렉션|내보내기|예|아니요|  
|보안|관리 코드 실행|예|예|  
|보안|부여된 권한 어설션|예|아니요|  
|사용자 인터페이스|무제한|예|아니요|  
|사용자 인터페이스|안전한 최상위 창|예|예|  
|사용자 인터페이스|고유한 클립보드|예|예|  
|웹 브라우저|HTML로의 안전한 프레임 탐색|예|예|  
  
> [!NOTE]
>  사용자가 시작한 경우 잘라내기 및 붙여넣기는 부분 신뢰에서만 허용됩니다.  
  
 권한을 늘려야 하는 경우 프로젝트 설정과 ClickOnce 응용 프로그램 매니페스트를 변경해야 합니다.  자세한 내용은 [WPF XAML 브라우저 응용 프로그램 개요](../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)를 참조하십시오.  다음 문서도 도움이 될 수 있습니다.  
  
-   [Mage.exe\(매니페스트 생성 및 편집 도구\)](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md).  
  
-   [MageUI.exe \(매니페스트 생성 및 편집 도구, 그래픽 클라이언트\)](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).  
  
-   [ClickOnce 응용 프로그램 보안](../Topic/Securing%20ClickOnce%20Applications.md).  
  
 [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)]에서 완전 신뢰가 필요한 경우 동일한 도구를 사용하여 요청된 권한을 늘릴 수 있습니다.  단, [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)]는 로컬 컴퓨터, 인트라넷 또는 브라우저의 신뢰할 수 있거나 허용된 사이트에 있는 URL에서 설치되고 시작된 경우에만 완전 신뢰를 받습니다.  응용 프로그램이 인트라넷 또는 신뢰할 수 있는 사이트에서 설치된 경우 사용자는 고급 권한에 대해 알리는 표준 ClickOne 프롬프트를 받습니다.  사용자는 설치를 계속하거나 취소하도록 선택할 수 있습니다.  
  
 또는 완전 신뢰 배포를 위해 신뢰할 수 있는 ClickOnce 배포 모델을 모든 보안 영역에서 사용할 수 있습니다.  자세한 내용은 [신뢰할 수 있는 응용 프로그램 배포 개요](../Topic/Trusted%20Application%20Deployment%20Overview.md) 및 [보안](../../../docs/framework/wpf/security-wpf.md)을 참조하십시오.  
  
## 참고 항목  
 [보안](../../../docs/framework/wpf/security-wpf.md)   
 [WPF 보안 전략 \- 플랫폼 보안](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)   
 [WPF 보안 전략 \- 보안 엔지니어링](../../../docs/framework/wpf/wpf-security-strategy-security-engineering.md)