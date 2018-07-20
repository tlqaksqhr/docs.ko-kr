---
title: 인터넷 정보 서비스 호스팅을 위한 최선의 방법
ms.date: 03/30/2017
ms.assetid: 0834768e-9665-46bf-86eb-d4b09ab91af5
ms.openlocfilehash: 119f14df9d46883a33272903558d83128501b293
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495764"
---
# <a name="internet-information-services-hosting-best-practices"></a>인터넷 정보 서비스 호스팅을 위한 최선의 방법
이 항목에서는 Windows Communication Foundation (WCF) 서비스를 호스팅하기 위한 몇 가지 모범 사례에 설명 합니다.  
  
## <a name="implementing-wcf-services-as-dlls"></a>WCF 서비스를 DLL로 구현  
 구현 하는 WCF 서비스 웹 응용 프로그램의 \bin 디렉터리에 배포 되는 DLL로를 사용 하면 인터넷 정보 서비스 (IIS)가 배포에 없을 수도 있는 테스트 환경에서 예를 들어 웹 응용 프로그램 모델 외부에서 서비스를 재사용 합니다.  
  
## <a name="service-hosts-in-iis-hosted-applications"></a>IIS에서 호스팅되는 응용 프로그램의 서비스 호스트  
 TCP 통신이 기본적으로 [!INCLUDE[iis601](../../../../includes/iis601-md.md)]에서 지원되지 않기 때문에 TCP 서비스를 호스팅하는 [!INCLUDE[iis601](../../../../includes/iis601-md.md)]처럼, IIS 호스팅 환경에서 기본적으로 지원하지 않는 네트워크 전송에서 수신 대기하는 새 서비스 호스트를 만들 때 명령적 자체 호스팅 API를 사용하지 마십시오. 이는 권장되는 방법이 아닙니다. 명령적으로 만들어진 서비스 호스트는 IIS 호스팅 환경 내에서 알 수 없습니다. 중요한 점은 호스팅 응용 프로그램 풀이 유휴 상태인지 여부를 결정할 때 명령적으로 만든 서비스에서 수행된 처리가 IIS에 의해 정의되지 않는다는 것입니다. 결과적으로 명령적으로 그러한 서비스 호스트를 만든 응용 프로그램에 적극적으로 IIS 호스트 프로세스를 삭제하는 IIS 호스팅 환경이 포함됩니다.  
  
## <a name="uris-and-iis-hosted-endpoints"></a>URI 및 IIS에서 호스팅되는 끝점  
 IIS에서 호스팅되는 서비스의 끝점은 절대 주소가 아닌 상대 URI(Uniform Resource Identifier)를 사용하여 구성되어야 합니다. 이렇게 하면 끝점 주소가 호스팅 응용 프로그램에 속하는 URI 주소 집합 내에 있게 되고 예상한 대로 메시지 기반 활성화가 수행됩니다.  
  
## <a name="state-management-and-process-recycling"></a>상태 관리 및 프로세스 재활용  
 IIS 호스팅 환경은 메모리에 로컬 상태를 유지 관리하지 않는 서비스에 맞게 최적화됩니다. IIS는 여러 외부 및 내부 이벤트에 대한 응답으로 호스트 프로세스를 재활용하여 메모리에만 저장된 일시적 상태가 손실됩니다. IIS에서 호스팅된 서비스는 해당 상태를 프로세스 외부(예: 데이터베이스)에 저장하거나 응용 프로그램 재활용 이벤트가 발생하는 경우 쉽게 다시 만들 수 있는 메모리 내 캐시에 저장해야 합니다.  
  
> [!NOTE]
>  WCF 메시지 계층 안정성 및 보안을 사용 하는 프로토콜 휘발성 메모리 내 상태를 활용 합니다. WCF 신뢰할 수 있는 세션 및 보안 세션 응용 프로그램 재활용으로 인해 갑자기 종료 될 수 있습니다. 응용 프로그램 계층 상태 (예를 들어 응용 프로그램 계층 생성 또는 사용자 지정 상관 관계 헤더) 또는 사용 안 함을 연결 하기 위한 WCF에서 제공한 세션 키 이외의 것에 의존 해야 하거나 두 프로토콜 하는 IIS에서 호스트 응용 프로그램 사용 호스팅된 응용 프로그램에 대 한 재생 하는 IIS 프로세스입니다.  
  
## <a name="optimizing-performance-in-middle-tier-scenarios"></a>중간 계층 시나리오에서 성능 최적화  
 최적의 성능을 위해는 *중간 계층 시나리오*-들어오는 메시지에 대 한 응답으로 다른 서비스 호출 하는 서비스-원격 서비스에 WCF 서비스 클라이언트를 한 번 인스턴스화하고 여러 수신에 대해 다시 사용 요청 수입니다. 작업은 WCF 서비스 클라이언트 인스턴스화는 기존 클라이언트 인스턴스에 대 한 서비스 호출을 만드는 기준으로 비용이 많이 드는 작업 및 중간 계층 시나리오는 요청을 통해 원격 클라이언트를 캐시 하 여 고유한 성능 향상을 생성 합니다. WCF 서비스 클라이언트는 스레드-안전 하므로 여러 스레드에 대해 클라이언트에 대 한 액세스를 동기화 할 필요가 없습니다.  
  
 중간 계층 시나리오는 또한 `svcutil /a` 옵션에서 생성된 비동기 API를 사용하여 성능을 향상시킵니다. `/a` 옵션을 사용 하면은 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 생성할 `BeginXXX/EndXXX` 에서 원격 서비스에 대 한 실행 시간이 긴 호출 수 있는 각 서비스 작업에 대 한 메서드 백그라운드 스레드입니다.  
  
## <a name="wcf-in-multi-homed-or-multi-named-scenarios"></a>멀티홈 또는 여러 개의 이름이 지정된 시나리오의 WCF  
 컴퓨터 집합이 공용 외부 이름을 공유 하는 IIS 웹 팜 내에서 WCF 서비스를 배포할 수 있습니다 (같은 http://www.contoso.com) 다른 호스트 이름으로 개별적으로 해결 되지만 (예를 들어 http://www.contoso.com 서로 다른 컴퓨터에 트래픽을 명명 된 http://machine1.internal.contoso.com 및 http://machine2.internal.contoso.com) 합니다. 이 배포 시나리오는 WCF에서 완벽 하 게 지원 하지만 서비스의 메타 데이터 (웹 서비스 기술 언어)에 올바른 (외부) 호스트 이름을 표시 하려면 WCF 서비스를 호스팅하는 IIS 웹 사이트의 특수 한 구성이 있어야 합니다.  
  
 올바른 호스트 이름을 생성 하는 WCF 서비스 메타 데이터에 표시 하려면 명시적 호스트 이름을 사용 하도록 WCF 서비스를 호스팅하는 IIS 웹 사이트에 대 한 기본 id를 구성 합니다. 예를 들어 www.contoso.com 팜 내 상주 하는 컴퓨터의 IIS 사이트 바인딩을 사용할지 * HTTP에 대 한 경우 및 \*: 443:www.contoso.com HTTPS에 대 한 합니다.  
  
 IIS MMC(Microsoft Management Console) 스냅인을 사용하여 IIS 웹 사이트 바인딩을 구성할 수 있습니다.  
  
## <a name="application-pools-running-in-different-user-contexts-overwrite-assemblies-from-other-accounts-in-the-temporary-folder"></a>다른 사용자 컨텍스트에서 실행되는 응용 프로그램 풀이 임시 폴더에 있는 다른 계정의 어셈블리를 덮어씀  
 다른 사용자 컨텍스트에서 실행되는 응용 프로그램 풀이 임시 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 파일 폴더에 있는 다른 계정의 어셈블리를 덮어쓸 수 없는지 확인하려면 응용 프로그램마다 다른 ID와 임시 폴더를 사용합니다. 예를 들어 두 개의 가상 응용 프로그램/Application1 및 / Application2가 있을 경우 ID가 다른 두 개의 응용 프로그램 풀 A와 B를 만들 수 있습니다. 응용 프로그램 풀 A는 사용자 ID(user1)에서 실행되는 동시에 응용 프로그램 풀 B는 다른 사용자 ID(user2)에서 실행되며 A를 사용하도록 /Application1을 구성하고 B를 사용하도록 /Application2를 구성할 수 있습니다.  
  
 Web.config에서 구성할 수 있습니다를 사용 하 여 임시 폴더 \< system.web/compilation/@tempFolder> 합니다. /Application1에 대 한 "c:\tempForUser1" 수 및 응용 프로그램 2에 대 한 "c:\tempForUser2" 수 있습니다. 이러한 폴더에 대해 해당하는 쓰기 권한을 두 ID에 부여합니다.  
  
 그러면 user2는 c:\tempForUser1에 있는 /application2에 대한 코드 생성 폴더를 변경할 수 없습니다.  
  
## <a name="enabling-asynchronous-processing"></a>비동기 처리 사용  
 기본적으로 IIS 6.0 및 이전 호스팅된 WCF 서비스에 전송 된 메시지를 동기 방식으로 처리 됩니다. ASP.NET (ASP.NET 작업자 스레드) 자체 스레드에서 WCF에 호출 하 고 WCF 다른 스레드를 사용 하 여 요청을 처리할 키를 누릅니다. WCF는 처리를 완료할 때까지 ASP.NET 작업자 스레드를 보관합니다. 따라서 요청이 동기 방식으로 처리됩니다. 요청을 비동기적으로 처리-WCF 유지 하지 않으면 ASP.NET 스레드를 처리 하는 동안 요청을 처리 하는 데 필요한 스레드 수가 줄어들기 때문에 확장성을 뛰어난 수 있습니다. 비동기 동작을 사용 하도록 서버를 열고 들어오는 요청을 제한할 수 없기 때문에 IIS 6.0을 실행 하는 컴퓨터에 대 한 권장 되지 않습니다 *서비스 거부* (DOS) 공격입니다. IIS 7.0부터는 동시 요청 스로틀(`[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0]"MaxConcurrentRequestsPerCpu`)이 도입되었습니다. 이 새 스로틀을 사용하면 비동기 처리를 사용해도 안전합니다.  IIS 7.0에서는 기본적으로 비동기 처리기 및 모듈이 등록되어 있습니다. 이러한 비동기 처리기 및 모듈이 해제되어 있는 경우 응용 프로그램의 Web.config 파일에서 비동기 처리 요청을 사용하도록 수동으로 설정할 수 있습니다. 사용하는 설정은 `aspNetCompatibilityEnabled` 설정에 따라 달라집니다. `aspNetCompatibilityEnabled`를 `false`로 설정한 경우에는 다음 구성 코드 조각에 나와 있는 것처럼 `System.ServiceModel.Activation.ServiceHttpModule`을 구성하십시오.  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="false" />      
  </system.serviceModel>  
  <system.webServer>  
    <modules>  
      <remove name="ServiceModel"/>  
      <add name="ServiceModel"   
           preCondition="integratedMode,runtimeVersionv2.0"   
           type="System.ServiceModel.Activation.ServiceHttpModule, System.ServiceModel,Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
    </modules>  
    </system.webServer>  
```  
  
 `aspNetCompatibilityEnabled`를 `true`로 설정한 경우에는 다음 구성 코드 조각에 나와 있는 것처럼 `System.ServiceModel.Activation.ServiceHttpHandlerFactory`를 구성하십시오.  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />      
  </system.serviceModel>  
  <system.webServer>  
    <handlers>  
          <clear/>  
          <add name="TestAsyncHttpHandler"   
               path="*.svc"   
               verb="*"   
               type="System.ServiceModel.Activation.ServiceHttpHandlerFactory, System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"           
               />  
    </handlers>      
  </system.webServer>  
```  
  
## <a name="see-also"></a>참고 항목  
 [서비스 호스팅 샘플](http://msdn.microsoft.com/library/f703a3f6-0fba-418a-a92f-7ce75ccfa47e)  
 [Windows Server App Fabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkId=201276)
