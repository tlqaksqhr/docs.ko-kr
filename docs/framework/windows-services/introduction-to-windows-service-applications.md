---
title: "Windows 서비스 응용 프로그램 소개 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ServiceController"
helpviewer_keywords: 
  - "프레임워크 서비스, 서비스 만들기"
  - "OnContinue 메서드"
  - "OnPause 메서드"
  - "OnStop 메서드"
  - "Service 클래스, Windows 서비스 응용 프로그램"
  - "서비스 상태"
  - "ServiceController 구성 요소, Windows 서비스 정보"
  - "서비스, 서비스 정보"
  - "서비스, 수명"
  - "서비스, 상태"
  - "WaitForStatus 메서드"
  - "Win32OwnProcess 서비스 형식"
  - "Win32ShareProcess 서비스 형식"
  - "Windows 서비스 응용 프로그램, Windows 서비스 응용 프로그램 정보"
  - "Windows 서비스 응용 프로그램, 배포"
  - "Windows 서비스 응용 프로그램, 수명"
ms.assetid: 1b1b5e67-3ff3-40c0-8154-322cfd6ef0ae
caps.latest.revision: 17
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 17
---
# Windows 서비스 응용 프로그램 소개
NT 서비스로 알려진 Microsoft Windows 서비스를 사용하면 자체의 Windows 세션에서 실행되는 장기 실행 응용 프로그램을 만들 수 있습니다.  이러한 서비스는 컴퓨터를 부팅할 때 자동으로 시작되고 일시 중지 및 다시 시작할 수 있으며 사용자 인터페이스를 표시하지 않습니다.  따라서 이러한 서비스는 서버에서 사용할 때 또는 동일한 컴퓨터에서 작업하는 다른 사용자를 방해하지 않는 장기 실행 기능이 필요할 때 유용합니다.  로그온한 사용자 계정이나 기본 컴퓨터 계정과 다른 특정 사용자 계정의 보안 컨텍스트에서 서비스를 실행할 수도 있습니다.  서비스 및 Windows 세션에 대한 자세한 내용은 MSDN Library의 Windows SDK 설명서를 참조하십시오.  
  
 서비스로 설치된 응용 프로그램을 작성하여 서비스를 쉽게 만들 수 있습니다.  예를 들어, 성능 카운터 데이터를 모니터링하여 임계값에 반응하는 서비스를 가정할 경우  성능 카운터 데이터를 수신하는 Windows 서비스 응용 프로그램을 작성한 다음 응용 프로그램을 배포하고 데이터 수집 및 분석을 시작하면 됩니다.  
  
 서비스를 Microsoft Visual Studio 프로젝트로 만들어 서비스에 전달할 수 있는 명령과 명령을 수신했을 때 수행할 동작을 제어하는 코드를 서비스에 정의합니다.  서비스에 전달할 수 있는 명령에는 서비스 시작, 일지 중지, 다시 시작 및 중지가 있습니다. 이외에도 사용자 지정 명령을 실행할 수 있습니다.  
  
 응용 프로그램을 만들고 빌드한 후 명령줄 유틸리티 InstallUtil.exe를 실행하여 서비스 실행 파일에 대한 경로를 전달하여 응용 프로그램을 설치할 수 있습니다.  그러면 **서비스 제어 관리자**를 사용하여 서비스를 시작, 중지, 일시 중지, 다시 시작 및 구성할 수 있습니다.  **서버 탐색기**에 있는 **서비스** 노드 또는 <xref:System.ServiceProcess.ServiceController> 클래스를 사용해도 이와 동일한 여러 작업을 수행할 수 있습니다.  
  
## 서비스 응용 프로그램 및 다른 Visual Studio 응용 프로그램  
 서비스 응용 프로그램은 다른 프로젝트 형식과 다음과 같이 다르게 작동합니다.  
  
-   프로젝트가 제대로 작동하려면 서비스 응용 프로그램 프로젝트에서 생성한 컴파일된 실행 파일이 서버에 설치되어 있어야 합니다.  서비스 응용 프로그램은 F5 또는 F11 키를 눌러 디버깅하거나 실행할 수 없으며 서비스를 즉시 실행하거나 서비스의 코드를 한 단계씩 실행할 수 없습니다.  대신 서비스를 설치하고 시작한 다음 서비스의 프로세스에 디버거를 연결해야 합니다.  자세한 내용은 [방법: Windows 서비스 응용 프로그램 디버깅](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)을 참조하십시오.  
  
-   일부 프로젝트 형식과 달리 서비스 응용 프로그램의 경우 설치 구성 요소를 만들어야 합니다.  설치 구성 요소는 서버에 서비스를 설치 및 등록하고 Windows **서비스 제어 관리자**를 사용하여 서비스에 대한 엔트리를 만듭니다.  자세한 내용은 [방법: 서비스 응용 프로그램에 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)을 참조하십시오.  
  
-   서비스 응용 프로그램에 대한 `Main` 메서드는 프로젝트가 포함하는 서비스에 대한 Run 명령을 발생시켜야 합니다.  `Run` 메서드는 서비스를 해당 서버의 **서비스 제어 관리자**로 로드합니다.  **Windows 서비스** 프로젝트 템플릿을 사용하면 이 메서드가 자동으로 작성됩니다.  서비스 로드와 서비스 시작은 다릅니다.  자세한 내용은 아래의 "서비스 수명"을 참조하십시오.  
  
-   Windows 서비스 응용 프로그램은 로그온한 사용자의 대화형 스테이션과는 다른 윈도우 스테이션에서 실행됩니다.  윈도우 스테이션은 클립보드, 전역 아톰 집합 및 데스크톱 개체 그룹이 포함된 안전한 개체입니다.  Windows 서비스가 실행되는 스테이션은 대화형이 아니기 때문에 Windows 서비스 응용 프로그램에서 사용되는 대화 상자는 보이지 않으며 사용자 프로그램의 응답을 중지시킬 수 있습니다.  이와 마찬가지로 오류 메시지는 사용자 인터페이스에서 발생되지 않고 Windows 이벤트 로그에 기록됩니다.  
  
     .NET Framework에서 지원하는 Windows 서비스 클래스에서는 대화형 스테이션, 즉 로그온한 사용자와의 상호 작용을 지원하지 않습니다.  또한 .NET Framework에는 스테이션 및 데스크톱을 나타내는 클래스가 포함되어 있지 않습니다.  Windows 서비스가 다른 스테이션과 상호 작용하려면 관리되지 않는 Windows API에 액세스해야 합니다.  자세한 내용은 Windows SDK 설명서를 참조하십시오.  
  
     Windows 서비스가 사용자나 다른 스테이션과 상호 작용하도록 디자인할 경우에는 로그온한 사용자가 없는 경우 또는 사용자에게 예기치 않은 데스크톱 개체 집합이 있는 경우 등의 시나리오가 포함되도록 신중하게 다루어야 합니다.  경우에 따라서는 사용자의 제어 하에 실행되는 Windows 응용 프로그램을 작성하는 것이 더 적합할 경우도 있습니다.  
  
-   Windows 서비스 응용 프로그램은 자체의 보안 컨텍스트에서 실행되고 이 응용 프로그램이 설치된 Windows 컴퓨터에 사용자가 로그인하기 전에 시작됩니다.  시스템 계정에서 실행되는 서비스는 사용자 계정보다 많은 권한을 가지므로 서비스를 실행할 사용자 계정을 구성할 때 주의해야 합니다.  
  
## 서비스 수명  
 서비스는 해당 수명 내에서 몇 가지의 내부 상태를 거칩니다.  먼저 서비스는 서비스가 실행될 시스템에 설치됩니다.  이 프로세스에서 서비스 프로젝트에 대한 설치 관리자가 실행되고 서비스가 해당 컴퓨터의 **서비스 제어 관리자**로 로드됩니다.  **서비스 제어 관리자**는 서비스 관리를 위해 Windows에서 제공하는 중앙 유틸리티입니다.  
  
 서비스는 로드된 다음 시작해야 합니다.  서비스를 시작하면 서비스가 작동을 시작합니다.  **서비스 제어 관리자** 또는 **서버 탐색기**에서 서비스를 시작하거나 <xref:System.ServiceProcess.ServiceController.Start%2A> 메서드를 호출하여 코드에서 서비스를 시작할 수 있습니다.  <xref:System.ServiceProcess.ServiceController.Start%2A> 메서드는 응용 프로그램의 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드에 처리를 전달하고 메서드에 정의된 모든 코드를 처리합니다.  
  
 실행 중인 서비스는 서비스를 중지 또는 일시 중지하거나 컴퓨터를 종료할 때까지 계속 현재 상태로 존재할 수 있습니다.  서비스는 <xref:System.ServiceProcess.ServiceControllerStatus>, <xref:System.ServiceProcess.ServiceControllerStatus> 또는 <xref:System.ServiceProcess.ServiceControllerStatus>의 세 가지 기본 상태 중 하나로 존재할 수 있습니다.  서비스는 또한 <xref:System.ServiceProcess.ServiceControllerStatus>, <xref:System.ServiceProcess.ServiceControllerStatus>, <xref:System.ServiceProcess.ServiceControllerStatus>, <xref:System.ServiceProcess.ServiceControllerStatus> 등의 보류 명령 상태를 보고할 수 있습니다.  이러한 상태는 실행 중인 서비스를 일시 중지하는 명령 등이 발생했지만 아직 수행되지 않은 상태를 나타냅니다.  <xref:System.ServiceProcess.ServiceController.Status%2A>를 쿼리하여 서비스의 상태를 확인하거나, <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>를 사용하여 이러한 상태가 발생할 경우 작업을 수행할 수 있습니다.  
  
 코드에서 메서드를 호출하거나 **서비스 제어 관리자** 또는 **서버 탐색기**를 사용하여 서비스를 일시 중지, 중지 또는 다시 시작할 수 있습니다.  이러한 각 동작은 서비스의 관련 프로시저\(<xref:System.ServiceProcess.ServiceBase.OnStop%2A>, <xref:System.ServiceProcess.ServiceBase.OnPause%2A> 또는 <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>\)를 호출할 수 있습니다. 이 프로시저에 서비스 상태가 변경될 때 수행할 추가 처리를 정의할 수 있습니다.  
  
## 서비스 형식  
 .NET Framework를 사용하여 Visual Studio에서 만들 수 있는 서비스에는 두 가지 형식이 있습니다.  프로세스에서 유일하게 존재하는 서비스는 <xref:System.ServiceProcess.ServiceType> 형식으로 할당됩니다.  다른 서비스와 프로세스를 공유하는 서비스는 <xref:System.ServiceProcess.ServiceType> 형식으로 할당됩니다.  <xref:System.ServiceProcess.ServiceController.ServiceType%2A> 속성을 쿼리하면 서비스 형식을 검색할 수 있습니다.  
  
 Visual Studio에서 작성하지 않은 기존 서비스를 쿼리하면 다른 서비스 형식이 표시될 수도 있습니다.  이러한 서비스에 대한 자세한 내용은 <xref:System.ServiceProcess.ServiceType>을 참조하십시오.  
  
## 서비스와 ServiceController 구성 요소  
 <xref:System.ServiceProcess.ServiceController> 구성 요소는 설치된 서비스에 연결하여 서비스의 상태를 관리하는 데 사용됩니다. <xref:System.ServiceProcess.ServiceController> 구성 요소를 사용하여 서비스를 시작 및 중지하고, 서비스의 작동을 일시 중지 및 계속하며, 서비스에 사용자 지정 명령을 전달할 수 있습니다.  그러나 서비스 응용 프로그램을 만들 때는 <xref:System.ServiceProcess.ServiceController> 구성 요소를 사용할 필요가 없습니다.  실제로 대부분의 경우 <xref:System.ServiceProcess.ServiceController> 구성 요소는 서비스를 정의하는 Windows 서비스 응용 프로그램과 별도의 응용 프로그램으로 존재해야 합니다.  
  
 자세한 내용은 <xref:System.ServiceProcess.ServiceController>을 참조하십시오.  
  
## 요구 사항  
  
-   서비스는 **Windows 서비스** 응용 프로그램 프로젝트에서 만들거나, 빌드하고 <xref:System.ServiceProcess.ServiceBase> 클래스에서 상속할 때 .exe 파일을 만드는 .NET Framework 사용 가능 프로젝트에서 만들어야 합니다.  
  
-   Windows 서비스를 포함하는 프로젝트에는 프로젝트와 해당 서비스에 대한 설치 구성 요소가 있어야 합니다.  이 작업은 **속성** 창에서 쉽게 수행할 수 있습니다.  자세한 내용은 [방법: 서비스 응용 프로그램에 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)을 참조하십시오.  
  
## 참고 항목  
 [Windows Service Applications](../../../docs/framework/windows-services/index.md)   
 [서비스 응용 프로그램 프로그래밍 아키텍처](../../../docs/framework/windows-services/service-application-programming-architecture.md)   
 [방법: Windows 서비스 만들기](../../../docs/framework/windows-services/how-to-create-windows-services.md)   
 [방법: 서비스 설치 및 제거](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)   
 [방법: 서비스 시작](../../../docs/framework/windows-services/how-to-start-services.md)   
 [방법: Windows 서비스 응용 프로그램 디버깅](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)   
 [연습: 구성 요소 디자이너에서 Windows 서비스 응용 프로그램 만들기](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)   
 [방법: 서비스 응용 프로그램에 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)