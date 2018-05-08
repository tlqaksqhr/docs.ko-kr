---
title: '방법: 서비스 시작'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, starting
- services, starting
ms.assetid: 9ea77955-2d96-4c3d-913c-14db7604cdad
author: ghogen
manager: douge
ms.openlocfilehash: 3c8382d2e425d11dc8aa8b22e361b3cc5637744f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-start-services"></a>방법: 서비스 시작
서비스를 설치한 후에 시작 되어야 합니다. 호출을 시작는 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 서비스 클래스에 메서드. 일반적으로 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 메서드는 서비스에서 수행할 유용한 작업을 정의 합니다. 서비스 시작 후 수동으로 일시 중지 또는 중지 될 때까지 활성 남아 있습니다.  
  
 자동 또는 수동으로 시작 하려면 서비스를 설정할 수 있습니다. 자동으로 시작 하는 서비스는 설치 된 컴퓨터를 다시 부팅 하거나 처음 켤 때 시작 됩니다. 사용자는 수동으로 시작 하는 서비스를 시작 해야 합니다.  
  
> [!NOTE]
>  기본적으로 Visual Studio를 사용 하 여 만든 서비스를 수동으로 시작 하도록 설정 됩니다.  
  
 여러 가지 방법으로 서비스를 수동으로 시작할 수 있습니다-에서 **서버 탐색기**에서 **서비스 제어 관리자**, 라는 구성 요소를 사용 하 여 코드에서 또는 <xref:System.ServiceProcess.ServiceController>합니다.  
  
 설정한는 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성에는 <xref:System.ServiceProcess.ServiceInstaller> 수동 또는 자동으로 서비스가 다시 시작 해야 하는지 여부를 결정 하는 클래스입니다.  
  
### <a name="to-specify-how-a-service-should-start"></a>서비스 시작 방법을 지정 하려면  
  
1.  서비스를 만든 후에 필요한 설치 관리자를 추가 합니다. 자세한 내용은 참조 [하는 방법: 서비스 응용 프로그램 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)합니다.  
  
2.  디자이너를 사용 하는 서비스에 대 한 서비스 설치 관리자를 클릭 합니다.  
  
3.  에 **속성** 창에서 설정 된 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성을 다음 중 하나:  
  
    |서비스를 설치 하도록 하는|이 값을 설정 합니다.|  
    |----------------------------------|--------------------|  
    |컴퓨터 다시 시작 되 면|**자동**|  
    |명시적 사용자 동작에서 서비스를 시작 하는 경우|**수동**|  
  
    > [!TIP]
    >  서비스에서 시작 되는 것을 방지 하려면 설정할 수 있습니다는 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 속성을 **비활성화**합니다. 서버를 여러 번 다시 부팅을 시작 정상적으로 시작 하는 서비스를 방지 하 여 시간 절약을 위해 하려는 경우 이렇게 할 수도 있습니다.  
  
    > [!NOTE]
    >  서비스를 설치한 후 이러한 오류 코드 및 기타 속성을 변경할 수 있습니다.  
  
     여러 가지 방법으로 서비스를 시작할 수는 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 프로세스로 설정 **수동** -에서 **서버 탐색기**에서 **Windows 서비스 제어 관리자**, 또는 코드입니다. 이러한 메서드의 일부 실제로 시작 서비스의 컨텍스트에서 해야는 **서비스 제어 관리자**; **서버 탐색기** 및 서비스를 시작 하는 프로그래밍 방법도 실제로 컨트롤러를 조작 합니다.  
  
### <a name="to-manually-start-a-service-from-server-explorer"></a>서버 탐색기에서 서비스를 수동으로 시작 하려면  
  
1.  **서버 탐색기**, 표시 되어 있지 않으면 하는 경우 서버를 추가 합니다. 자세한 내용은 참조 하는 방법: 액세스 및 서버 탐색기 데이터베이스 탐색기를 초기화 합니다.  
  
2.  확장 된 **서비스** 노드를 한 다음 시작 하려면 서비스를 찾습니다.  
  
3.  서비스의 이름을 마우스 오른쪽 단추로 클릭 하 고 클릭 **시작**합니다.  
  
### <a name="to-manually-start-a-service-from-services-control-manager"></a>서비스 제어 관리자에서 서비스를 수동으로 시작 하려면  
  
1.  열기는 **서비스 제어 관리자** 다음 중 하나를 수행 하 여:  
  
    -   Windows XP 및 2000 Professional에서 마우스 오른쪽 단추로 클릭 **내 컴퓨터** 바탕 화면, 클릭 한 다음에 **관리**합니다. 표시 되는 대화 상자에서 확장 된 **서비스 및 응용 프로그램** 노드.  
  
         \- 또는 -  
  
    -   Windows Server 2003 및 Windows 2000 Server에서 클릭 **시작**, 가리킨 **프로그램**, 클릭 **관리 도구**, 클릭 하 고 **서비스**.  
  
        > [!NOTE]
        >  Windows nt 버전 4.0에서이 대화 상자를 열 수 있습니다 **제어판**합니다.  
  
     에 서비스 목록이 표시 됩니다는 **서비스** 창의 섹션입니다.  
  
2.  목록에서 서비스를 선택 하 고 마우스 오른쪽 단추로 클릭 한 다음 **시작**합니다.  
  
### <a name="to-manually-start-a-service-from-code"></a>코드에서 서비스를 수동으로 시작 하려면  
  
1.  인스턴스를 만들고는 <xref:System.ServiceProcess.ServiceController> 클래스를 관리 하려면 서비스와 상호 작용 하도록 구성 합니다.  
  
2.  <xref:System.ServiceProcess.ServiceController.Start%2A> 메서드를 호출하여 서비스를 시작합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows 서비스 응용 프로그램 소개](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [방법: Windows 서비스 만들기](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [방법: 서비스 응용 프로그램에 설치 관리자 추가](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)
