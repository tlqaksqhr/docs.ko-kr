---
title: "방법: Windows 서비스 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, creating
- templates, Windows Service
ms.assetid: 0f5e2cbb-d95d-477c-b2b5-4b990e6b86ff
caps.latest.revision: "18"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 7d93f8543b9e6e370827f5a666315d562e28ee76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-windows-services"></a>방법: Windows 서비스 만들기
서비스를 만들 때 호출 하는 Visual Studio 프로젝트 템플릿을 사용할 수 있습니다 **Windows 서비스**합니다. 이 템플릿은 적절한 클래스 및 네임스페이스를 참조하고, 서비스의 기본 클래스에서 상속을 설정하고, 개발자가 재정의할 가능성이 높은 여러 메서드를 재정의하여 대부분의 작업을 자동으로 수행합니다.  
  
> [!WARNING]
>  Visual Studio Express 버전에서는 Windows 서비스 프로젝트 템플릿을 사용할 수 없습니다.  
  
 작동하는 서비스를 만들려면 최소한 다음 작업을 수행해야 합니다.  
  
-   <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 속성을 설정합니다.  
  
-   서비스 응용 프로그램에 필요한 설치 관리자를 만듭니다.  
  
-   <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 메서드의 코드를 재정의 및 지정하여 서비스 동작 방식을 사용자 지정합니다.  
  
### <a name="to-create-a-windows-service-application"></a>Windows 서비스 응용 프로그램을 만들려면  
  
1.  만들기는 **Windows 서비스** 프로젝트.  
  
    > [!NOTE]
    >  서비스 템플릿을 사용 하지 않고 작성 방법에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 프로그래밍 방식으로 서비스 작성](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)합니다.  
  
2.  에 **속성** 창의 설정에서 <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 서비스에 대 한 속성입니다.  
  
     ![ServiceName 속성을 설정 합니다. ] (../../../docs/framework/windows-services/media/windowsservice-servicename.PNG "WindowsService_ServiceName")  
  
    > [!NOTE]
    >  <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 속성의 값은 항상 설치 관리자 클래스에 기록된 이름과 일치해야 합니다. 이 속성을 변경하는 경우에는 설치 관리자 클래스의 <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 속성도 업데이트해야 합니다.  
  
3.  다음 속성을 설정하여 서비스 작동 방식을 결정합니다.  
  
    |속성|설정|  
    |--------------|-------------|  
    |<xref:System.ServiceProcess.ServiceBase.CanStop%2A>|서비스가 실행 중지 요청을 수락함을 나타내려면 `True`로 설정하고 서비스 중지를 차단하려면 `false`로 설정합니다.|  
    |<xref:System.ServiceProcess.ServiceBase.CanShutdown%2A>|서비스가 활성화되어 있는 컴퓨터가 종료될 때 서비스에서 알림을 수신하여 `True` 프로시저를 호출할 수 있도록 설정할 것임을 나타내려면 <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A>로 설정합니다.|  
    |<xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A>|서비스가 실행 일시 중지 또는 다시 시작 요청을 수락함을 나타내려면 `True`로 설정하고 서비스 일시 중지 및 다시 시작을 차단하려면 `false`로 설정합니다.|  
    |<xref:System.ServiceProcess.ServiceBase.CanHandlePowerEvent%2A>|`True`서비스 컴퓨터의 전원 상태에 대 한 변경 통지를 처리할 수 있습니다. `false` 로 설정 하면 서비스에서 이러한 변경 내용이 통보 되 고 있습니다.|  
    |<xref:System.ServiceProcess.ServiceBase.AutoLog%2A>|서비스에서 작업을 수행할 때 응용 프로그램 이벤트 로그에 정보 항목을 기록하려면 `True`로 설정하고 이 기능을 사용하지 않도록 설정하려면 `false`로 설정합니다. 자세한 내용은 참조 [하는 방법: 로그 정보에 대 한 서비스](../../../docs/framework/windows-services/how-to-log-information-about-services.md)합니다. **참고:** 기본적으로 <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> 로 설정 된 `true`합니다.|  
  
    > [!NOTE]
    >  때 <xref:System.ServiceProcess.ServiceBase.CanStop%2A> 또는 <xref:System.ServiceProcess.ServiceBase.CanPauseAndContinue%2A> 로 설정 `false`, **서비스 제어 관리자** 중지, 일시 중지 하거나 서비스를 계속 하려면 해당 메뉴 옵션은 사용 하지 않도록 설정 됩니다.  
  
4.  코드 편집기에 액세스하여 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 및 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 프로시저에 대해 원하는 처리를 입력합니다.  
  
5.  기능을 정의할 다른 메서드를 재정의합니다.  
  
6.  서비스 응용 프로그램에 필요한 설치 관리자를 추가합니다. 자세한 내용은 참조 [하는 방법: 서비스 응용 프로그램 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)합니다.  
  
7.  선택 하 여 프로젝트를 빌드해야 **솔루션 빌드** 에서 **빌드** 메뉴.  
  
    > [!NOTE]
    >  F5 키를 눌러 프로젝트를 실행하지 마세요. 서비스 프로젝트는 이러한 방식으로 실행할 수 없습니다.  
  
8.  서비스를 설치합니다. 자세한 내용은 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [방법: 프로그래밍 방식으로 서비스 작성](../../../docs/framework/windows-services/how-to-write-services-programmatically.md)  
 [방법: 서비스 응용 프로그램에 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [방법: 서비스에 대한 정보 로깅](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [방법: 서비스 시작](../../../docs/framework/windows-services/how-to-start-services.md)  
 [방법: 서비스에 대한 보안 컨텍스트 지정](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)  
 [방법: 서비스 설치 및 제거](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [연습: 구성 요소 디자이너에서 Windows 서비스 응용 프로그램 만들기](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
