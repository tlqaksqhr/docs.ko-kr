---
title: ".NET Framework 초기화 오류: 사용자 환경 관리 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - ".NET Framework, 초기화 오류"
  - "초기화 오류[.NET Framework]"
  - "프레임워크가 없는 환경"
ms.assetid: 680a7382-957f-4f6e-b178-4e866004a07e
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# .NET Framework 초기화 오류: 사용자 환경 관리
공용 언어 런타임\(common language runtime\)\(CLR\) 정품 인증 시스템에서는 관리되는 응용 프로그램 코드를 실행하는 데 사용할 CLR 버전을 결정합니다.  일부 경우 정품 인증 시스템은 로드할 CLR의 버전을 찾지 못할 수도 있습니다.  이러한 상황은 응용 프로그램에서 잘못되었거나 지정된 컴퓨터에 설치되어 있지 않은 CLR 버전이 필요한 경우 일반적으로 발생합니다.  요청한 버전이 발견되지 않으면 CLR 활성화 시스템 함수는 호출된 함수 또는 인터페이스로부터 HRESULT 오류 코드를 반환하고, 응용 프로그램 사용자에게 에러 메세지를 보여줄 수 있습니다.  이 문서에서는 HRESULT 코드 목록을 제공하고 오류 메시지 표시를 방지할 수 있는 방법을 설명합니다.  
  
 CLR에서는 [방법: CLR 활성화 문제 디버깅](../../../docs/framework/deployment/how-to-debug-clr-activation-issues.md)에서 설명한 대로 CLR 활성화 문제를 디버깅하는 데 도움을 주는 로깅 인프라를 제공합니다.  이 인프라를 완전히 다른 [어셈블리 바인딩 로그](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md)와 혼동하면 안 됩니다.  
  
## CLR 활성화 HRESULT 코드  
 CLR 활성화 API는 활성화 작업의 결과를 호스트에 보고하기 위해 HRESULT 코드를 반환합니다.  CLR 호스트는 추가 작업을 계속하기 전에 이러한 반환 값을 항상 확인해야 합니다.  
  
-   CLR\_E\_SHIM\_RUNTIMELOAD  
  
-   CLR\_E\_SHIM\_RUNTIMEEXPORT  
  
-   CLR\_E\_SHIM\_INSTALLROOT  
  
-   CLR\_E\_SHIM\_INSTALLCOMP  
  
-   CLR\_E\_SHIM\_LEGACYRUNTIMEALREADYBOUND  
  
-   CLR\_E\_SHIM\_SHUTDOWNINPROGRESS  
  
## 초기화 오류에 대한 UI  
 CLR 활성화 시스템이 응용 프로그램에 필요한 올바른 버전의 런타임을 로드할 수 없으면, 사용자에게 응용 프로그램을 실행할 수 있는 환경을 올바르게 구성하지 못했음 알려주는 에러 메세지를 나타내고, 이러한 문제를 해결할 수 있는 방법을 제공합니다.  일반적으로 이 상황에서는 다음과 같은 오류 메시지가 나타납니다.  사용자는 **예**를 선택하여 응용 프로그램용의 올바른 .NET Framework 버전을 다운로드할 수 있는 Microsoft 웹 사이트로 이동합니다.  
  
 ![.NET Framework 초기화 오류 대화 상자](../../../docs/framework/deployment/media/initerrordialog.png "InitErrorDialog")  
초기화 오류에 대한 일반적인 오류 메시지  
  
## 초기화 오류 해결  
 개발자로서 여러분은 .NET Framework 초기화 오류 메시지를 제어하는 다양한 옵션을 갖고 있습니다.  예를 들어, 다음 섹션에 설명된 것처럼 메시지 표시를 방지하는 API 플래그를 사용할 수 있습니다.  그러나 여전히 응용 프로그램에서 요청한 런타임을 로드하지 못하도록 하는 문제를 해결해야 합니다.  그렇지 않으면 응용 프로그램이 전혀 실행되지 않거나 일부 기능을 사용할 수 없습니다.  
  
 기본 문제를 해결하고 최고의 사용자 환경을 제공하기 위해\(더 적은 오류 메시지\) 다음을 권장합니다.  
  
-   .NET Framework 3.5 및 이전 버전 응용 프로그램: .NET Framework 4 또는 4.5를 지원하도록 응용 프로그램을 구성하십시오. \([지침](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)을 참조하십시오\).  
  
-   .NET Framework 4 응용 프로그램: 응용 프로그램 설치 일부로 .NET Framework 4 재배포 가능 패키지를 설치합니다.  [개발자를 위한 배포 가이드](../../../docs/framework/deployment/deployment-guide-for-developers.md)를 참조하십시오.  
  
## 오류 메시지를 제어  
 요청한 .NET Framework 버전을 찾을 수 없었음을 알리는 오류 메시지의 표시가 유용한 서비스로 또는 사용자를 덜 짜증나게 하는 수단으로 사용될 수 있습니다.  어느 경우나 플래그를 활성화 API로 전달하여 이 UI를 제어할 수 있습니다.  
  
 [ICLRMetaHostPolicy::GetRequestedRuntime](../Topic/ICLRMetaHostPolicy::GetRequestedRuntime%20Method.md) 메서드는 입력으로 [METAHOST\_POLICY\_FLAGS](../../../ocs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) 열거형 멤버를 허용합니다.  요청한 CLR 버전을 찾을 수 없는 경우 오류 메시지를 요청하려면 METAHOST\_POLICY\_SHOW\_ERROR\_DIALOG 플래그를 포함시킬 수 있습니다.  기본적으로 오류 메시지는 표시되지 않습니다. \([ICLRMetaHost::GetRuntime](../Topic/ICLRMetaHost::GetRuntime%20Method.md) 메서드는 이 플래그를 사용할 수 없으며 이외의 오류 메시지 표시 방법을 제공하지 않습니다.\)  
  
 Windows에서는 프로세스 내에서 실행 되는 코드의 결과로 오류 메시지를 표시할지 여부를 선언하는데 사용할 수 있는 [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkID=255242) 함수를 제공합니다.  오류 메시지가 표시되지 않도록 SEM\_FAILCRITICALERRORS 플래그를 지정할 수 있습니다.  
  
 그러나 일부 시나리오에서는 응용 프로그램 프로세스를 통해 설정된 SEM\_FAILCRITICALERRORS 설정을 재정의하는 것이 중요합니다.  예를 들어, CLR을 호스트로 하는 네이티브 COM 구성요소가 SEM\_FAILCRITICALERRORS가 설정된 곳의 프로세스에서 호스트한다면 특정 응용 프로그램 프로세스의 에러 메세지 출력에 따라 플래그를 오버라이드하는 것이 좋습니다.  이 경우 다음 플래그 중 하나를 사용하여 SEM\_FAILCRITICALERRORS를 재정의합니다.  
  
-   METAHOST\_POLICY\_IGNORE\_ERROR\_MODE를 [ICLRMetaHostPolicy::GetRequestedRuntime](../Topic/ICLRMetaHostPolicy::GetRequestedRuntime%20Method.md) 메서드와 함께 사용합니다.  
  
-   RUNTIME\_INFO\_IGNORE\_ERROR\_MODE를 [GetRequestedRuntimeInfo](../../../ocs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md) 함수에 사용합니다.  
  
## CLR에서 제공하는 호스트에 대한 UI 정책  
 CLR에는 다양한 시나리오에 대한 호스트 집합이 포함되어 있으며 이러한 호스트 모두는 런타임의 필요한 버전 로드 시 문제가 발생하는 경우에 오류 메시지를 표시합니다.  다음 표에서는 호스트 목록 및 오류 메시지 정책을 제공합니다.  
  
|CLR 호스트|설명|오류 메시지 정책|오류 메시지를 비활성화할 수 있습니까?|  
|-------------|--------|---------------|---------------------------|  
|관리 EXE 호스트|관리되는 EXE를 시작합니다.|누락된 .NET Framework 버전의 경우 표시|아니요|  
|관리 COM 호스트|관리되는 COM 구성 요소를 프로세스에 로드합니다.|누락된 .NET Framework 버전의 경우 표시|예. SEM\_FAILCRITICALERRORS 플래그를 설정하여|  
|ClickOnce 호스트|ClickOnce 응용 프로그램을 시작합니다.|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]로 시작되는 누락된 .NET Framework 버전의 경우 표시|아니요|  
|XBAP 호스트|WPF XBAP 응용 프로그램을 시작합니다.|[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]로 시작되는 누락된 .NET Framework 버전의 경우 표시|아니요|  
  
## [!INCLUDE[win8](../../../includes/win8-md.md)] 동작 및 UI  
 CLR 활성화 시스템은 CLR 2.0 로드 시 문제가 발생하는 경우를 제외하고 다른 버전의 Windows 운영 체제에서와 마찬가지로 [!INCLUDE[win8](../../../includes/win8-md.md)]에서 동일한 동작과 UI를 제공합니다.  [!INCLUDE[win8](../../../includes/win8-md.md)]. 여기에는 CLR 4.5를 사용하는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]가 포함됩니다. 그러나 [!INCLUDE[win8](../../../includes/win8-md.md)]은 CLR 2.0을 사용하는 .NET Framework 2.0, 3.0 또는 3.5을 포함하지 않습니다.  결과적으로 CLR 2.0을 사용하는 응용 프로그램은 기본적으로 [!INCLUDE[win8](../../../includes/win8-md.md)]에서 실행되지 않습니다.  대신, 사용자가 .NET Framework 3.5를 설치할 수 있는 다음 대화 상자가 표시됩니다.  사용자는 제어판에서 .NET Framework 3.5를 사용할 수도 있습니다.  두 옵션 모두 문서 [Installing the .NET Framework 3.5 on Windows 8 and later versions](../../../docs/framework/install/net-framework-3-5-on-windows-8-plus.md)에서 설명합니다.  
  
 ![Windows 8에 3.5 설치용 대화 상자](../../../docs/framework/deployment/media/installdialog.png "installdialog")  
요청 시 .NET Framework 3.5를 설치하도록 메시지 표시  
  
> [!NOTE]
>  [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]는 사용자 컴퓨터에서 .NET Framework 4\(CLR 4\)를 대체합니다.  따라서 .NET Framework 4 응용 프로그램은 [!INCLUDE[win8](../../../includes/win8-md.md)]에 이 대화 상자를 표시하지 않고 완벽하게 실행됩니다.  
  
 .NET Framework 3.5가 설치되면 사용자는 [!INCLUDE[win8](../../../includes/win8-md.md)] 컴퓨터에서 .NET Framework 2.0, 3.0 또는 3.5에 종속된 응용 프로그램을 실행할 수 있습니다.  이는 이러한 응용 프로그램에서 .NET Framework 1.0 또는 1.1에서만 실행되도록 명시적으로 구성되지 않을 경우 .NET Framework 1.0 및 1.1 응용 프로그램을 실행할 수도 있습니다.  [.NET Framework 1.1에서 마이그레이션](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)를 참조하십시오.  
  
 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]로 시작하는 CLR 활성화 로깅은 초기화 오류 메시지 시기 및 이유를 기록하는 로그 항목을 포함하도록 향상되었습니다.  자세한 내용은 [방법: CLR 활성화 문제 디버깅](../../../docs/framework/deployment/how-to-debug-clr-activation-issues.md)을 참조하십시오.  
  
## 참고 항목  
 [개발자를 위한 배포 가이드](../../../docs/framework/deployment/deployment-guide-for-developers.md)   
 [방법: .NET Framework 4 또는 4.5를 지원하도록 응용 프로그램 구성](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)   
 [방법: CLR 활성화 문제 디버깅](../../../docs/framework/deployment/how-to-debug-clr-activation-issues.md)   
 [Installing the .NET Framework 3.5 on Windows 8 and later versions](../../../docs/framework/install/net-framework-3-5-on-windows-8-plus.md)