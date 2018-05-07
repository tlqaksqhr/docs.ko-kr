---
title: Windows 서비스 응용 프로그램에서의 호스팅
ms.date: 03/30/2017
ms.assetid: f4199998-27f3-4dd9-aee4-0a4addfa9f24
ms.openlocfilehash: e440961055ccd40bf56b4b88ea73d167f1903245
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="hosting-in-a-windows-service-application"></a>Windows 서비스 응용 프로그램에서의 호스팅
Windows 서비스(이전의 Windows NT 서비스)에서는 장기 실행되는 실행 파일에 있어야 하는 응용 프로그램에 특히 적합한 프로세스 모델을 제공하지만 사용자 인터페이스 폼을 표시하지 않습니다. Windows 서비스 응용 프로그램의 프로세스 수명은 Windows 서비스 응용 프로그램을 시작, 중지 및 일지 중지할 수 있도록 해 주는 SCM(서비스 제어 관리자)이 관리합니다. Windows 서비스 프로세스가 "항상" 응용 프로그램에 적합 한 호스팅 환경을 만들 컴퓨터를 시작할 때 자동으로 시작 되도록 구성할 수 있습니다. Windows 서비스 응용 프로그램에 대 한 자세한 내용은 참조 [Windows 서비스 응용 프로그램](http://go.microsoft.com/fwlink/?LinkId=89450)합니다.  
  
 Windows 서비스와 함께 여러 특징을 공유 하는 오래 실행 되는 Windows Communication Foundation (WCF) 서비스를 호스트 하는 응용 프로그램입니다. 특히 WCF 서비스는 장기 실행 서버 실행 파일 직접 사용자 상호 작용 하지 않는 및 따라서 모든 형태의 사용자 인터페이스를 구현 하지 않습니다. 따라서 Windows 서비스 응용 프로그램 대신 WCF 서비스 호스팅은 강력한 장기 실행 WCF 응용 프로그램을 구축 하기 위한 한 가지 옵션입니다.  
  
 종종 WCF 개발자가 WCF 응용 프로그램 Windows 서비스 내에서 또는 인터넷 정보 서비스 (IIS) 또는 Windows Process Activation Service (가) 호스팅 환경 내에서 호스트할 지 결정 해야 합니다. 다음과 같은 경우에는 Windows 서비스 응용 프로그램을 사용하는 것을 고려해야 합니다.  
  
-   응용 프로그램에서 명시적 활성화가 필요한 경우. 예를 들어, 서버가 들어오는 첫 번째 메시지에 대한 응답으로 동적으로 시작되는 대신 시작될 때 응용 프로그램이 자동으로 시작되어야 하는 경우 Windows 서비스를 사용해야 합니다.  
  
-   응용 프로그램을 호스트하는 프로세스가 일단 시작되면 계속 실행되어야 하는 경우. Windows 서비스 프로세스는 일단 시작되면 서버 관리자가 서비스 제어 관리자를 사용하여 명시적으로 종료하지 않는 한 계속 실행됩니다. IIS 또는 WAS에서 호스트되는 응용 프로그램은 시스템 리소스의 사용을 최적화하기 위해 동적으로 시작되거나 중지될 수 있습니다. 호스팅 프로세스의 수명을 명시적으로 제어할 필요가 있는 응용 프로그램은 IIS 또는 WAS 대신 Windows 서비스를 사용해야 합니다.  
  
-   WCF 서비스가 Windows Server 2003에서 실행 되어야 하며 HTTP 이외의 전송을 사용 합니다. Windows Server 2003에서 [!INCLUDE[iis601](../../../../includes/iis601-md.md)] 호스팅 환경은 HTTP 통신으로만 제한됩니다. Windows 서비스 응용 프로그램이이 제한이 적용 않으며 net.tcp, net.pipe 및 net.msmq를 포함 하 여 모든 전송 WCF에서는 사용할 수 있습니다.  
  
### <a name="to-host-wcf-inside-of-a-windows-service-application"></a>Windows 서비스 응용 프로그램 대신 WCF를 호스트하려면  
  
1.  Windows 서비스 응용 프로그램을 만듭니다. <xref:System.ServiceProcess> 네임스페이스에 있는 클래스를 사용하여 관리 코드에서 Windows 서비스 응용 프로그램을 작성할 수 있습니다. 이 응용 프로그램에는 <xref:System.ServiceProcess.ServiceBase>에서 상속된 하나의 클래스가 있어야 합니다.  
  
2.  Windows 서비스 응용 프로그램의 수명에 WCF 서비스의 수명에 연결 합니다. 일반적으로 WCF 서비스 호스팅 서비스가 시작 될 때는 활성화, 호스팅 서비스를 중지 하 고 WCF 서비스에서 오류가 발생 하는 경우 호스팅 프로세스를 종료 되 면 메시지에 대 한 수신 대기를 중지 하는 Windows 서비스 응용 프로그램에서 호스트 합니다. 이렇게 하려면 다음을 수행합니다.  
  
    -   <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>를 재정의하여 <xref:System.ServiceModel.ServiceHost>의 인스턴스를 하나 이상 엽니다. 하나의 Windows 서비스 응용 프로그램이 시작 하 고 하나의 그룹으로 중지 하는 여러 개의 WCF 서비스를 호스팅할 수 있습니다.  
  
    -   재정의 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 호출할 <xref:System.ServiceModel.Channels.CommunicationObject.Closed> 에 <xref:System.ServiceModel.ServiceHost> 하는 동안 시작 된 모든 실행 중인 WCF 서비스 <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>합니다.  
  
    -   <xref:System.ServiceModel.Channels.CommunicationObject.Faulted>의 <xref:System.ServiceModel.ServiceHost> 이벤트를 구독하고 <xref:System.ServiceProcess.ServiceController> 클래스를 사용하여 오류가 발생한 경우 Windows 서비스 응용 프로그램을 종료합니다.  
  
     WCF 서비스를 호스트 하는 Windows 서비스 응용 프로그램 배포 되 고 동일한 방식으로 사용으로 관리 하지 않는 Windows 서비스 응용 프로그램의 WCF 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceProcess>  
 [연습: 구성 요소 디자이너에서 Windows 서비스 응용 프로그램 만들기](http://go.microsoft.com/fwlink/?LinkId=94875)  
 [방법: 관리되는 Windows 서비스에서 WCF 서비스 호스팅](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)  
 [Windows Service 호스트](../../../../docs/framework/wcf/samples/windows-service-host.md)  
 [서비스 응용 프로그램 프로그래밍 아키텍처](http://go.microsoft.com/fwlink/?LinkId=94876)  
 [Windows Server App Fabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkId=201276)
