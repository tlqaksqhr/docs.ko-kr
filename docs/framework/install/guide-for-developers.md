---
title: ".NET Framework 설치 | Microsoft 문서"
ms.custom: 
ms.date: 04/28/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: get-started-article
helpviewer_keywords:
- .NET Framework redistributable package, downloading
- .NET Framework, installing
- installing .NET Framework
- installation [.NET Framework]
ms.assetid: daf9d9d5-84ac-4bd9-a864-27665ffd0f5c
caps.latest.revision: 165
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 65036823e67475a73c39ae60dff41cba5fa90dbb
ms.contentlocale: ko-kr
ms.lasthandoff: 05/11/2017

---
# <a name="installing-the-net-framework"></a>.NET Framework 설치

.NET은 Windows에서 실행되는 대부분의 응용 프로그램에서 필수적인 요소이며, 해당 응용 프로그램이 실행되는 데 필요한 공통적인 기능을 제공합니다. 개발자를 위해 .NET Framework에서는 시각적으로 멋진 사용자 환경 및 원활하고 안전한 통신이 가능한 응용 프로그램을 구축하기 위한 포괄적이고 일관적인 프로그래밍 모델을 제공합니다.  

이 문서에서는 컴퓨터에 .NET Framework 4.5와 해당 포인트 릴리스(4.5.1, 4.5.2), [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 해당 포인트 릴리스(4.6.1, 4.6.2) 및 .NET Framework 4.7을 설치하기 위한 링크를 제공합니다. 개발자는 이러한 링크를 앱과 함께 .NET Framework를 다운로드하고 재배포하기 위해 사용할 수 있습니다.

.NET Framework의 새 버전을 설치한다고 항상 이전 버전이 대체되는 것은 아닙니다. .NET Framework 버전 및 컴퓨터에 설치된 버전을 확인하는 방법에 대한 자세한 내용은 [버전 및 종속성](~/docs/framework/migration-guide/versions-and-dependencies.md) 및 [방법: 설치되는 .NET Framework 버전 결정](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)을 참조하십시오. 다음 표에 나열된 모든 .NET Framework 버전은 .NET Framework 4의 현재 위치 업데이트입니다. 다시 말해 .NET Framework 4.6과 같은 최신 버전을 설치하는 경우 .NET Framework 4.5, 4.5.1 또는 4.5.2 등의 이전 버전을 먼저 설치할 필요가 없습니다. 마찬가지로 .NET Framework 4.6과 같은 최신 버전을 설치하는 경우 .NET Framework 4.5, 4.5.1 또는 4.5.2 등의 이전 버전을 먼저 제거할 필요도 없습니다. 

.NET Framework 4.x 이상 버전이 이전 버전에 In-place 업데이트된다는 것은 최신 버전이 이미 설치된 경우 표에 나열된 이전 버전을 설치*할 수 없다*는 의미입니다. 예를 들면 Windows 10의 11월 업데이트 시스템에 .NET Framework 4.6.1이 사전 설치되어 있으므로 .NET Framework 4.6을 설치할 수 없습니다.    

> [!NOTE]
> .NET Framework 3.5에 대한 자세한 내용은 [Windows 8 이상 버전에 .NET Framework 3.5 설치](~/docs/framework/install/net-framework-3-5-on-windows-8-plus.md)를 참조하십시오.

다음 표에서 빠른 링크를 확인하거나 자세한 내용을 확인하세요. 설치하기 전에 .NET Framework에 대한 시스템 요구 사항을 보려면 [시스템 요구 사항](~/docs/framework/get-started/system-requirements.md)을 참조하십시오. 문제 해결에 대한 도움말은 [문제 해결](~/docs/framework/install/troubleshoot-blocked-installations-and-uninstallations.md)을 참조하십시오.  

|.NET Framework 버전|개발자 설치|재배포 가능 설치|플랫폼 지원|  
|----------------------------|----------------------------|----------------------------------|----------------------|  
|**4.7**|[NET Framework 4.7 개발자 팩](http://go.microsoft.com/fwlink/?LinkId=825319)|[4.7 웹 설치 관리자의 다운로드 페이지](http://go.microsoft.com/fwlink/?LinkId=825299)<br /><br /> [4.7 오프라인 설치 관리자의 다운로드 페이지](http://go.microsoft.com/fwlink/?LinkId=825303)|포함된 운영 체제: <br/>Windows 10 작성자 업데이트<br /><br /> 설치 가능한 운영 체제:<br /> Windows 10 1주년 업데이트<br /> Windows 8.1 및 이전 버전<br /> Windows Server 2012 R2 및 이전 버전<br /> (전체 목록은 [시스템 요구 사항](~/docs/framework/get-started/system-requirements.md) 참조)||
|**4.6.2**|[NET Framework 4.6.2 개발자 팩](http://go.microsoft.com/fwlink/?LinkId=780617)|[4.6.2 웹 설치 관리자의 다운로드 페이지](http://go.microsoft.com/fwlink/?LinkId=780597)<br /><br /> [4.6.2 오프라인 설치 관리자의 다운로드 페이지](http://go.microsoft.com/fwlink/?LinkId=780601)|포함된 운영 체제: <br /> Windows 10 Anniversary Edition<br /><br /> 설치 가능한 운영 체제:<br /> Windows 10 <br /> Windows 8.1 및 이전 버전<br /> Windows Server 2012 R2 및 이전 버전<br /> (전체 목록은 [시스템 요구 사항](~/docs/framework/get-started/system-requirements.md) 참조)|
|**4.6.1**|[NET Framework 4.6.1 개발자 팩](http://go.microsoft.com/fwlink/?LinkId=690706)|[4.6.1 웹 설치 관리자의 다운로드 페이지](http://go.microsoft.com/fwlink/?LinkId=671729)<br /><br /> [4.6.1 오프라인 설치 관리자의 다운로드 페이지](http://go.microsoft.com/fwlink/?LinkId=671744)|설치 가능한 운영 체제:<br /> Windows 10 <br /> Windows 8.1 및 이전 버전<br /> Windows Server 2012 R2 및 이전 버전<br /> (전체 목록은 [시스템 요구 사항](~/docs/framework/get-started/system-requirements.md) 참조)|
|**4.6**|[!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]에 포함됨 자세한 내용은 [Visual Studio 2015 시작](http://msdn.microsoft.com/library/dd831853\(v=vs.140\).aspx)을 참조하십시오.<br /><br /> [Microsoft .NET Framework 4.6 타기팅 팩](http://go.microsoft.com/fwlink/?LinkId=528261)|[4.6 웹 설치 관리자의 다운로드 페이지](http://go.microsoft.com/fwlink/?LinkId=528259)<br /><br /> [4.6 오프라인 설치 관리자의 다운로드 페이지](http://go.microsoft.com/fwlink/?LinkId=528233)|포함된 운영 체제: <br /> Windows 10 <br />[!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]<br /><br /> 설치 가능한 운영 체제:<br /> Windows 8.1 및 이전 버전<br /> Windows Server 2012 R2 및 이전 버전<br /> (전체 목록은 [시스템 요구 사항](~/docs/framework/get-started/system-requirements.md) 참조)|  
|**4.5.2**|[Microsoft .NET Framework 4.5.2 개발자 팩](http://go.microsoft.com/fwlink/?LinkId=397702)<br /><br /> [Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=325532), Visual Studio 2012 또는 기타 IDE와 함께 사용할 경우|[4.5.2 웹 설치 관리자의 다운로드 페이지](http://go.microsoft.com/fwlink/p/?LinkId=397703)<br /><br /> [4.5.2 오프라인 설치 관리자의 다운로드 페이지](http://go.microsoft.com/fwlink/p/?LinkId=397706)|설치 가능한 운영 체제:<br /> Windows 8.1 및 이전 버전<br /> Windows Server 2012 R2 및 이전 버전<br /> (전체 목록은 [시스템 요구 사항](~/docs/framework/get-started/system-requirements.md) 참조)|  
|**4.5.1**|[Microsoft .NET Framework 4.5.1 개발자 팩](http://go.microsoft.com/fwlink/?LinkId=324213)<br /><br /> Visual Studio 2012 또는 기타 IDE와 함께 사용할 경우|[4.5.1 웹 설치 관리자의 다운로드 페이지](http://go.microsoft.com/fwlink/p/?LinkId=310158)<br /><br /> [4.5.1 오프라인 설치 관리자의 다운로드 페이지](http://go.microsoft.com/fwlink/p/?LinkId=310159)|포함된 운영 체제:<br /> [!INCLUDE[win81](../../../includes/win81-md.md)]<br /> Windows Server 2012 R2<br /> [Visual Studio 2013](http://go.microsoft.com/fwlink/?LinkID=325532)<br /><br /> 설치 가능한 운영 체제:<br /> [!INCLUDE[win8](../../../includes/win8-md.md)] 및 이전 버전<br /> [!INCLUDE[winserver8](../../../includes/winserver8-md.md)] 및 이전 버전<br />(전체 목록은 [시스템 요구 사항](~/docs/framework/get-started/system-requirements.md) 참조)|  
|**4.5**|Visual Studio 2012에 포함됨<br /><br /> 또한 [Windows 8 SDK](http://msdn.microsoft.com/windows/hardware/hh852363)의 일부로 사용 가능|[4.5 웹 설치 관리자의 다운로드 페이지](http://go.microsoft.com/fwlink/p/?LinkId=245484)|포함된 운영 체제: <br /> [!INCLUDE[win8](../../../includes/win8-md.md)]<br /> [!INCLUDE[winserver8](../../../includes/winserver8-md.md)]<br /> Visual Studio 2012<br /><br /> 설치 가능한 운영 체제:<br /> Windows 7 및 이전 버전<br /> Windows Server 2008 SP2 및 이전 버전<br />(전체 목록은 [시스템 요구 사항](~/docs/framework/get-started/system-requirements.md) 참조)|  

지원되는 모든 플랫폼에서 .NET Framework의 특정 버전에 대한 **개발자 팩**을 설치할 수 있습니다.  

다음에서 **웹 또는 오프라인 설치 관리자**를 설치할 수 있습니다.  

- Windows 8.1 및 이전 버전

- Windows Server 2012 R2 및 이전 버전

전체 목록은 [시스템 요구 사항](~/docs/framework/get-started/system-requirements.md)을 참조하십시오.  

사용자와 개발자 모두를 위한 .NET Framework에 대한 일반적인 소개는 [시작](../get-started/index.md)을 참조하십시오. 응용 프로그램과 함께 .NET Framework를 배포하는 방법에 대한 자세한 내용은 [배포 가이드](~/docs/framework/deployment/deployment-guide-for-developers.md)를 참조하십시오. .NET Framework의 아키텍처 및 주요 기능에 대해 읽어보려면 [개요](~/docs/framework/get-started/overview.md)를 참조하십시오.  


## <a name="installation-choices"></a>설치 선택 사항
Visual Studio 또는 다른 개발 환경에서 최신 버전의 .NET Framework에 대한 개발을 위해 개발자 대상 팩을 설치하거나 앱 또는 컨트롤 배포를 위해 .NET Framework 재배포 가능 패키지를 다운로드합니다.  

## <a name="to-install-the-net-framework-developer-or-targeting-pack"></a>.NET Framework 개발자 또는 타기팅 팩을 설치하려면
.NET Framework 4.5.1 또는 4.5.2용 개발자 팩, [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]용 타기팅 팩 및 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], 4.6.2 또는 4.7용 개발자 팩에서는 Visual Studio와 같은 통합 개발 환경에서 사용할 수 있는 .NET Framework 4.5.1이나 4.5.2 또는 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1이나 4.6.2 또는 .NET Framework 4.7 참조 어셈블리, 언어 팩 및 IntelliSense 파일을 제공합니다. Visual Studio를 사용하는 경우 개발자 팩 또는 타기팅 팩은 설치된 .NET Framework 버전을 새 프로젝트를 만들 때 선택한 대상에도 추가합니다. 다음 개발자 팩 또는 타기팅 팩 중 하나를 선택합니다.
- [Microsoft .NET Framework 4.7 개발자 팩](http://go.microsoft.com/fwlink/?LinkId=825319)

- [Microsoft .NET Framework 4.6.2 개발자 팩](http://go.microsoft.com/fwlink/?LinkId=780617)

- [Microsoft .NET Framework 4.6.1 개발자 팩](http://go.microsoft.com/fwlink/?LinkId=690706)

- [Microsoft .NET Framework 4.6 타기팅 팩](http://go.microsoft.com/fwlink/?LinkId=528261)

- [.NET Framework 4.5.2 개발자 팩](http://go.microsoft.com/fwlink/?LinkId=397702)(버전 4.5.2를 Windows 8.1 또는 이전 버전, Visual Studio 2013, Visual Studio 2012 또는 기타 IDE에 설치하려는 경우)

- [.NET Framework 4.5.1 개발자 팩](http://go.microsoft.com/fwlink/?LinkId=324213)(버전 4.5.1을 Visual Studio 2012 또는 기타 IDE에 설치하려는 경우)

개발자 팩 다운로드 페이지에서 **다운로드**를 선택합니다. 그리고 **실행** 또는 **저장**을 선택하고 표시된 메시지의 지침을 따릅니다.  

## <a name="to-install-or-download-the-net-framework-redistributable"></a>.NET Framework 재배포 가능 패키지를 설치하거나 다운로드하려면
이러한 설치 관리자는 응용 프로그램에 대한 .NET Framework 구성 요소나 해당 버전의 .NET Framework를 대상으로 하는 컨트롤을 다운로드합니다. 이러한 구성 요소는 응용 프로그램이나 컨트롤이 실행되는 각 컴퓨터에 설치되어야 합니다. 두 설치 관리자 모두 재배포 가능하므로 응용 프로그램의 설치 프로그램에 포함할 수 있습니다.  

다운로드 페이지는 여러 언어로 제공되지만 대부분의 다운로드가 영어로만 제공됩니다. 추가 언어 지원을 사용하려면 언어 팩을 설치해야 합니다.  

다음 두 가지 재배포 가능 설치 유형을 사용할 수 있습니다.  

- **웹 설치 관리자**(웹 부트스트래퍼)는 설치 컴퓨터의 운영 체제와 일치하는 필수 구성 요소와 언어 팩을 웹에서 다운로드합니다. 이 패키지는 오프라인 설치 관리자보다 크기가 훨씬 작지만 지속적인 인터넷 연결이 필요합니다. [독립 실행형 언어 팩](#to-install-language-packs)을 다운로드하면 추가 언어 지원을 설치할 수 있습니다.

- **오프라인 설치 관리자**(독립 실행형 재배포 가능 패키지)에는 .NET Framework를 설치하는 데 필요한 구성 요소가 모두 포함되어 있지만 언어 팩은 포함되어 있지 않습니다. 이 다운로드는 웹 설치 관리자보다 크기가 큽니다. 오프라인 설치 관리자는 인터넷 연결이 필요 없습니다. 오프라인 설치 관리자를 실행한 후 [독립 실행형 언어 팩](#to-install-language-packs)을 다운로드하여 언어 지원을 설치할 수 있습니다. 지속적인 인터넷 연결이 제공된다는 보장이 없는 경우 오프라인 설치 관리자를 사용합니다.

웹 설치 관리자와 오프라인 설치 관리자 모두 x86 기반 컴퓨터 및 x64 기반 컴퓨터용으로 설계되었지만([시스템 요구 사항](~/docs/framework/get-started/system-requirements.md) 참조) Itanium 기반 컴퓨터는 지원하지 않습니다.  

Microsoft 다운로드 센터에서 .NET Framework를 설치하거나 다운로드하려면 다음 지침을 따르세요. 표에 있는 링크를 사용하여 .exe 파일을 직접 다운로드할 수도 있습니다.  

1. 설치하려는 .NET Framework 버전의 다운로드 페이지를 엽니다.

    - .NET Framework 4.7([웹 설치 관리자](http://go.microsoft.com/fwlink/?LinkId=825299) 또는 [오프라인 설치 관리자](http://go.microsoft.com/fwlink/p/?LinkId=825303))

    - .NET Framework 4.6.2([웹 설치 관리자](http://go.microsoft.com/fwlink/?LinkId=780597) 또는 [오프라인 설치 관리자](http://go.microsoft.com/fwlink/p/?LinkId=780601))

    - .NET Framework 4.6.1([웹 설치 관리자](http://go.microsoft.com/fwlink/?LinkId=671729) 또는 [오프라인 설치 관리자](http://go.microsoft.com/fwlink/p/?LinkId=671744))

    - .NET Framework 4.6([웹 설치 관리자](http://go.microsoft.com/fwlink/?LinkId=528259) 또는 [오프라인 설치 관리자](http://go.microsoft.com/fwlink/p/?LinkId=528233))

    - .NET Framework 4.5.2([웹 설치 관리자](http://go.microsoft.com/fwlink/p/?LinkId=397703) 또는 [오프라인 설치 관리자](http://go.microsoft.com/fwlink/p/?LinkId=397706))

    - .NET Framework 4.5.1([웹 설치 관리자](http://go.microsoft.com/fwlink/p/?LinkId=310158) 또는 [오프라인 설치 관리자](http://go.microsoft.com/fwlink/p/?LinkId=310159))

    - [.NET Framework 4.5](http://go.microsoft.com/fwlink/p/?LinkId=245484)

2. 다운로드 페이지의 언어를 선택합니다. 이 옵션을 선택해도 .NET Framework의 지역화된 리소스를 다운로드하지는 않습니다. 이는 다운로드 페이지에 표시되는 텍스트에만 영향을 줍니다.

3. **다운로드**를 선택합니다.

4. 메시지가 표시되면 시스템 아키텍처와 일치하는 다운로드를 선택한 후 **다음**을 선택합니다.

5. 다운로드 메시지가 표시되는 경우

    - .NET Framework를 컴퓨터에 설치할 경우 **실행**을 선택한 후 화면에 표시되는 메시지를 따릅니다.
        또는

    - 재배포를 위해 .NET Framework를 다운로드할 경우 **저장**을 선택한 후 화면에 표시되는 메시지를 따릅니다.

6. 추가 언어 리소스를 다운로드할 경우 다음 섹션의 지침에 따라 하나 이상의 언어 팩을 설치합니다.  

> [!NOTE]
> 설치하는 동안 문제가 발생하면 [문제 해결](~/docs/framework/install/troubleshoot-blocked-installations-and-uninstallations.md)을 참조하십시오.

 **설치 참고:**

- [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 및 4.5.2와 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2 및 4.7은 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]의 현재 위치 업데이트입니다.

- [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], 해당 포인트 릴리스, [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 해당 포인트 릴리스 및 .NET Framework 4.7이 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]를 대체합니다. [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]가 설치되어 있는 시스템에 이러한 버전을 설치하면 어셈블리가 교체됩니다.

- [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], 해당 포인트 릴리스, [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 해당 포인트 릴리스 또는 .NET Framework 4.7을 제거하면 기존 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 파일도 제거됩니다. [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)](으)로 돌아가려면 해당 프로그램과 업데이트를 다시 설치해야 합니다. ([.NET Framework 4 설치](http://go.microsoft.com/fwlink/p/?LinkId=230665) 참조)

- [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], 해당 포인트 릴리스, .NET Framework 4.6, 해당 포인트 릴리스 및 .NET Framework 4.7을 설치하려면 관리자 자격 증명이 있어야 합니다.

- .NET Framework 4.5 재배포 가능 패키지는 Microsoft에서 생성 및 서명된 파일의 디지털 서명이 중간에 만료되도록 한 디지털 서명의 부적절한 타임스탬프 관련 문제를 해결하기 위해 2012년 10월 9일 업데이트되었습니다. 이전에 2012년 8월 16일자 .NET Framework 4.5 재배포 가능 패키지를 설치한 경우 [Microsoft 다운로드 센터](http://go.microsoft.com/fwlink/p/?LinkId=245484)에서 최신 재배포 가능 패키지로 업데이트하는 것이 좋습니다. 이 문제에 대한 자세한 내용은 [Microsoft 보안 공지 2749655](http://technet.microsoft.com/security/advisory/2749655) 및 [기술 자료 문서 2770445](http://support.microsoft.com/kb/2770445)를 참조하십시오.  

## <a name="to-install-language-packs"></a>언어 팩을 설치하려면
언어 팩은 지원되는 언어에 대해 지역화된 리소스(예: 번역된 오류 메시지 및 UI 텍스트)를 포함하는 실행 파일입니다. 언어 팩을 설치하지 않는 경우 .NET Framework 오류 메시지 및 기타 텍스트는 영어로 표시됩니다.  웹 설치 관리자는 운영 체제와 일치하는 언어 팩을 자동으로 설치하지만 다른 언어 팩을 추가로 컴퓨터에 다운로드할 수 있습니다. 오프라인 설치 관리자에는 언어 팩이 포함되지 않습니다. 또한 언어 팩은 .NET Framework 4.7에 사용할 수 없습니다.

> [!IMPORTANT]
> 언어 팩에는 응용 프로그램을 실행하는 데 필요한 .NET Framework 구성 요소가 포함되지 않으므로 언어 팩을 설치하기 전에 웹 또는 오프라인 설치 관리자를 실행해야 합니다. 언어팩을 이미 설치한 경우 해당 언어 팩을 제거하고 .NET Framework를 설치한 다음 다시 언어 팩을 설치합니다.  

1. 설치된 .NET Framework 버전의 언어 팩 다운로드 페이지를 엽니다.

    - [.NET Framework 4.7 언어 팩](http://go.microsoft.com/fwlink/?LinkID=825306)

    - [.NET Framework 4.6.2 언어 팩](http://go.microsoft.com/fwlink/?LinkID=780604)

    - [.NET Framework 4.6.1 언어 팩](http://go.microsoft.com/fwlink/?LinkID=671747)

    - [.NET Framework 4.6 언어 팩](http://go.microsoft.com/fwlink/?LinkID=528314)

    - [.NET Framework 4.5.2 언어 팩](http://go.microsoft.com/fwlink/?LinkId=397701)

    - [.NET Framework 4.5.1 언어 팩](http://go.microsoft.com/fwlink/?LinkId=322101)

    - [.NET Framework 4.5 언어 팩](http://go.microsoft.com/fwlink/p/?LinkId=245451)

2. 언어 목록에서 다운로드하려는 언어를 선택하고 페이지가 해당 언어로 다시 로드될 때까지 몇 초 동안 기다립니다.

3. **다운로드**를 선택합니다.

다음 표에서는 지원되는 언어 목록을 보여 줍니다.

|언어|문화권|
|--------------|-------------|
|아랍어|ar|
|체코어|cs|
|덴마크어|da|
|네덜란드어|nl|
|핀란드어|fi|
|프랑스어|fr|
|독일어|de|
|그리스어|el|
|히브리어|he|
|헝가리어|hu|
|이탈리아어|it|
|일본어|ja|
|한국어|ko|
|노르웨이어|no|
|폴란드어|pl|
|포르투갈어(브라질)|pt-BR|
|포르투갈어(포르투갈)|pt-PT|
|러시아어|ru|
|중국어(간체)|zh-CHS|
|스페인어|es|
|스웨덴어|sv|
|중국어(번체)|zh-CHT|
|터키어|tr|
|영어(미국)|ko-KR|

## <a name="next-steps"></a>다음 단계

- .NET Framework를 처음 사용하는 경우 [개요](~/docs/framework/get-started/overview.md)에서 주요 개념과 구성 요소에 대한 소개를 참조하십시오.

- .NET Framework 4.7, [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.5.2, 4.5.1 및 4.5의 새로운 기능과 향상된 기능을 확인하려면 [새로운 기능](../../../docs/framework/whats-new/index.md)을 참조하세요.

- 응용 프로그램과 함께 .NET Framework를 배포하는 방법에 대한 자세한 정보는 [개발자를 위한 배포 가이드](~/docs/framework/deployment/deployment-guide-for-developers.md)를 참조하십시오.  

- 응용 프로그램과 함께 .NET Framework의 배포에 영향을 주는 변경 내용은 [.NET Framework 4.5를 설치하는 동안 시스템 다시 시작 줄이기](~/docs/framework/deployment/reducing-system-restarts.md)를 참조하십시오.

- 응용 프로그램을 .NET Framework 4에서 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 또는 해당 포인트 릴리스 중 하나로 마이그레이션하는 방법에 대한 자세한 내용은 [마이그레이션 가이드](~/docs/framework/migration-guide/index.md)를 참조하십시오.

- 온라인에서 .NET Framework 소스 코드를 검색하려면 [.NET Framework 참조 소스](http://referencesource.microsoft.com/)를 참조하십시오. 참조 소스는 [Github](https://github.com/Microsoft/referencesource)에서도 사용할 수 있습니다. [참조 소스를 다운로드](http://referencesource.microsoft.com/download.html)하여 오프라인에서 살펴보고, 디버그 시 소스(패치 및 업데이트 포함)를 단계별로 실행할 수 있습니다. 자세한 내용은 블로그 항목 [.NET 참조 소스의 새로운 디자인](http://blogs.msdn.com/b/dotnet/archive/2014/02/24/a-new-look-for-net-reference-source.aspx)을 참조하십시오.

## <a name="see-also"></a>참고 항목
 [개발자를 위한 배포 가이드](~/docs/framework/deployment/deployment-guide-for-developers.md)   
 [관리자를 위한 배포 가이드](~/docs/framework/deployment/guide-for-administrators.md)   
 [Windows 8 이상 버전에 .NET Framework 3.5 설치](~/docs/framework/install/net-framework-3-5-on-windows-8-plus.md)   
 [문제 해결](~/docs/framework/install/troubleshoot-blocked-installations-and-uninstallations.md)
