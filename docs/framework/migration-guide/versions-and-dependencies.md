---
title: ".NET Framework 버전 및 종속성"
ms.custom: updateeachrelease
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords: versions, .NET Framework
ms.assetid: f75a72de-e2f2-4a7a-9574-3f278684ea90
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5fc4e1de77a6105b803f4fb9ed8dd644eb2ef144
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2017
---
# <a name="net-framework-versions-and-dependencies"></a>.NET Framework 버전 및 종속성
.NET Framework의 각 버전에는 CLR(공용 언어 런타임), 기본 클래스 라이브러리 및 기타 관리되는 라이브러리가 포함되어 있습니다. 이 항목에서는 버전별 .NET Framework의 주요 기능에 대해 설명하고 기본 CLR 버전 및 관련 개발 환경에 대한 정보를 제공하며 Windows 운영 체제별로 설치된 버전을 확인합니다.  
  
> [!NOTE]
>  .NET Framework 다운로드 및 설치에 대한 자세한 내용은 [개발자용 .NET Framework 설치](../../../docs/framework/install/guide-for-developers.md)를 참조하세요.  
  
 다음 테이블에는 .NET Framework 버전 기록이 요약되어 있으며 Visual Studio, Windows 및 Windows Server와의 상관 관계가 나와 있습니다. Visual Studio에서는 나열된 .NET Framework 버전으로 사용이 제한되지 않도록 멀티 타기팅 기능을 제공합니다.  
  
 새 .NET Framework 버전에서는 각각 이전 버전의 기능을 유지하며 새 기능을 추가합니다. CLR은 고유한 버전 번호로 식별됩니다. CLR 버전은 매번 증가하지 않지만, .NET Framework 버전 번호는 각 릴리스마다 증가합니다. 예를 들어 .NET Framework 4, 4.5 및 이후 릴리스에는 CLR 4가 포함되지만 .NET Framework 2.0, 3.0 및 3.5에는 CLR 2.0이 포함됩니다. CLR 버전 3이 포함된 .NET Framework 버전은 없습니다.  
  
 지원되는 운영 체제의 전체 목록은 [시스템 요구 사항](../../../docs/framework/get-started/system-requirements.md)을 참조하십시오. 다운로드에 대해서는 [개발자용 .NET Framework 설치](../../../docs/framework/install/guide-for-developers.md)를 참조하세요. 참조 컴퓨터에 설치 된.NET Framework의 버전을 확인 하기 위한 [하는 방법:.NET Framework 버전이 설치 된 확인](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)합니다.  
  
 표의 **Windows에 포함됨/설치 가능** 및 **Windows Server에 포함됨/설치 가능** 열에 ✓ 표시된 운영 체제 버전에 설치되어 있는 .NET Framework 버전은 [제어판에서 활성화](../../../docs/framework/install/dotnet-35-windows-10.md)되거나(Windows의 경우) 서버 관리자를 통해 활성화되어야(Windows Server의 경우) 합니다.  
  
|.NET Framework 버전|CLR 버전|기능|포함된 Visual Studio 버전|✓ 다음에서 포함된 버전:<br />+ 다음에서 설치 가능한 버전:<br />Windows|✓ 다음에서 포함된 버전:<br />+ 다음에서 설치 가능한 버전:<br />Windows Server|설치된 .NET 버전 확인 방법|  
|----------------------------|-----------------|--------------|---------------------------------------|----------------------------------------------------|-----------------------------------------------------------|-----------------------------------------| 
|4.7.1|4|.NET 표준 2.0에 대 한 지원입니다.<br/> 런타임 시 구성 파일의 생성을 허용 하는 구성 작성기에 대 한 지원.<br/> -Runtime 기능 검색 미리 정의 된 기능 런타임 환경에서 지원 되는지 여부를 확인할 수 있습니다.<br/> -직렬화 가능 값 튜플의 합니다.<br/> -가비지 수집에 대 한 향상 된 성능입니다.<br/> 이식 가능한 Pdb에 대 한 지원입니다.<br/> -에 대 한 지원 s h A-2 <xref:System.Messaging.Message.HashAlgorithm%2A?displayProperty=nameWithType>합니다.<br/> ASP.NET 쿠키 포함 된 구문에 대 한 지원의 <xref:System.Web.HttpCookie.TryParse%2A?displayProperty=nameWithType> 메서드.<br/> ASP.NET 폼 인증 자격 증명에 대 한 해시 s h A-2에 대 한 지원.<br/> -응용 프로그램 개발자에; 다양 한 내게 필요한 옵션 기능 향상 참조 [내게 필요한 옵션에는.NET Framework의 새로운 기능](../whats-new/whats-new-in-accessibility.md)합니다.| | ✓ 10 년 작성자 업데이트 <br/> <br/> + 10 작성자 업데이트 <br/> + 10 1주년 업데이트 <br/> + 8.1 <br/> +7| + 2016 <br/> + 2012 R2 <br/> + 2012 <br/> + 2008 R2 SP1 |`Release` DWORD 사용:<br/><br/> -461308 (Windows 10 작성자 업데이트) <br/> -461310 (다른 모든 OS 버전) <br/><br/> ([지침](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) 참조) 
|4.7|4|- 운영 체제에서 제공하는 TLS 지원 수준 지원.<br/> - TLS1.1 또는 TLS1.2에 대한 기본 메시지 보안 설정 구성 가능. <br /> - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>의 안정성 향상 <br /> - WCF 응용 프로그램을 사용한 직렬화 및 역직렬화 안정성 향상. <br /> - ASP.NET 개체 캐시 확장 가능. <br /> - WPF 응용 프로그램용 WISP(Windows 잉크 서비스 플랫폼) 대신 `WM_POINTER` Windows 메시지 기반의 터치/스타일러스 스택 지원. <br /> - WPF 응용 프로그램에서 인쇄하는 경우 Windows 인쇄 문서 패키지 API 사용.<br /> - Windows 10 크리에이터 업데이트에서 실행되는 Windows Forms 응용 프로그램에 대한 높은 DPI 및 다중 모니터 지원 향상 | | ✓  10 제작자 업데이트 <br/> <br/> + 10 1주년 업데이트 <br/> + 8.1 <br/> +7| + 2016 <br/> + 2012 R2 <br/> + 2012 <br/> + 2008 R2 SP1 |`Release` DWORD 사용:<br/><br/> - 460798(Windows 10 크리에이터 업데이트) <br/> - 460805(다른 모든 OS 버전) <br/><br/> ([지침](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) 참조) |  
|4.6.2|4|- FIS 186-3 DSA를 포함하는 X509 인증서에 대한 지원, 지속형 키 대칭형 암호화 지원, SHA-2 해시에 대한 <xref:System.Security.Cryptography.Xml.SignedXml> 지원, ECDiffieHellman 키 파생 루틴에 대한 입력 정확성 향상을 비롯한 암호화 향상.<br />-   WPF(Windows Presentation Foundation) 앱에 대한 소프트 키보드 지원 및 모니터별 DPI.<br />-   TLS 1.1 및 TLS 1.2 프로토콜에 대한 ClickOnce 지원.<br />-   Windows Forms 및 WPF 앱을 UWP 앱으로 변환 지원.||✓  10 1주년 업데이트<br /><br /> + 8.1<br />+ 7|✓  2016<br /><br /> + 2012 R2<br />+ 2012<br />+ 2008 R2 SP1|`Release` DWORD 사용:<br /><br /> -   394802(Windows 10 1주년 업데이트)<br />-   394806(다른 모든 OS 버전)<br /><br /> ([지침](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) 참조)|  
|4.6.1|4|-   ECDSA를 포함하는 X509 인증서 지원<br />-   ADO.NET의 하드웨어로 보호된 키에 대해 상시 암호화 지원<br />-   WPF의 향상된 맞춤법 검사<br />-   [자세히...](../../../docs/framework/whats-new/index.md)||✓ 10 11월 업데이트<br /><br /> + 10<br />+ 8.1<br />+ 8<br />+ 7|+ 2012 R2<br />+ 2012<br />+ 2008 R2 SP1|`Release` DWORD 사용:<br /><br /> -   394254(Windows 10 11월 업데이트)<br />-   394271(다른 모든 OS 버전)<br /><br /> ([지침](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) 참조)|  
|4.6|4|-   .NET 네이티브를 사용하여 컴파일<br />-   ASP.NET Core 5<br />-   이벤트 추적 향상<br />-   페이지 인코딩 지원<br />-   [자세히...](../../../docs/framework/whats-new/index.md)|2015(일부 .NET 라이브러리는 [NuGet](https://www.nuget.org/)에서 사용할 수 있음) 자세한 내용은 [.NET Framework 및 번외 릴리스](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)를 참조하십시오.|✓ 10<br />+ 8.1<br />+ 8<br />+ 7<br />+ Vista|+ 2012 R2<br />+ 2012<br />+ 2008 R2 SP1<br />+ 2008 SP2|`Release` DWORD 사용:<br /><br /> -   393295(Windows 10)<br />-   393297(다른 모든 OS 버전)<br /><br /> ([지침](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) 참조)|  
|4.5.2|4|-   트랜잭션 시스템 및 ASP.NET을 위한 새 API<br />-   시스템 DPI를 통한 Windows Forms 컨트롤 크기 조정<br />-   프로파일링 기능 향상<br />-   ETW 및 스트레스 로깅 향상<br />-   [자세히...](../../../docs/framework/whats-new/index.md)|-|+ 8.1<br />+ 8<br />+ 7<br />+ Vista|+ 2012 R2<br />+ 2012<br />+ 2008 R2 SP1<br />+ 2008 SP2|`Release` DWORD 사용: 379893<br />([지침](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) 참조)|  
|4.5.1|4|-   Windows Phone 스토어 앱 지원<br />-   자동 바인딩 리디렉션<br />-   성능 및 디버깅 향상<br />-   [자세히...](../../../docs/framework/whats-new/index.md)|2013|✓ 8.1<br />+ 8<br />+ 7<br />+ Vista|✓ 2012 R2<br />+ 2012<br />+ 2008 R2 SP1<br />+ 2008 SP2|`Release` DWORD 사용:<br /><br /> -   378675(Windows 8.1)<br />-   378758(다른 모든 버전)<br /><br /> ([지침](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) 참조)|  
|4.5|4|-   Windows 스토어 앱 지원<br />-   WPF, WCF, WF, ASP.NET 업데이트<br />-   [자세히...](../../../docs/framework/whats-new/index.md)|2012|✓ 8<br />+ 7<br />+ Vista|✓ 2012<br />+ 2008 R2 SP1<br />+ 2008 SP2|`Release` DWORD 사용: 378389<br />([지침](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) 참조)|  
|4|4|-   확장된 기본 클래스 라이브러리<br />-   이식 가능한 클래스 라이브러리로 플랫폼 간 개발<br />-   MEF, DLR, 코드 계약<br />-   [자세히...](http://msdn.microsoft.com/library/ms171868\(v=vs.100\).aspx)|2010|+ 7<br />+ Vista|+ 2008 R2 SP1<br />+ 2008 SP2<br />+ 2003|[지침](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) 참조|  
|3.5|2.0|-   AJAX 사용 웹 사이트<br />-   LINQ<br />-   Dynamic Data<br />-   [자세히...](http://msdn.microsoft.com/library/ms171868\(v=vs.90\).aspx)|2008|✓ 10✓ 8.1*<br />✓ 8\*<br />✓ 7<br />+ Vista|✓ 2008 R2 SP1*<br />+ 2012 R2<br />+ 2012<br />+ 2008 SP2<br />+ 2003|[지침](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) 참조|  
|3.0|2.0|-   WPF, WCF, WF, CardSpace|-|✓ Vista|✓ 2008 R2 SP1*<br />✓ 2008 SP2\*<br />+ 2003|[지침](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) 참조|  
|2.0|2.0|-   제네릭<br />-   ASP.NET 추가 기능<br />-   [자세히...](http://msdn.microsoft.com/library/t357fb32\(v=vs.80\).aspx)|2005|-|✓ 2008 R2 SP1<br />✓ 2008 SP2<br />✓ 2003|[지침](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) 참조|  
|1.1|1.1|-   ASP.NET 및 ADO.NET 업데이트<br />-   Side-by-Side 실행<br />-   [자세히...](http://msdn.microsoft.com/library/9wtde3k4\(v=vs.80\).aspx)|2003|-|✓ 2003|[지침](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) 참조|  
|1.0|1.0|.NET Framework 첫 번째 버전|Visual Studio .NET|-|-|[지침](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) 참조|  
  
 사용 중인 응용 프로그램이 특정 버전에 종속적일 수 있고 해당 버전을 제거하면 응용 프로그램이 중단될 수 있으므로 컴퓨터에 설치된 .NET Framework의 모든 버전은 일반적으로 제거하면 안 됩니다. 여러 버전의 .NET Framework를 동시에 단일 컴퓨터에서 로드할 수 있습니다. 즉, 이전 버전을 제거하지 않고도 .NET Framework를 설치할 수 있습니다. 자세한 내용은 [시작](../../../docs/framework/get-started/index.md)을 참조하십시오.  
  
## <a name="targeting-and-running-net-framework-apps-for-version-45-and-later"></a>.NET Framework 앱의 대상을 버전 4.5 이상으로 지정 및 앱 실행  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 대체 하는 현재 위치 업데이트는 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 컴퓨터에서와 마찬가지로,는 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 및 4.7.1은 내부 업데이트에는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], 즉, 동일한 런타임 버전을 사용 하는 하지만 어셈블리 버전이 업데이트 되 고 새 형식과 멤버를 포함 합니다. 이러한 업데이트 중 하나를 설치한 후 프로그램 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], [!INCLUDE[net_v45](../../../includes/net-v45-md.md)],.NET Framework 4.6 또는.NET Framework 4.7 앱 다시 컴파일할 필요 없이 실행할 계속 해야 합니다. 하지만 그 반대의 경우는 성립되지 않습니다. .NET Framework의 이전 버전에서 최신 버전의.NET Framework를 대상으로 하는 앱을 실행 하는 것은 좋지 않습니다. 예를 들어 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에서 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]을 대상으로 하는 앱을 실행하지 않는 것이 좋습니다. 다음과 같은 지침이 적용됩니다.  
  
-   Visual Studio에서는 프로젝트에 대한 대상 프레임워크로 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]를 선택(<xref:Microsoft.Build.Tasks.GetReferenceAssemblyPaths.TargetFrameworkMoniker%2A?displayProperty=nameWithType> 속성을 설정)하여 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 어셈블리 또는 실행 파일로 프로젝트를 컴파일할 수 있습니다. 이 어셈블리 또는 실행 파일 수에서 사용할 수 있는 모든 컴퓨터는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 또는 4.7.1 설치 합니다.  
  
-   Visual Studio에서는 프로젝트에 대한 대상 프레임워크로 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]를 선택(<xref:Microsoft.Build.Tasks.GetReferenceAssemblyPaths.TargetFrameworkMoniker%2A?displayProperty=nameWithType> 속성을 설정)하여 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 어셈블리 또는 실행 파일로 프로젝트를 컴파일할 수 있습니다. 이 어셈블리 또는 실행 파일은 .NET Framework [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 이상의 버전이 설치된 컴퓨터에서만 실행됩니다. [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]을 대상으로 하는 실행 파일은 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]와 같은 이전 버전의 .NET Framework만 설치된 컴퓨터에서 실행되는 것이 차단되며 사용자에게 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]을 설치하라는 메시지가 표시됩니다. 또한는 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 어셈블리와 같은 이전 버전의.NET Framework를 대상으로 하는 응용 프로그램에서 호출할 수 없습니다는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]합니다.  
  
     여기서 [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 및 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]는 예제로만 사용됩니다. 이 원칙 적용 모든 응용 프로그램에 대상으로 하는 실행 중인 시스템에 설치 되어 있는 것 보다 최신 버전의.NET Framework 합니다.  
  
 .NET Framework의 일부 변경 내용으로 인해 앱 코드를 변경해야 할 수 있습니다. [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 이상 버전에서 기존 앱을 실행하기 전에 [응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility.md)을 참조하십시오. 현재 버전 설치에 대한 자세한 내용은 [개발자용 .NET Framework 설치](../../../docs/framework/install/guide-for-developers.md)를 참조하세요. .NET Framework 지원에 대한 자세한 내용은 Microsoft 지원 웹 사이트의 [Microsoft .NET Framework 지원 기간 정책](http://go.microsoft.com/fwlink/?LinkId=196607)을 참조하십시오.  
  
## <a name="targeting-and-running-apps-for-older-versions"></a>이전 버전에 대한 대상 지정 및 앱 실행  
 .NET Framework 버전 2.0, 3.0 및 3.5는 동일한 버전의 CLR(CLR 2.0)로 빌드됩니다. 이러한 버전은 단일 설치의 후속 레이어를 나타냅니다. 각 버전은 이전 버전 위에 증분 방식으로 빌드됩니다. 컴퓨터에서 버전 2.0, 3.0 및 3.5를 side-by-side 실행할 수는 없습니다. 버전 3.5를 설치하면 2.0 및 3.0 레이어가 자동으로 설치되며 버전 2.0, 3.0 및 3.5용으로 빌드된 앱 모두를 3.5 버전에서 실행할 수 있습니다. 그러나 이 계층적 방식은 .NET Framework 4에서 종료됩니다. .NET Framework 4부터는 In-Process Side-By-Side 호스팅을 사용하여 단일 프로세스에서 여러 버전의 CLR을 실행할 수 있습니다. 자세한 내용은 [어셈블리 및 Side-by-Side 실행](../../../docs/framework/app-domains/assemblies-and-side-by-side-execution.md)을 참조하십시오.  
  
 또한 앱이 버전 2.0, 3.0 또는 3.5를 대상으로 하는 경우 사용자가 앱을 실행하기 전에 [!INCLUDE[win8](../../../includes/win8-md.md)] 또는 [!INCLUDE[win81](../../../includes/win81-md.md)] 컴퓨터에서 .NET Framework 3.5를 사용하도록 설정해야 할 수 있습니다. 자세한 내용은 [Windows 10, Windows 8.1 및 Windows 8에 .NET Framework 3.5 설치](../../../docs/framework/install/dotnet-35-windows-10.md)를 참조하세요.  
  
## <a name="next-steps"></a>다음 단계  
  
-   .NET Framework를 처음 사용하는 경우 [개요](../../../docs/framework/get-started/overview.md)에서 주요 개념 및 기능에 대한 소개를 참조하십시오.  
  
-   [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 및 해당 포인트 릴리스의 새로운 기능과 개선 사항을 확인하려면 [ .NET Framework의 새로운 기능](../../../docs/framework/whats-new/index.md)을 참조하십시오.  
  
-   앱을 .NET Framework 4에서 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 및 해당 포인트 릴리스로 마이그레이션하는 방법에 대한 자세한 내용은 [마이그레이션 가이드](../../../docs/framework/migration-guide/index.md)를 참조하십시오.  
  
-   컴퓨터에 설치된 버전 또는 업데이트 확인에 대한 자세한 내용은 [방법: 설치된 .NET Framework 버전 확인](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) 및 [방법: 설치된 .NET Framework 업데이트 확인](../../../docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목

[버전 호환성](../../../docs/framework/migration-guide/version-compatibility.md)   
[Microsoft .NET Framework 지원 기간 정책](http://go.microsoft.com/fwlink/?LinkId=196607)   
[차단된 .NET Framework 설치 및 제거 문제 해결](../../../docs/framework/install/troubleshoot-blocked-installations-and-uninstallations.md)
