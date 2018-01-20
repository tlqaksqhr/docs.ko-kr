---
title: "Windows Forms의 보안 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code access security [Windows Forms], Windows Forms
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms], about security
- access control [Windows Forms], Windows Forms
ms.assetid: 4810dc9f-ea23-4ce1-8ea1-657f0ff1d820
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e56ae77a36ce0000fd518a3324ab5e5b8409d1d4
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="security-in-windows-forms-overview"></a>Windows Forms의 보안 개요
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 릴리스 이전에는 사용자 컴퓨터에서 실행되는 모든 코드가 컴퓨터의 사용자와 동일한 리소스 액세스 권한을 가졌습니다. 예를 들어 사용자가 파일 시스템에 액세스할 수 있는 경우 코드에서 파일 시스템에 액세스할 수 있었습니다. 사용자가 데이터베이스에 액세스할 수 있는 경우 코드에서 해당 데이터베이스에 액세스할 수 있었습니다. 이러한 권한 또는 사용 권한은 사용자가 명시적으로 로컬 컴퓨터에 설치한 실행 파일의 코드에는 적합할 수 있지만 인터넷 또는 로컬 인트라넷에서 들어오는 잠재적 악성 코드에는 적합하지 않을 수 있습니다. 이 코드는 권한 없이 사용자의 컴퓨터 리소스에 액세스할 수 없어야 합니다.  
  
 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서는 코드에서 보유한 권한과 사용자가 보유한 권한을 구분할 수 있게 해주는 코드 액세스 보안이라는 인프라가 도입되었습니다. 기본적으로 인터넷 및 인트라넷에서 들어오는 코드는 부분 신뢰에서만 실행할 수 있습니다. 부분 신뢰에서는 응용 프로그램에 일련의 제한이 적용됩니다. 특히, 응용 프로그램의 로컬 하드 디스크 액세스가 제한되며 비관리 코드를 실행할 수 없습니다. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서는 코드의 ID, 출처, [강력한 이름 어셈블리](../../../docs/framework/app-domains/strong-named-assemblies.md)가 있는지 여부, 인증서로 서명되었는지 여부 등에 따라 해당 코드가 액세스할 수 있는 리소스를 제어합니다.  
  
 Windows Forms 응용 프로그램을 배포하는 데 사용하는 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 기술은 부분 신뢰, 완전 신뢰 또는 높은 권한으로 부분 신뢰에서 실행되는 응용 프로그램을 쉽게 개발할 수 있도록 도와줍니다. [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]에서는 응용 프로그램이 책임 있는 방식으로 로컬 사용자로부터 완전 신뢰 또는 높은 권한을 요청할 수 있도록 권한 상승 및 신뢰할 수 있는 응용 프로그램 배포와 같은 기능을 제공합니다.  
  
## <a name="understanding-security-in-the-net-framework"></a>.NET Framework의 보안 이해  
 코드 액세스 보안을 통해 코드 발생 위치 및 코드 ID의 다른 측면에 따라 다양한 수준으로 코드를 신뢰할 수 있습니다. 공용 언어 런타임에서 보안 정책을 결정하는 데 사용하는 증거에 대한 자세한 내용은 [증거](http://msdn.microsoft.com/library/64ceb7c8-a0b4-46c4-97dc-6c22da0539da)를 참조하세요. 악성 코드로부터 컴퓨터 시스템을 보호하고 의도적으로 또는 실수로 보안이 손상되지 않도록 신뢰할 수 있는 코드를 보호합니다. 코드 액세스 보안을 통해 응용 프로그램에 필요한 권한만 지정할 수 있으므로 응용 프로그램이 수행할 수 있는 작업에 대한 제어도 강화됩니다. 코드 액세스 보안은 코드에서 단일 코드 액세스 보안 권한 검사를 수행하지 않는 경우에도 공용 언어 런타임을 대상으로 하는 모든 관리 코드에 영향을 줍니다. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]의 보안에 대한 자세한 내용은 [주요 보안 개념](../../../docs/standard/security/key-security-concepts.md) 및 [코드 액세스 보안 기본 사항](../../../docs/framework/misc/code-access-security-basics.md)을 참조하세요.  
  
 사용자가 웹 서버 또는 파일 공유에서 직접 Windows Forms 실행 파일을 실행하는 경우 응용 프로그램에 부여되는 신뢰 수준은 코드가 상주하는 위치 및 시작 방법에 따라 달라집니다. 응용 프로그램이 실행되면 자동으로 평가되고 공용 언어 런타임으로부터 명명된 권한 집합을 받습니다. 기본적으로 로컬 컴퓨터의 코드에는 완전 신뢰 권한 집합이 부여되고, 로컬 네트워크의 코드에는 로컬 인트라넷 권한 집합이 부여되며, 인터넷의 코드에는 인터넷 권한 집합이 부여됩니다.  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 버전 1.0 서비스 팩 1과 서비스 팩 2에서는 인터넷 영역 코드 그룹이 Nothing 권한 집합을 받습니다. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]의 다른 모든 릴리스에서는 인터넷 영역 코드 그룹이 인터넷 권한 집합을 받습니다.  
>   
>  각 권한 집합에 부여되는 기본 권한은 [기본 보안 정책](http://msdn.microsoft.com/library/2c086873-0894-4f4d-8f7e-47427c1a3b55) 항목에 나열됩니다. 받는 권한에 따라 응용 프로그램이 올바르게 실행되거나 보안 예외를 생성합니다.  
>   
>  대부분의 Windows Forms 응용 프로그램은 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]를 사용하여 배포됩니다. [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 배포를 생성하는 데 사용되는 도구는 앞에서 설명한 것과 다른 보안 기본값을 사용합니다. 자세한 내용은 다음 설명을 참조하세요.  
  
 보안 정책을 수정할 수 있기 때문에 응용 프로그램에 부여되는 실제 권한은 기본값과 다를 수 있습니다. 즉, 컴퓨터에 따라 응용 프로그램의 권한이 다를 수 있습니다.  
  
## <a name="developing-a-more-secure-windows-forms-application"></a>보다 안전한 Windows Forms 응용 프로그램 개발  
 보안은 응용 프로그램 개발의 모든 단계에서 중요합니다. 먼저 [보안 코딩 지침](../../../docs/standard/security/secure-coding-guidelines.md)을 검토하고 따릅니다.  
  
 그런 다음 응용 프로그램을 완전 신뢰로 실행해야 하는지 여부 또는 부분 신뢰로 실행해야 하는지 여부를 결정합니다. 완전 신뢰에서 응용 프로그램을 실행하면 로컬 컴퓨터의 리소스에 더 쉽게 액세스할 수 있지만 보안 코딩 지침 항목에 따라 엄격하게 응용 프로그램을 디자인 및 개발하지 않을 경우 응용 프로그램 및 해당 사용자가 높은 보안 위험에 노출됩니다. 부분 신뢰로 응용 프로그램을 실행하면 보다 안전한 응용 프로그램을 쉽게 개발할 수 있고 많은 위험이 감소하지만 특정 기능을 구현하는 방법에서 추가 계획이 필요합니다.  
  
 부분 신뢰(즉, 인터넷 또는 로컬 인트라넷 권한 집합)를 선택하는 경우 이 환경에서 원하는 응용 프로그램의 동작 방식을 결정합니다. Windows Forms는 부분 신뢰 환경에서 기능을 구현하는 보다 안전한 대체 방법을 제공합니다. 데이터 액세스와 같은 응용 프로그램의 특정 부분을 부분 신뢰 및 완전 신뢰 환경 둘 다에 대해 다르게 디자인 및 작성할 수 있습니다. 응용 프로그램 설정과 같은 일부 Windows Forms 기능은 부분 신뢰로 작동하도록 설계되었습니다. 자세한 내용은 [응용 프로그램 설정 개요](../../../docs/framework/winforms/advanced/application-settings-overview.md)를 참조하세요.  
  
 응용 프로그램에 부분 신뢰에서 허용하는 것보다 많은 권한이 필요하지만 완전 신뢰로 실행하지 않으려는 경우 필요한 추가 권한만 어설션하는 동시에 부분 신뢰로 실행할 수 있습니다. 예를 들어 부분 신뢰로 실행하지만 사용자의 파일 시스템에 있는 디렉터리에 대한 읽기 전용 액세스 권한을 응용 프로그램에 부여해야 경우 해당 디렉터리에 대해서만 <xref:System.Security.Permissions.FileIOPermission>을 요청할 수 있습니다. 올바르게 사용할 경우 이 접근 방식은 응용 프로그램의 기능을 증가시키며 사용자의 보안 위험을 최소화할 수 있습니다.  
  
 부분 신뢰로 실행되는 응용 프로그램을 개발할 때는 응용 프로그램이 실행해야 하는 권한 및 응용 프로그램이 선택적으로 사용할 수 있는 권한을 추적합니다. 모든 권한을 알고 난 후 응용 프로그램 수준에서 권한에 대한 선언적 요청을 해야 합니다. 권한을 요청하면 응용 프로그램에 필요한 권한 및 구체적으로 원하지 않는 권한에 대해 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 런타임에 알립니다. 권한 요청에 대한 자세한 내용은 [권한 요청](http://msdn.microsoft.com/library/0447c49d-8cba-45e4-862c-ff0b59bebdc2)을 참조하세요.  
  
 선택적 권한을 요청할 때는 응용 프로그램에서 부여되지 않은 권한이 필요한 작업을 수행하는 경우 생성되는 보안 예외를 처리해야 합니다. <xref:System.Security.SecurityException>을 적절히 처리하면 응용 프로그램이 계속 작동할 수 있습니다. 응용 프로그램은 예외를 사용하여 사용자에 대해 기능을 사용할 수 없도록 설정할지 여부를 결정할 수 있습니다. 예를 들어 필요한 파일 권한이 부여되지 않은 경우 응용 프로그램에서 **저장** 메뉴 옵션을 사용할 수 없습니다.  
  
 적절한 권한을 모두 어설션했는지 확인하기 어려운 경우도 있습니다. 예를 들어 화면에서 무해한 것처럼 보이는 메서드 호출이 실행 중 특정 지점에서 파일 시스템에 액세스할 수도 있습니다. 필요한 모든 권한으로 응용 프로그램을 배포하지 않을 경우 데스크톱에서 디버그할 때는 정상적으로 테스트되지만 배포 시 실패할 수 있습니다. [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] SDK 및 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]에는 모두 응용 프로그램에 필요한 권한을 계산하기 위한 도구인 MT.exe 명령줄 도구와 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]의 권한 계산 기능이 각각 포함되어 있습니다.  
  
 다음 항목에서는 추가 Windows Forms 보안 기능을 설명합니다.  
  
|항목|설명|  
|-----------|-----------------|  
|-   [Windows Forms의 파일 및 데이터 액세스 추가 보안](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)|부분 신뢰 환경에서 파일 및 데이터에 액세스하는 방법을 설명합니다.|  
|-   [Windows Forms의 인쇄 추가 보안](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)|부분 신뢰 환경에서 인쇄 기능에 액세스하는 방법을 설명합니다.|  
|-   [Windows Forms의 추가 보안 고려 사항](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)|창 조작 수행, 클립보드 사용 및 부분 신뢰 환경에서 비관리 코드 호출을 설명합니다.|  
  
-  
  
### <a name="deploying-an-application-with-the-appropriate-permissions"></a>적절한 권한으로 응용 프로그램 배포  
 클라이언트 컴퓨터에 Windows Forms 응용 프로그램을 배포하는 가장 일반적인 방법은 응용 프로그램에서 실행해야 하는 모든 구성 요소를 설명하는 배포 기술인 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]를 사용하는 것입니다. [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]는 매니페스트라는 XML 파일을 사용하여 응용 프로그램을 구성하는 어셈블리 및 파일과 응용 프로그램에 필요한 권한을 설명합니다.  
  
 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)]에는 클라이언트 컴퓨터에서 높은 권한을 요청하는 두 가지 기술이 있습니다. 두 기술은 모두 Authenticode 인증서를 사용합니다. 인증서는 응용 프로그램이 신뢰할 수 있는 소스에서 제공되었다는 일부 보증을 사용자에게 제공합니다.  
  
 다음 표에서는 이러한 기술을 설명합니다.  
  
|높은 권한 기술|설명|  
|------------------------------------|-----------------|  
|권한 상승|응용 프로그램을 처음 실행할 때 사용자에게 보안 대화 상자를 표시합니다. **권한 상승** 대화 상자는 사용자가 추가 신뢰를 부여할지 여부에 대해 합리적인 결정을 내릴 수 있도록 응용 프로그램을 게시한 사람을 사용자에게 알립니다.|  
|신뢰할 수 있는 응용 프로그램 배포|시스템 관리자가 클라이언트 컴퓨터에서 게시자 Authenticode 인증서의 일회성 설치를 수행해야 합니다. 이때부터 인증서로 서명된 응용 프로그램은 신뢰할 수 있는 것으로 간주되며, 추가 확인 메시지 없이 로컬 컴퓨터에서 완전 신뢰로 실행될 수 있습니다.|  
  
 선택하는 기술은 배포 환경에 따라 달라집니다. 자세한 내용은 [ClickOnce 배포 전략 선택](/visualstudio/deployment/choosing-a-clickonce-deployment-strategy)을 참조하세요.  
  
 기본적으로 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 또는 [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] SDK 도구(Mage.exe 및 MageUI.exe) 중 하나를 사용하여 배포된 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 응용 프로그램은 완전히 신뢰할 수 있는 클라이언트 컴퓨터에서 실행되도록 구성됩니다. 부분 신뢰를 사용하거나 일부 추가 권한만 사용하여 응용 프로그램을 배포하는 경우 이 기본값을 변경해야 합니다. 이 작업을 배포를 구성할 때 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 또는 [!INCLUDE[dnprdnlong](../../../includes/dnprdnlong-md.md)] SDK 도구 MageUI.exe를 사용하여 수행할 수 있습니다. MageUI.exe를 사용하는 방법에 대한 자세한 내용은 연습: 명령줄에서 ClickOnce 응용 프로그램 배포를 참조하세요.  또한 [방법: ClickOnce 응용 프로그램에 대한 사용자 지정 권한 설정](http://msdn.microsoft.com/library/hafybdaa\(v=vs.110\)) 또는 [방법: ClickOnce 응용 프로그램에 대한 사용자 지정 권한 설정](http://msdn.microsoft.com/library/hafybdaa\(v=vs.120\))을 참조하세요.  
  
 [!INCLUDE[ndptecclick](../../../includes/ndptecclick-md.md)] 및 권한 상승의 보안 측면에 대한 자세한 내용은 [ClickOnce 응용 프로그램 보안](/visualstudio/deployment/securing-clickonce-applications)을 참조하세요. 신뢰할 수 있는 응용 프로그램 배포에 대한 자세한 내용은 [신뢰할 수 있는 응용 프로그램 배포 개요](/visualstudio/deployment/trusted-application-deployment-overview)를 참조하세요.  
  
### <a name="testing-the-application"></a>응용 프로그램 테스트  
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]를 사용하여 Windows Forms 응용 프로그램을 배포한 경우 개발 환경에서 부분 신뢰 또는 제한된 권한 집합으로 디버깅을 사용할 수 있습니다.  또한 [방법: 제한된 권한으로 ClickOnce 응용 프로그램 디버그](http://msdn.microsoft.com/library/593zkfdf\(v=vs.110\)) 또는 [방법: 제한된 권한으로 ClickOnce 응용 프로그램 디버그](http://msdn.microsoft.com/library/593zkfdf\(v=vs.120\))를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 보안](../../../docs/framework/winforms/windows-forms-security.md)  
 [코드 액세스 보안 기본 사항](../../../docs/framework/misc/code-access-security-basics.md)  
 [ClickOnce 보안 및 배포](/visualstudio/deployment/clickonce-security-and-deployment)  
 [신뢰할 수 있는 응용 프로그램 배포 개요](/visualstudio/deployment/trusted-application-deployment-overview)  
 [Mage.exe(매니페스트 생성 및 편집 도구)](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md)  
 [MageUI.exe(매니페스트 생성 및 편집 도구, 그래픽 클라이언트)](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)
