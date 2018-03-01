---
title: "Windows 서비스 응용 프로그램 소개"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ServiceController
helpviewer_keywords:
- Windows Service applications, deploying
- OnStop method
- OnPause method
- services, about services
- Service class, Windows Service applications
- framework services, creating services
- ServiceController components, about Windows services
- Win32OwnProcess service type
- services, lifetime
- OnContinue method
- Windows Service applications, about Windows Service applications
- services, states
- service states
- WaitForStatus method
- Win32ShareProcess service type
- Windows Service applications, lifetime
ms.assetid: 1b1b5e67-3ff3-40c0-8154-322cfd6ef0ae
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 613107a13820ad71b854dcba93f21c41f2a5fa5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="introduction-to-windows-service-applications"></a>Windows 서비스 응용 프로그램 소개
Microsoft Windows 서비스, 이전의 NT 서비스를 사용 하 여 자신의 Windows 세션에서 실행 되 긴 실행 가능한 응용 프로그램을 만들 수 있습니다. 이러한 서비스 자동으로 시작 되는 컴퓨터를 부팅할 때 일시 중지 및 다시 시작 하 고 사용자 인터페이스를 표시 하지 않습니다. 이러한 기능은 동일한 컴퓨터에서 작업 하는 다른 사용자와 방해 하지 않는 장기 실행 기능이 필요할 때마다 또는 서버에서 사용 하기에 적합 서비스를 확인 합니다. 로그온 한 사용자와에서 다른 특정 사용자 계정 또는 기본 컴퓨터 계정의 보안 컨텍스트에서 서비스를 실행할 수 있습니다. 서비스 및 Windows 세션에 대 한 자세한 내용은 Windows SDK 설명서를 참조 합니다.  
  
 서비스로 설치 하는 응용 프로그램을 만들어 서비스를 쉽게 만들 수 있습니다. 예를 들어 성능 카운터 데이터를 모니터링 하 고 임계값에 반응 한다고 가정 합니다. 성능 카운터 데이터를 수신 하는 Windows 서비스 응용 프로그램을 작성 하 고, 응용 프로그램을 배포 하 고, 데이터 수집 및 분석을 시작할 수 없습니다.  
  
 Microsoft Visual Studio 프로젝트와 서비스를 만들려면 명령에서 작업을 제어 하는 코드 내에서 정의 게 수 서비스와 해당 명령의 받을 때 어떤 작업을 수행 해야 합니다. 서비스에 보낼 수 있는 명령에는 서비스를 중지 및 시작, 일시 중지, 다시 시작 또한 사용자 지정 명령을 실행할 수 있습니다.  
  
 만들고 응용 프로그램 빌드 후 명령줄 유틸리티 InstallUtil.exe를 실행 하는 서비스의 실행 파일 경로 전달 하 여 설치할 수 있습니다. 사용할 수 있습니다는 **서비스 제어 관리자** 를 시작, 중지, 일시 중지, 계속 및 서비스를 구성 합니다. 여러에서 동일한 작업을 수행할 수 있습니다는 **서비스** 노드에서 **서버 탐색기** 또는 사용 하 여는 <xref:System.ServiceProcess.ServiceController> 클래스입니다.  
  
## <a name="service-applications-vs-other-visual-studio-applications"></a>서비스 응용 프로그램 및입니다. 다른 Visual Studio 응용 프로그램  
 여러 가지 방법으로 여러 가지 다른 프로젝트 형식 다르게에서 서비스 응용 프로그램 기능:  
  
-   컴파일된 실행 파일을 서비스 응용 프로그램 프로젝트를 만듭니다는 의미 있는 방식으로 작동 하기 전에 서버에 설치 해야 합니다. 디버깅 또는 f5 키 또는 F11 키를 눌러 서비스 응용 프로그램을 실행할 수 없습니다. 해당 코드에 서비스 또는 단계를 즉시 실행할 수 없습니다. 대신, 설치 및 서비스를 시작 하 고 해야 다음 서비스의 프로세스에 디버거를 연결 합니다. 자세한 내용은 참조 [하는 방법: Windows 서비스 응용 프로그램 디버그](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)합니다.  
  
-   일부 유형의 프로젝트와 달리 서비스 응용 프로그램에 대 한 설치 구성 요소를 만들어야 합니다. 설치 구성 요소 설치 및 서버에서 서비스를 등록 및 windows 서비스에 대 한 항목을 만들 **서비스 제어 관리자**합니다. 자세한 내용은 참조 [하는 방법: 서비스 응용 프로그램 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)합니다.  
  
-   `Main` 메서드 서비스 응용 프로그램 서비스에 대 한 실행 명령을 프로젝트 실행 해야 합니다를 포함 합니다. `Run` 메서드 로드에 서비스는 **서비스 제어 관리자** 적절 한 서버에 있습니다. 사용 하는 경우는 **Windows 서비스** 프로젝트 템플릿을이 메서드를 자동으로 작성 됩니다. 서비스를 로드 하지 않은 서비스를 시작 하는와 같은 작업 메모 합니다. 서비스 "수명" 아래에 대 한 자세한 내용은 참조 하십시오.  
  
-   Windows 서비스 응용 프로그램 로그온 한 사용자의 대화형 스테이션 보다 다양 한 창 스테이션에 실행합니다. 윈도우 스테이션은 클립보드, 전역 원자 집합 및 데스크톱 개체 그룹을 포함 하는 보안 개체입니다. Windows 서비스의 스테이션 스테이션은 대화형 없기 때문에 서비스 응용 프로그램을 볼 수 없습니다 하며 프로그램 응답 하지 않을 수 있습니다는 Windows 내 대화 상자에서 발생 합니다. 마찬가지로, 오류 메시지 사용자 인터페이스에서 발생 되지 않고 Windows 이벤트 로그에 기록 됩니다.  
  
     .NET Framework에서 지 원하는 Windows 서비스 클래스는 대화형 거래소, 즉, 로그인 한 사용자와의 상호 작용을 지원 하지 않습니다. 또한.NET Framework는 스테이션 및 데스크톱을 나타내는 클래스를 포함 하지 않습니다. Windows 서비스에 다른 스테이션와 상호 작용 해야, 관리 되지 않는 Windows API에 액세스 해야 합니다. 자세한 내용은 Windows SDK 설명서를 참조 합니다.  
  
     시나리오를 포함 하도록 이러한 만큼 없는 로그온된 한 사용자 또는 사용자가 데스크톱 개체에 대 한 예기치 않은 집합이 되 고 서비스 사용자 또는 다른 스테이션을 신중 하 게 디자인 해야 Windows와의 상호 작용 합니다. 일부 경우에 더 적절 한 사용자의 제어를 받으며 실행 하는 Windows 응용 프로그램을 작성할 수 있습니다.  
  
-   Windows 서비스 응용 프로그램의 보안 컨텍스트에서 실행 하 고 설치 된 Windows 컴퓨터에 사용자가 로그인 하기 전에 시작 됩니다. 내에서 서비스를 실행할 사용자 계정을 신중 하 게 계획 해야 시스템 계정에서 실행 되는 서비스에 더 많은 사용 권한 및 사용자 계정 보다 권한이 있습니다.  
  
## <a name="service-lifetime"></a>서비스 수명  
 서비스 수명 중에 여러 내부 상태를 거칩니다. 첫째, 서비스가 실행 될 시스템에 설치 되어 있습니다. 이 프로세스는 서비스 프로젝트에 대 한 설치 관리자를 실행 하 고 서비스에 로드 된 **서비스 제어 관리자** 해당 컴퓨터에 대 한 합니다. **서비스 제어 관리자** 는 서비스 관리를 위해 Windows에서 제공 하는 중앙 유틸리티입니다.  
  
 서비스를 로드 한 다음 시작 되어야 합니다. 서비스를 시작 작동 될 수 있습니다. 서비스를 시작할 수는 **서비스 제어 관리자**에서 **서버 탐색기**, 또는 호출 하 여 코드의 <xref:System.ServiceProcess.ServiceController.Start%2A> 메서드. <xref:System.ServiceProcess.ServiceController.Start%2A> 처리 응용 프로그램의를 전달 하는 메서드 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드 하 고 여기에 정의 된 있는 모든 코드를 처리 합니다.  
  
 실행 중인 서비스는 컴퓨터가 종료 되거나 중지 되거나 일시 중지 됩니다 때까지 무한정이 상태에 있을 수 있습니다. 서비스의 세 가지 기본 상태 중 하나에 있을 수 있습니다: <xref:System.ServiceProcess.ServiceControllerStatus.Running>, <xref:System.ServiceProcess.ServiceControllerStatus.Paused>, 또는 <xref:System.ServiceProcess.ServiceControllerStatus.Stopped>합니다. 서비스 보류 중인 명령의 상태를 보고할 수도: <xref:System.ServiceProcess.ServiceControllerStatus.ContinuePending>, <xref:System.ServiceProcess.ServiceControllerStatus.PausePending>, <xref:System.ServiceProcess.ServiceControllerStatus.StartPending>, 또는 <xref:System.ServiceProcess.ServiceControllerStatus.StopPending>합니다. 이러한 상태는 명령 실행 된 명령 실행 중인 서비스를 일시 중지 등 하지만 아직 수행 하지 않은 나타냅니다. 쿼리할 수 있습니다는 <xref:System.ServiceProcess.ServiceController.Status%2A> 이 다음에 서비스 상태를 확인 하거나 사용 하는 <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A> 발생할 경우 이러한 상태는 작업을 수행 하려면.  
  
 일시 중지, 중지 또는에서 서비스를 다시 시작할 수는 **서비스 제어 관리자**에서 **서버 탐색기**, 또는 코드에서 메서드를 호출 합니다. 서비스에서 관련된 프로시저를 호출할 수 이러한 각 작업 (<xref:System.ServiceProcess.ServiceBase.OnStop%2A>, <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, 또는 <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>), 서비스 상태가 변경 될 때 수행할 추가 처리를 정의할 수 있는에 있습니다.  
  
## <a name="types-of-services"></a>서비스 종류  
 두 가지 유형의 서비스를.NET Framework를 사용 하 여 Visual Studio에서 만들 수 있습니다. 서비스는 프로세스에서 하나 뿐인 서비스를 형식으로 할당 됩니다 <xref:System.ServiceProcess.ServiceType.Win32OwnProcess>합니다. 다른 서비스와 프로세스를 공유 하는 서비스 형식에 할당 됩니다 <xref:System.ServiceProcess.ServiceType.Win32ShareProcess>합니다. 쿼리하여 서비스 유형을 검색할 수는 <xref:System.ServiceProcess.ServiceController.ServiceType%2A> 속성입니다.  
  
 Visual Studio에서 생성 되지 않은 기존 서비스를 쿼리 하는 경우 다른 서비스 유형을 표시 될 수도 있습니다. 이러한 이벤트에 대해 자세한 내용은 참조는 <xref:System.ServiceProcess.ServiceType>합니다.  
  
## <a name="services-and-the-servicecontroller-component"></a>서비스 및 ServiceController 구성 요소  
 <xref:System.ServiceProcess.ServiceController> 구성 요소가 설치 된 서비스에 연결 하 고의 상태를 관리 하는 데 사용, 사용 하 여 한 <xref:System.ServiceProcess.ServiceController> 구성 요소 및 서비스 중지, 일시 중지 및 계속의 작동을 시작 서비스에 사용자 지정 명령을 보냅니다. 그러나 않아도 사용 하는 <xref:System.ServiceProcess.ServiceController> 서비스 응용 프로그램을 만들 때 구성 요소입니다. 실제로 대부분의 경우에 프로그램 <xref:System.ServiceProcess.ServiceController> 구성 요소 서비스를 정의 하는 Windows 서비스 응용 프로그램에서 별도 응용 프로그램에 있어야 합니다.  
  
 자세한 내용은 <xref:System.ServiceProcess.ServiceController>을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
-   서비스에서 만들어져야 합니다는 **Windows 서비스** 응용 프로그램 프로젝트 또는 다른.NET Framework 기반 프로젝트를 빌드할 때.exe 파일을 만들고에서 상속 하는 <xref:System.ServiceProcess.ServiceBase> 클래스입니다.  
  
-   Windows 서비스를 포함 하는 프로젝트에는 프로젝트와 해당 서비스에 대 한 설치 구성 요소가 있어야 합니다. 이 수에서 쉽게 수행할 수는 **속성** 창. 자세한 내용은 참조 [하는 방법: 서비스 응용 프로그램 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows 서비스 응용 프로그램](../../../docs/framework/windows-services/index.md)  
 [서비스 응용 프로그램 프로그래밍 아키텍처](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 [방법: Windows 서비스 만들기](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [방법: 서비스 설치 및 제거](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [방법: 서비스 시작](../../../docs/framework/windows-services/how-to-start-services.md)  
 [방법: Windows 서비스 응용 프로그램 디버깅](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [연습: 구성 요소 디자이너에서 Windows 서비스 응용 프로그램 만들기](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 [방법: 서비스 응용 프로그램에 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
