---
title: "Net.TCP 포트 공유"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- port activation [WCF]
- port sharing [WCF]
ms.assetid: f13692ee-a179-4439-ae72-50db9534eded
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c54ce56cccffa350479d0dd4dcec130ddd004764
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="nettcp-port-sharing"></a>Net.TCP 포트 공유
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서는 고성능 통신을 위한 새로운 TCP 기반 네트워크 프로토콜(net.tcp://)을 제공합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 여러 사용자 프로세스 간에 net.tcp 포트를 공유할 수 있는 새 시스템 구성 요소인 Net.TCP Port Sharing Service도 제공합니다.  
  
## <a name="background-and-motivation"></a>배경 및 동기  
 TCP/IP 프로토콜이 처음에 도입되었을 때는 소수의 응용 프로그램 프로토콜에만 사용되었습니다. TCP/IP 사용 포트 번호는 고유 16비트 포트 번호를 각 응용 프로그램 프로토콜에 할당하므로 응용 프로그램에 따라 달라집니다. 예를 들어 HTTP 트래픽은 TCP 포트 80을, SMTP는 TCP 포트 25를, FTP는 TCP 포트 20 및 21을 사용하도록 표준화되어 있습니다. TCP를 전송 프로토콜로 사용하는 다른 응용 프로그램은 규칙에 따라 또는 공식 표준화를 통해 사용 가능한 다른 포트 번호를 선택할 수 있습니다.  
  
 응용 프로그램을 서로 구분하기 위해 포트 번호를 사용하면 보안 문제가 발생합니다. 일반적으로 방화벽은 몇 개의 잘 알려진 진입점을 제외하고 모든 포트의 TCP 트래픽을 차단하도록 구성되므로 비표준 포트를 사용하는 응용 프로그램을 배포하는 것은 기업 및 개인 방화벽으로 인해 복잡하거나 불가능할 수도 있습니다. 이미 허용된 잘 알려진 표준 포트를 통해 통신할 수 있는 응용 프로그램의 경우 공격을 받을 수 있는 부분이 줄어듭니다. 대부분의 방화벽은 TCP 포트 80에서 트래픽을 허용하도록 기본적으로 구성되기 때문에 여러 네트워크 응용 프로그램에서 HTTP 프로토콜을 사용합니다.  
  
 여러 HTTP 응용 프로그램의 트래픽이 단일 TCP 포트에 멀티플렉싱되는 HTTP.SYS 모델이 Windows 플랫폼의 표준이 되었습니다. 따라서 응용 프로그램 개발자가 네트워크를 사용할 수 있는 새 응용 프로그램을 빌드하는 데 필요한 배포 비용을 최소화할 수 있도록 하는 동시에 방화벽 관리자를 위한 공통 제어 지점을 제공합니다.  
  
 여러 HTTP 응용 프로그램 간의 포트를 공유할 수 있는 기능은 IIS(인터넷 정보 서비스)의 오래된 기능 중 하나입니다. 그러나 이 인프라가 완전히 일반화된 것은 [!INCLUDE[iis601](../../../../includes/iis601-md.md)]과 함께 HTTP.SYS(커널 모드 HTTP 프로토콜 수신기)가 도입된 이후부터입니다. 실제로 HTTP.SYS를 사용하면 임의의 사용자 프로세스에서 HTTP 트래픽 전용 TCP 포트를 공유할 수 있습니다. 이 기능을 사용하면 동일한 실제 컴퓨터에서 여러 HTTP 응용 프로그램을 별도의 격리 프로세스로 함께 사용할 수 있고, TCP 포트 80을 통해 트래픽을 보내고 받는 데 필요한 네트워크 인프라를 공유할 수 있습니다. Net.TCP Port Sharing Service를 통해 net.tcp 응용 프로그램에서 동일한 형식의 포트를 공유할 수 있습니다.  
  
## <a name="port-sharing-architecture"></a>포트 공유 아키텍처  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 포트 공유 아키텍처에는 다음과 같은 세 가지 주요 구성 요소가 있습니다.  
  
-   작업자 프로세스: 공유 포트를 사용하여 net.tcp://를 통해 통신하는 모든 프로세스를 의미합니다.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] TCP 전송: net.tcp:// 프로토콜을 구현합니다.  
  
-   Net.TCP Port Sharing Service: 여러 작업자 프로세스에서 동일한 TCP 포트를 공유할 수 있도록 합니다.  
  
 Net.TCP Port Sharing Service는 이 서비스를 통해 연결되는 사용자 프로세스 대신 net.tcp:// 연결을 수락하는 사용자 모드 Windows 서비스입니다. 소켓 연결이 도착하면 포트 공유 서비스는 대상 주소를 가져오기 위해 들어오는 메시지 스트림을 검사합니다. 포트 공유 서비스는 이 주소에 따라 데이터 스트림을 최종적으로 처리하는 응용 프로그램으로 라우팅할 수 있습니다.  
  
 net.tcp:// 포트 공유를 사용하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 열릴 때 응용 프로그램 프로세스에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] TCP 전송 인프라는 TCP 소켓을 직접 열지 않습니다. 대신 전송 인프라는 서비스의 기본 주소 URI(Uniform Resource Identifier)를 Net.TCP Port Sharing Service를 사용하여 등록하고 포트 공유 서비스가 대신 메시지를 수신 대기하도록 기다립니다.  포트 공유 서비스는 메시지가 도착하면 응용 프로그램 서비스에 주소가 지정된 메시지를 디스패치합니다.  
  
## <a name="installing-port-sharing"></a>포트 공유 설치  
 Net.TCP Port Sharing Service는 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]을 지원하는 모든 운영 체제에서 사용할 수 있지만 기본적으로 서비스가 활성화되어 있지는 않습니다. 보안 예방 조치로 관리자는 Net.TCP Port Sharing Service를 처음 사용하기 전에 수동으로 활성화해야 합니다. Net.TCP Port Sharing Service는 포트 공유 서비스에서 소유한 네트워크 소켓의 여러 특징을 조작할 수 있는 구성 옵션을 노출합니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][하는 방법: Net.TCP Port Sharing Service를 사용 하도록 설정](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md)합니다.  
  
## <a name="using-nettcp-port-sharing-in-an-application"></a>응용 프로그램에서 Net.tcp 포트 공유 사용  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램에서 net.tcp:// 포트 공유를 사용하는 가장 쉬운 방법은 <xref:System.ServiceModel.NetTcpBinding>을 사용하여 서비스를 노출한 다음 <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> 속성을 사용하여 Net.TCP Port Sharing Service를 활성화하는 것입니다.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]이 작업을 수행 하 [하는 방법: WCF 서비스를 사용 하 여 포트 공유 구성](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md)합니다.  
  
## <a name="security-implications-of-port-sharing"></a>포트 공유 시 보안 관련 문제  
 Net.TCP Port Sharing Service에서는 응용 프로그램과 네트워크 간의 처리 계층을 제공하지만 포트 공유를 사용하는 응용 프로그램의 경우 네트워크에서 직접 수신 대기하고 있는 것처럼 보안이 설정되어 있어야 합니다. 특히 포트 공유를 사용하는 응용 프로그램은 응용 프로그램이 실행되는 프로세스 권한을 평가해야 합니다. 네트워크 통신에 필요한 프로세스 권한의 최소 집합으로 실행되는 기본 제공 Network Service 계정을 사용하여 응용 프로그램을 실행해 보세요.  
  
## <a name="see-also"></a>참고 항목  
 [Net.TCP Port Sharing Service를 구성 합니다.](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)  
 [호스팅](../../../../docs/framework/wcf/feature-details/hosting.md)  
 [방법: 포트 공유 사용 하도록 WCF 서비스 구성](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md)  
 [방법: Net.TCP Port Sharing Service를 사용 하도록 설정](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md)
