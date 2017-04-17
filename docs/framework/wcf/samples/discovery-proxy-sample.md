---
title: "Discovery Proxy 샘플 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1dfa02df-15b1-4e97-9c8e-f5f2772711b0
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Discovery Proxy 샘플
이 샘플에서는 검색 프록시를 구현하여 기존 서비스에 대한 정보를 저장하는 방법과 클라이언트가 해당 프록시에서 정보를 쿼리하는 방법을 보여 줍니다.이 샘플은 다음의 세 프로젝트로 구성되어 있습니다.  
  
-   **Service**: 검색 프록시에 자동으로 등록되는 간단한 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 계산기 서비스입니다.  
  
-   **Discovery Proxy**: 검색 프록시 서비스의 구현입니다.  
  
-   **Client**: 검색 프록시를 호출하여 서비스를 검색하는 WCF 클라이언트 응용 프로그램입니다.  
  
## 세부 항목  
 검색 프록시 구현  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryProxy`  
  
## DiscoveryProxy  
 Program.cs 파일의 `Main` 메서드에서 이 샘플은 <xref:System.ServiceModel.Discovery.DiscoveryProxy> 형식의 서비스가 호스팅되는 방식을 보여 줍니다.이 샘플에서는 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> 형식과 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> 형식의 두 끝점을 노출합니다.두 끝점 모두 전송에 TCP를 사용합니다.<xref:System.ServiceModel.Discovery.DiscoveryEndpoint>는 `probeEndpointAddress` 매개 변수로 지정된 URI에서 수신 대기합니다. 클라이언트는 이 URI에서 프로브 메시지를 보내 프록시에서 데이터를 쿼리할 수 있습니다.<xref:System.ServiceModel.Discovery.AnnouncementEndpoint>는 `announcementEndpointAddress` 매개 변수로 지정된 URI에서 수신 대기합니다.프록시는 이 URI에서 알림을 수신 대기합니다.온라인 알림을 받은 경우 프록시는 캐시에 서비스를 추가하고 오프라인 알림을 받은 경우에는 캐시에서 서비스를 제거합니다.  
  
 DiscoveryProxy.cs에는 <xref:System.ServiceModel.Discovery.DiscoveryProxy>의 구현이 포함되어 있습니다.프록시는 <xref:System.ServiceModel.Discovery.DiscoveryProxyBase> 클래스에서 상속해야 하며 <xref:System.Runtime.Remoting.Messaging.AsyncResult>의 구현을 필요로 합니다.인스턴스화 시 프록시는 새 <xref:Systems.Collections.Generic.Dictionary%601>를 만들어 알려진 요소를 저장하는 데 사용합니다.  
  
 파일은 프록시 캐시 메서드와 검색 프록시 구현의 두 영역으로 나뉘어 있습니다.프록시 캐시 메서드 영역에는 <xref:Systems.Collections.Generic.Dictionary%601>를 업데이트하고, <xref:Systems.Collections.Generic.Dictionary%601>에 대한 쿼리를 수행하고, 사용자에게 데이터를 출력하는 데 사용되는 메서드가 포함되어 있습니다.검색 프록시 구현 영역에는 알림 및 프로브 기능에 필요한 재정의된 메서드가 포함되어 있습니다.이러한 메서드는 온라인 알림, 오프라인 알림 또는 프로브 메시지를 받은 후 프록시에서 수행하는 작업을 정의합니다.  
  
## Service  
 Service 프로젝트의 Program.cs 파일에서는 검색 프록시와 동일한 URI가 알림 끝점에 사용됩니다.서비스에서는 알림을 보내는 데 끝점을 사용하는 반면 프록시에서는 알림을 받는 데 끝점을 사용하기 때문입니다.서비스에서는 <xref:System.ServiceModel.Discovery.DiscoveryBehavior>를 사용하고 여기에 알림 끝점을 추가합니다.  
  
## Client  
 Client 프로젝트에서는 프록시와 동일한 URI를 프로브 끝점에 사용합니다.이 시나리오의 프로브는 프록시에서 사용할 수 있는 끝점에 대한 유니캐스트가 되기도 하기 때문입니다.클라이언트는 이 잘 알려진 주소에 연결한 다음 이 주소에서 서비스를 쿼리하고,서비스를 찾은 후에는 해당 서비스에 연결합니다.  
  
#### 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에 프로젝트 솔루션을 로드하고 프로젝트를 빌드합니다.  
  
2.  먼저 \[solution base directory\]\\DiscoveryProxy\\bin\\debug에 생성된 Discovery Proxy 응용 프로그램을 실행합니다.서비스에서 알림을 보내기 위해서는 TCP 알림 끝점이 작동 상태여야 하므로 Discovery Proxy를 먼저 실행해야 합니다.  
  
3.  그 다음 \[solution base directory\]\\Service\\bin\\debug에 생성된 서비스 응용 프로그램을 실행합니다.시작 시 이 서비스는 검색 프록시의 알림 끝점에 알림을 보내며 프록시의 캐시에 등록됩니다.  
  
4.  그 다음 \[solution base directory\]\\Client\\bin\\debug에 생성된 클라이언트 응용 프로그램을 실행합니다.클라이언트는 프록시를 쿼리하고 서비스 주소를 가져온 다음 서비스에 연결합니다.  
  
5.  마지막으로, 클라이언트, 서비스 및 프록시를 차례로 종료합니다.프록시에서 서비스의 오프라인 알림을 받으려면 프록시가 실행되고 있어야 합니다.  
  
## 참고 항목