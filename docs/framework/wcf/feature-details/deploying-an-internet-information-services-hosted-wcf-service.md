---
title: 인터넷 정보 서비스에서 호스트하는 WCF 서비스 배포
ms.date: 03/30/2017
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
ms.openlocfilehash: 59f18d8487deb52f5ecb5b5c814ec9bdbc74e2cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496382"
---
# <a name="deploying-an-internet-information-services-hosted-wcf-service"></a>인터넷 정보 서비스에서 호스트하는 WCF 서비스 배포
개발 및 인터넷 정보 서비스 (IIS)에서 호스팅되는 Windows Communication Foundation (WCF) 서비스를 배포 하는 다음과 같은 작업으로 구성 됩니다.  
  
-   IIS, ASP.NET, WCF, 및 WCF 활성화 구성 요소가 올바르게 설치 되어 등록을 확인 합니다.  
  
-   새 IIS 응용 프로그램을 만들거나 기존 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램을 다시 사용합니다.  
  
-   WCF 서비스에 대 한.svc 파일을 만듭니다.  
  
-   IIS 응용 프로그램에 서비스 구현을 배포합니다.  
  
-   WCF 서비스를 구성 합니다.  
  
 IIS에서 호스팅되는 WCF 서비스를 만드는 자세한 연습은 참조 [하는 방법: IIS에서 WCF 서비스 호스팅](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)합니다.  
  
## <a name="ensure-that-iis-aspnet-and-wcf-are-correctly-installed-and-registered"></a>IIS, ASP.NET 및 WCF가 제대로 설치되고 등록되었는지 확인  
 WCF, IIS 및 ASP.NET 제대로 작동 하려면 IIS에서 호스팅되는 WCF 서비스에 대 한 설치 되어야 합니다. WCF 설치 절차 (의 일부로 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]), ASP.NET 및 IIS가 사용 되는 운영 체제 버전에 따라 달라 집니다. WCF 설치에 대 한 자세한 내용은 및 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], 참조 [MICROSOFT.NET Framework 4 웹 설치 관리자](http://go.microsoft.com/fwlink/?LinkId=201185)합니다. IIS 설치 지침은 [Installing IIS(IIS 설치)](http://go.microsoft.com/fwlink/?LinkId=201188)에서 확인할 수 있습니다.  
  
 에 대 한 설치 프로세스는 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] IIS가 이미 컴퓨터에 있는 경우 IIS와 WCF을 자동으로 등록 합니다. IIS를 나중에 설치 하는 경우는 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], IIS와 함께 WCF를 등록 하는 추가 단계가 필요 및 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]합니다. 이러한 작업을 수행하려면 운영 체제에 따라 다음과 같이 하십시오.  
  
-   [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)]Windows 7 및 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]: 사용 하 여는 [ServiceModel 등록 도구 (ServiceModelReg.exe)](../../../../docs/framework/wcf/servicemodelreg-exe.md) IIS와 함께 WCF를 등록 하는 도구:이 도구를 사용 하려면 입력 **ServiceModelReg.exe /i /x** Visual Studio에서 명령 프롬프트입니다. 시작 단추를 클릭하고 **모든 프로그램**, **Microsoft Visual Studio 2012**, **Visual Studio Tools**및 **Visual Studio 명령 프롬프트**를 선택하여 이 명령 프롬프트를 엽니다.  
  
-   [!INCLUDE[wv](../../../../includes/wv-md.md)]: [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]의 Windows Communication Foundation 활성화 구성 요소 하위 구성 요소를 설치합니다. 제어판에서이 작업을 수행 하려면 **프로그램 추가 / 제거** 차례로 **추가\/Windows 구성 요소 제거**합니다. 이렇게 하면 **Windows 구성 요소 마법사**가 활성화됩니다.  
  
-   Windows 7:  
  
 마지막으로 ASP.NET이 .NET Framework 버전 4를 사용하도록 구성되었는지 확인해야 합니다. ASPNET_Regiis 도구를 –i 옵션과 함께 실행하여 이를 확인할 수 있습니다. 자세한 내용은 참조 [ASP.NET IIS 등록 도구](http://go.microsoft.com/fwlink/?LinkId=201186)  
  
## <a name="create-a-new-iis-application-or-reuse-an-existing-aspnet-application"></a>새 IIS 응용 프로그램을 만들거나 기존 ASP.NET 응용 프로그램을 다시 사용  
 IIS에서 호스팅되는 WCF 서비스는 IIS 응용 프로그램 내부에 있어야 합니다. 단독으로 WCF 서비스를 호스팅할 새 IIS 응용 프로그램을 만들 수 있습니다. 또는 이미 호스팅하고 있는 기존 응용 프로그램에는 WCF 서비스를 배포할 수 있습니다 [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] 콘텐츠 (.aspx 페이지 및 ASP.NET 웹 서비스 [ASMX]). 이러한 옵션에 대 한 자세한 내용은 참조는 "호스팅 WCF--와 함께 ASP.NET" 및 "ASP.NET 호환 모드에서 WCF 서비스 호스팅" 섹션 [WCF 서비스 및 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)합니다.  
  
 [!INCLUDE[iis601](../../../../includes/iis601-md.md)] 이상 버전은 격리된 개체 지향 프로그래밍 응용 프로그램을 정기적으로 다시 시작합니다. 기본값은 1740분입니다. 지원되는 최대값은 71,582분입니다. 다시 시작은 사용할 수 없습니다. 이 속성에 대 한 자세한 내용은 참조는 [PeriodicRestartTime](http://go.microsoft.com/fwlink/?LinkId=109968)합니다.  
  
## <a name="create-an-svc-file-for-the-wcf-service"></a>WCF 서비스에 대한 .svc 파일 만들기  
 IIS에서 호스팅되는 WCF 서비스는 IIS 응용 프로그램 내 특수 한 콘텐츠 파일 (.svc 파일)로 표현 됩니다. 이 모델은 ASMX 페이지가 IIS 응용 프로그램 내에서 .asmx 파일로 표시되는 방식과 비슷합니다. .Svc 파일에는 WCF 관련 처리 지시문을 포함 ([@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)) WCF 인프라를 호스팅 들어오는 메시지에 응답 하는 호스팅된 서비스를 활성화할 수 있도록 합니다. .svc 파일의 가장 일반적인 구문은 다음 문에서 볼 수 있습니다.  
  
```  
<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>  
```  
  
 이 구문은 [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 지시문과 단일 특성 `Service`로 구성됩니다. `Service` 특성 값은 서비스 구현의 CLR(공용 언어 런타임) 형식 이름입니다. 이 지시문을 사용하는 것은 기본적으로 다음 코드를 사용하여 서비스 호스트를 만드는 것과 같습니다.  
  
```  
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );  
```  
  
 서비스의 기본 주소 목록을 만드는 것과 같은 추가 호스팅 구성 작업을 수행할 수도 있습니다. 사용자 지정 <xref:System.ServiceModel.Activation.ServiceHostFactory> 를 사용하여 사용자 지정 호스팅 솔루션에 사용할 지시문을 확장할 수도 있습니다. WCF 서비스를 호스팅하는 IIS 응용 프로그램 만들기 및 수명을 관리 하는 것에 대 한 책임을 지지 않습니다 <xref:System.ServiceModel.ServiceHost> 인스턴스. 관리 되는 WCF 호스팅 인프라 만드는 데 필요한 <xref:System.ServiceModel.ServiceHost> .svc 파일에 대 한 첫 번째 요청을 받으면 인스턴스를 동적으로 합니다. 이 인스턴스는 코드에서 명시적으로 닫거나 응용 프로그램이 재활용될 때까지 해제되지 않습니다.  
  
 .Svc 파일에 대 한 구문에 대 한 자세한 내용은 참조 [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)합니다.  
  
## <a name="deploy-the-service-implementation-to-the-iis-application"></a>IIS 응용 프로그램에 서비스 구현 배포  
 IIS에서 호스팅되는 WCF 서비스 사용과 동일한 동적 컴파일 모델 [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)]합니다. 과 마찬가지로 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], 다음과 같이 다양 한 위치에서 여러 가지 방법으로 IIS에서 호스팅되는 WCF 서비스에 대 한 구현 코드를 배포할 수 있습니다.  
  
-   GAC(전역 어셈블리 캐시) 또는 응용 프로그램의 \bin 디렉터리에 있는 미리 컴파일된 .dll 파일로 배포합니다. 미리 컴파일된 이진 파일은 클래스 라이브러리의 새 버전이 배포될 때까지 업데이트되지 않습니다.  
  
-   응용 프로그램의 \App_Code 디렉터리에 있는 컴파일되지 않은 소스 파일로 배포합니다. 응용 프로그램의 첫 번째 요청을 처리할 때 이 디렉터리에 있는 소스 파일이 동적으로 필요합니다. \App_Code 디렉터리의 파일을 변경하면 다음 요청을 받았을 때 전체 응용 프로그램이 재활용되고 다시 컴파일됩니다.  
  
-   .svc 파일에 직접 배치된 컴파일되지 않은 코드로 배포합니다. 구현 코드 후 서비스의.svc 파일에서 인라인으로 찾을된 수도 있습니다는 @ServiceHost 지시문입니다. 인라인 코드를 변경하면 다음 요청을 받았을 때 응용 프로그램이 재활용되고 다시 컴파일됩니다.  
  
 에 대 한 자세한 내용은 [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] 컴파일 모델 참조 [ASP.NET 컴파일 개요](http://go.microsoft.com/fwlink/?LinkId=94773)합니다.  
  
## <a name="configure-the-wcf-service"></a>WCF 서비스 구성  
 IIS에서 호스팅되는 WCF 서비스는 해당 구성을 응용 프로그램 Web.config 파일에 저장 합니다. IIS에서 호스팅되는 서비스는 IIS 외부에서 호스팅되는 WCF 서비스로 동일한 구성 요소 및 구문을 사용 합니다. 그러나 다음 제약 조건은 IIS 호스팅 환경에만 적용됩니다.  
  
-   IIS에서 호스팅되는 서비스의 기본 주소  
  
-   IIS 외부에서 호스팅 WCF 서비스의 기본 집합을 전달 하 여 호스트 하는 서비스의 기본 주소를 제어할 수는 응용 프로그램 주소 Uri에는 <xref:System.ServiceModel.ServiceHost> 생성자 또는 제공 하 여 한 [ \<호스트 >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) 요소에는 서비스의 구성입니다. IIS에서 호스팅되는 서비스에는 해당 기본 주소를 제어하는 기능이 없습니다. IIS에서 호스팅되는 서비스의 기본 주소는 해당 .svc 파일의 주소입니다.  
  
### <a name="endpoint-addresses-for-iis-hosted-services"></a>IIS에서 호스팅되는 서비스의 끝점 주소  
 IIS에서 호스팅되는 경우 끝점 주소는 서비스를 나타내는 .svc 파일의 주소에 항상 상대적인 것으로 간주됩니다. 예를 들어, WCF 서비스의 기본 주소는 http://localhost/Application1/MyService.svc 다음과 같은 끝점 구성을 사용 합니다.  
  
```xml  
<endpoint address="anotherEndpoint" .../>  
```  
  
 에 연결할 수 있는 끝점을 제공 "http://localhost/Application1/MyService.svc/anotherEndpoint"입니다.  
  
 마찬가지로, 끝점 하는 구성 요소에 도달할 수 있는 끝점을 제공 하는 상대 주소는 빈 문자열을 사용 하 여 http://localhost/Application1/MyService.svc, 하는 기본 주소입니다.  
  
```xml  
<endpoint address="" ... />  
```  
  
 IIS에서 호스팅되는 서비스 끝점에는 항상 상대 끝점 주소를 사용해야 합니다. 제공 된 정규화 된 끝점 주소 (예를 들어 http://localhost/MyService.svc) 끝점 주소가 끝점을 노출 하는 서비스를 호스팅하는 IIS 응용을 가리키지 않을 경우 서비스의 배포에서 오류가 발생할 수 있습니다. 호스팅된 서비스에 상대 끝점 주소를 사용하면 이러한 잠재적 충돌을 예방할 수 있습니다.  
  
### <a name="available-transports"></a>사용 가능한 전송  
 IIS 5.1에서 호스팅되는 WCF 서비스 및 [!INCLUDE[iis601](../../../../includes/iis601-md.md)] HTTP 기반 통신의 사용이 제한 됩니다. 이러한 IIS 플랫폼에서 HTTP가 아닌 바인딩을 사용하도록 호스팅된 서비스를 구성하면 서비스 활성화 중에 오류가 발생합니다. 기존 MSMQ 응용 프로그램과의 호환성을 위해 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]에서 지원되는 전송에는 HTTP, Net.TCP, Net.Pipe, Net.MSMQ 및 msmq.formatname이 있습니다.  
  
### <a name="http-transport-security"></a>HTTP 전송 보안  
 IIS에서 호스팅되는 WCF 서비스 http 사용 하 여 만들 수는 서비스를 포함 하는 IIS 가상 디렉터리를 지원 하는 것으로 전송 보안 (예를 들어 HTTPS 및 HTTP 인증 스키마 Basic, 다이제스트, Windows 통합 인증 등) 설정. 호스팅된 끝점의 바인딩에서 HTTP 전송 보안 설정은 끝점의 바인딩을 포함하는 IIS 가상 디렉터리의 전송 보안 설정과 일치해야 합니다.  
  
 예를 들어 HTTP 다이제스트 인증을 사용 하도록 구성 하는 WCF 끝점은 HTTP 다이제스트 인증을 허용 하도록 구성 된 IIS 가상 디렉터리에 있어야 합니다. IIS 설정과 WCF 끝점 설정 조합이 일치 하지 않으면된 서비스 활성화 중 오류가 발생 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [인터넷 정보 서비스에서 호스팅](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [인터넷 정보 서비스 호스팅을 위한 최선의 방법](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Windows Server App Fabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkId=201276)
