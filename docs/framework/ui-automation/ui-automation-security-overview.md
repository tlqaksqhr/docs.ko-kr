---
title: "UI 자동화 보안 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, security model
- security model, UI Automation
ms.assetid: 1d853695-973c-48ae-b382-4132ae702805
caps.latest.revision: "23"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: ee3847164ecdc9b9868d806b5a1394ffca0bbd31
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ui-automation-security-overview"></a>UI 자동화 보안 개요
> [!NOTE]
>  이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](http://go.microsoft.com/fwlink/?LinkID=156746)를 참조하세요.  
  
 이 개요에서는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 의 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)]에 대한 보안 모델을 설명합니다.  
  
<a name="User_Account_Control"></a>   
## <a name="user-account-control"></a>사용자 계정 컨트롤  
 보안은 [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] 의 중요 사항이며, 혁신적 기능 중에는 사용자가 더 높은 권한이 필요한 응용 프로그램과 서비스를 실행할 수 없도록 차단되지 않고 표준(비관리자) 사용자로 실행할 수 있는 기능이 있습니다.  
  
 [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)]에서는 대부분의 응용 프로그램에 표준 또는 관리 토큰이 제공됩니다. 응용 프로그램을 관리 응용 프로그램으로 식별할 수 없는 경우 기본적으로 표준 응용 프로그램으로 시작됩니다. 관리 응용 프로그램으로 식별된 응용 프로그램을 시작하기 전에 [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] 에서 높은 권한으로 응용 프로그램을 실행할 것인지 묻는 메시지를 사용자에게 표시합니다. 관리자 자격 증명이 필요한 응용 프로그램 또는 시스템 구성 요소가 실행 권한을 요청할 때까지 관리자가 표준 사용자로 실행되므로 사용자가 로컬 관리자 그룹의 멤버인 경우에도 동의 확인 프롬프트가 기본적으로 표시됩니다.  
  
<a name="Tasks_Requiring_Higher_Privileges"></a>   
## <a name="tasks-requiring-higher-privileges"></a>더 높은 권한이 필요한 작업  
 사용자가 관리자 권한이 필요한 작업을 수행하려고 [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] 에서 사용자에게 계속할 것인지 묻는 대화 상자를 표시합니다. 이 대화 상자는 악성 소프트웨어가 사용자 입력을 시뮬레이션할 수 없도록 크로스 프로세스 통신으로부터 보호됩니다. 마찬가지로, 데스크톱 로그온 화면은 일반적으로 다른 프로세스에서 액세스할 수 없습니다.  
  
 UI 자동화 클라이언트는 더 높은 권한 수준에서 실행 중일 수도 있는 다른 프로세스와 통신해야 합니다. 클라이언트가 일반적으로 다른 프로세스에 표시되지 않는 시스템 대화 상자에 액세스해야 할 수도 있습니다. 따라서 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클라이언트는 시스템에서 신뢰되어야 하며 특수 권한으로 실행되어야 합니다.  
  
 더 높은 권한 수준에서 실행 중인 응용 프로그램과 통신할 수 있도록 신뢰되려면 응용 프로그램에 서명해야 합니다.  
  
<a name="Manifest_Files"></a>   
## <a name="manifest-files"></a>매니페스트 파일  
 보호된 시스템 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]에 액세스할 수 있으려면 매니페스트 파일에 특수 특성이 포함된 매니페스트 파일로 응용 프로그램을 빌드해야 합니다. 이 `uiAccess` 특성은 다음과 같이 `requestedExecutionLevel` 태그에 포함됩니다.  
  
 `<trustInfo xmlns="urn:0073chemas-microsoft-com:asm.v3">`  
  
 `<security>`  
  
 `<requestedPrivileges>`  
  
 `<requestedExecutionLevel`  
  
 `level="highestAvailable"`  
  
 `UIAccess="true" />`  
  
 `</requestedPrivileges>`  
  
 `</security>`  
  
 `</trustInfo>`  
  
 이 코드에서 `level` 특성의 값은 예제일 뿐입니다.  
  
 `UIAccess` 는 기본적으로 "false"입니다. 즉, 특성을 생략하거나 어셈블리에 대한 매니페스트가 없을 경우 응용 프로그램이 보호된 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]에 액세스할 수 없습니다.  
  
 [!INCLUDE[TLA#tla_longhorn2](../../../includes/tlasharptla-longhorn2-md.md)] 보안, 응용 프로그램 서명 및 어셈블리 매니페스트를 만드는 방법에 대한 자세한 내용은  [MSDN](http://msdn.microsoft.com/library/default.asp?url=/library/dnlong/html/AccProtVista.asp)의 "최소 권한 환경에서 응용 프로그램에 대한 개발자 모범 사례 및 지침"을 참조하세요.
