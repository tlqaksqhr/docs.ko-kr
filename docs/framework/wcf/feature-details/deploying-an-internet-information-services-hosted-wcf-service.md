---
title: "인터넷 정보 서비스에서 호스트하는 WCF 서비스 배포 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 04ebd329-3fbd-44c3-b3ab-1de3517e27d7
caps.latest.revision: 30
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 30
---
# 인터넷 정보 서비스에서 호스트하는 WCF 서비스 배포
IIS\(인터넷 정보 서비스\)에서 호스팅되는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스의 개발 및 배포는 다음과 같은 작업으로 구성됩니다.  
  
-   IIS, ASP.NET, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 활성화 구성 요소가 제대로 설치되고 등록되었는지 확인합니다.  
  
-   새 IIS 응용 프로그램을 만들거나 기존 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램을 다시 사용합니다.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에 대한 .svc 파일을 만듭니다.  
  
-   IIS 응용 프로그램에 서비스 구현을 배포합니다.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 구성합니다.  
  
 IIS에서 호스팅되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 만드는 자세한 연습은 [방법: IIS에서의 WCF 서비스 호스팅](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)을 참조하십시오.  
  
## IIS, ASP.NET 및 WCF가 제대로 설치되고 등록되었는지 확인  
 IIS에서 호스팅되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 제대로 작동하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], IIS 및 ASP.NET이 설치되어 있어야 합니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 설치 절차\([!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]의 일부\), ASP.NET 및 IIS는 사용하고 있는 운영 체제에 따라 달라집니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 설치[!INCLUDE[crabout](../../../../includes/crabout-md.md)][Microsoft .NET Framework 4 웹 설치 관리자](http://go.microsoft.com/fwlink/?LinkId=201185)를 참조하세요. IIS 설치 지침은 [Installing IIS\(IIS 설치\)](http://go.microsoft.com/fwlink/?LinkId=201188)에서 확인할 수 있습니다.  
  
 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]를 설치할 때 IIS가 이미 설치되어 있으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 IIS에 자동으로 등록됩니다. IIS가 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 다음에 설치되는 경우에는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 IIS 및 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]에 등록하는 추가 단계가 필요합니다. 이러한 작업을 수행하려면 운영 체제에 따라 다음과 같이 하십시오.  
  
-   [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)], Windows 7 및 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]: [ServiceModel 등록 도구\(ServiceModelReg.exe\)](../../../../docs/framework/wcf/servicemodelreg-exe.md) 도구를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 IIS에 등록: 이 도구를 사용하려면 Visual Studio 명령 프롬프트에 **ServiceModelReg.exe \/i \/x**를 입력합니다. 시작 단추를 클릭하고 **모든 프로그램**, **Microsoft Visual Studio 2012**, **Visual Studio Tools** 및 **Visual Studio 명령 프롬프트**를 선택하여 이 명령 프롬프트를 엽니다.  
  
-   [!INCLUDE[wv](../../../../includes/wv-md.md)]: [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)]의 Windows Communication Foundation 활성화 구성 요소 하위 구성 요소를 설치합니다. 이 작업을 수행하려면 제어판에서 **프로그램 추가\/제거**를 클릭한 다음 **Windows 구성 요소 추가\/제거**를 클릭합니다. 이렇게 하면 **Windows 구성 요소 마법사**가 활성화됩니다.  
  
-   Windows 7:  
  
 마지막으로 ASP.NET이 .NET Framework 버전 4를 사용하도록 구성되었는지 확인해야 합니다. ASPNET\_Regiis 도구를 –i 옵션과 함께 실행하여 이를 확인할 수 있습니다.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [ASP.NET IIS 등록 도구](http://go.microsoft.com/fwlink/?LinkId=201186)  
  
## 새 IIS 응용 프로그램을 만들거나 기존 ASP.NET 응용 프로그램을 다시 사용  
 IIS에서 호스팅되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 IIS 응용 프로그램의 내부에 있어야 합니다. 새 IIS 응용 프로그램을 만들어 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 단독으로 호스팅할 수 있습니다. 또는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] 콘텐츠\(.aspx 페이지 및 ASP.NET 웹 서비스 \[ASMX\]\)를 이미 호스팅하고 있는 기존 응용 프로그램으로 배포할 수 있습니다. 이러한 옵션에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)][WCF 서비스 및 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)에서 "ASP.NET과 함께 WCF 호스팅" 및 "ASP.NET 호환 모드에서 WCF 서비스 호스팅" 단원을 참조하세요.  
  
 [!INCLUDE[iis601](../../../../includes/iis601-md.md)] 이상 버전은 격리된 개체 지향 프로그래밍 응용 프로그램을 정기적으로 다시 시작합니다. 기본값은 1740분입니다. 지원되는 최대값은 71,582분입니다. 다시 시작은 사용할 수 없습니다. 이 속성에 [!INCLUDE[crabout](../../../../includes/crabout-md.md)][PeriodicRestartTime](http://go.microsoft.com/fwlink/?LinkId=109968)을 참조하세요.  
  
## WCF 서비스에 대한 .svc 파일 만들기  
 IIS에서 호스팅되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 IIS 응용 프로그램 내에서 특수한 콘텐츠 파일\(.svc 파일\)로 표시됩니다. 이 모델은 ASMX 페이지가 IIS 응용 프로그램 내에서 .asmx 파일로 표시되는 방식과 비슷합니다. .svc 파일에는 들어오는 메시지에 대한 응답으로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 호스팅 인프라에서 호스티드 서비스를 활성화할 수 있는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 특정 처리 지시문\([@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)\)이 포함되어 있습니다. .svc 파일의 가장 일반적인 구문은 다음 문에서 볼 수 있습니다.  
  
```  
<% @ServiceHost Service="MyNamespace.MyServiceImplementationTypeName" %>  
```  
  
 이 구문은 [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 지시문과 단일 특성 `Service`로 구성됩니다.`Service` 특성 값은 서비스 구현의 CLR\(공용 언어 런타임\) 형식 이름입니다. 이 지시문을 사용하는 것은 기본적으로 다음 코드를 사용하여 서비스 호스트를 만드는 것과 같습니다.  
  
```  
new ServiceHost( typeof( MyNamespace.MyServiceImplementationTypeName ) );  
```  
  
 서비스의 기본 주소 목록을 만드는 것과 같은 추가 호스팅 구성 작업을 수행할 수도 있습니다. 사용자 지정 <xref:System.ServiceModel.Activation.ServiceHostFactory>를 사용하여 사용자 지정 호스팅 솔루션에 사용할 지시문을 확장할 수도 있습니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호스팅하는 IIS 응용 프로그램은 <xref:System.ServiceModel.ServiceHost> 인스턴스의 만들기 및 수명을 관리하지 않습니다. 관리되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 호스팅 인프라는 .svc 파일에 대한 첫 번째 요청을 받으면 필요한 <xref:System.ServiceModel.ServiceHost> 인스턴스를 동적으로 만듭니다. 이 인스턴스는 코드에서 명시적으로 닫거나 응용 프로그램이 재활용될 때까지 해제되지 않습니다.  
  
 .svc 파일의 구문에 [!INCLUDE[crabout](../../../../includes/crabout-md.md)][@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)를 참조하세요.  
  
## IIS 응용 프로그램에 서비스 구현 배포  
 IIS에서 호스팅되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서는 [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)]과 동일한 동적 컴파일 모델을 사용합니다.[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]과 마찬가지로 IIS에서 호스팅되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에 대한 구현 코드를 다음과 같이 여러 위치에 다양한 방법으로 배포할 수 있습니다.  
  
-   GAC\(전역 어셈블리 캐시\) 또는 응용 프로그램의 \\bin 디렉터리에 있는 미리 컴파일된 .dll 파일로 배포합니다. 미리 컴파일된 이진 파일은 클래스 라이브러리의 새 버전이 배포될 때까지 업데이트되지 않습니다.  
  
-   응용 프로그램의 \\App\_Code 디렉터리에 있는 컴파일되지 않은 소스 파일로 배포합니다. 응용 프로그램의 첫 번째 요청을 처리할 때 이 디렉터리에 있는 소스 파일이 동적으로 필요합니다. \\App\_Code 디렉터리의 파일을 변경하면 다음 요청을 받았을 때 전체 응용 프로그램이 재활용되고 다시 컴파일됩니다.  
  
-   .svc 파일에 직접 배치된 컴파일되지 않은 코드로 배포합니다. @ServiceHost 지시문 다음에 서비스의 .svc 파일에서 구현 코드를 인라인으로 찾을 수도 있습니다. 인라인 코드를 변경하면 다음 요청을 받았을 때 응용 프로그램이 재활용되고 다시 컴파일됩니다.  
  
 [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] 컴파일 모델에 [!INCLUDE[crabout](../../../../includes/crabout-md.md)][ASP.NET 컴파일 개요](http://go.microsoft.com/fwlink/?LinkId=94773)를 참조하세요.  
  
## WCF 서비스 구성  
 IIS에서 호스팅되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 해당 구성을 응용 프로그램 Web.config 파일에 저장합니다. IIS에서 호스팅되는 서비스는 IIS 외부에서 호스팅된 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스와 같은 구성 요소 및 구문을 사용합니다. 그러나 다음 제약 조건은 IIS 호스팅 환경에만 적용됩니다.  
  
-   IIS에서 호스팅되는 서비스의 기본 주소  
  
-   IIS 외부의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호스트하는 응용 프로그램에서는 기본 주소 URI 집합을 <xref:System.ServiceModel.ServiceHost> 생성자에게 전달하거나 서비스 구성에 [\<host\>](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) 요소를 제공하여 호스트하는 서비스의 기본 주소를 제어할 수 있습니다. IIS에서 호스팅되는 서비스에는 해당 기본 주소를 제어하는 기능이 없습니다. IIS에서 호스팅되는 서비스의 기본 주소는 해당 .svc 파일의 주소입니다.  
  
### IIS에서 호스팅되는 서비스의 끝점 주소  
 IIS에서 호스팅되는 경우 끝점 주소는 서비스를 나타내는 .svc 파일의 주소에 항상 상대적인 것으로 간주됩니다. 다음과 같은 끝점 구성을 가진 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 기본 주소가 http:\/\/localhost\/Application1\/MyService.svc인 경우를 예로 들 수 있습니다.  
  
```  
<endpoint address="anotherEndpoint" .../>  
```  
  
 여기서는 "http:\/\/localhost\/Application1\/MyService.svc\/anotherEndpoint"에 도달할 수 있는 끝점을 제공합니다.  
  
 마찬가지로 빈 문자열을 상대 주소로 사용하는 끝점 구성 요소는 기본 주소인 http:\/\/localhost\/Application1\/MyService.svc에 도달할 수 있는 끝점을 제공합니다.  
  
```  
<endpoint address="" ... />  
```  
  
 IIS에서 호스팅되는 서비스 끝점에는 항상 상대 끝점 주소를 사용해야 합니다. 정규화된 끝점 주소\(예: http:\/\/localhost\/MyService.svc\)를 제공하면 끝점 주소가 끝점을 노출하는 서비스를 호스팅하는 IIS 응용 프로그램을 가리키지 않을 경우 서비스 배포 시 오류가 발생할 수 있습니다. 호스팅된 서비스에 상대 끝점 주소를 사용하면 이러한 잠재적 충돌을 예방할 수 있습니다.  
  
### 사용 가능한 전송  
 IIS 5.1 및 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 호스팅된 [!INCLUDE[iis601](../../../../includes/iis601-md.md)] 서비스는 HTTP 기반 통신의 사용이 제한됩니다. 이러한 IIS 플랫폼에서 HTTP가 아닌 바인딩을 사용하도록 호스팅된 서비스를 구성하면 서비스 활성화 중에 오류가 발생합니다. 기존 MSMQ 응용 프로그램과의 호환성을 위해 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]에서 지원되는 전송에는 HTTP, Net.TCP, Net.Pipe, Net.MSMQ 및 msmq.formatname이 있습니다.  
  
### HTTP 전송 보안  
 IIS에서 호스팅되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 HTTP 전송 보안\(예: Basic, Digest, Windows Integrated 인증과 같은 HTTPS 및 HTTP 인증 스키마\)을 사용할 수 있습니다. 단 WCF 서비스가 포함되어 있는 IIS 가상 디렉터리에서 해당 설정을 지원해야 합니다. 호스팅된 끝점의 바인딩에서 HTTP 전송 보안 설정은 끝점의 바인딩을 포함하는 IIS 가상 디렉터리의 전송 보안 설정과 일치해야 합니다.  
  
 예를 들어 HTTP Digest 인증을 사용하도록 구성된 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점은 HTTP Digest 인증을 사용할 수 있도록 구성된 IIS 가상 디렉터리에 있어야 합니다. IIS 설정과 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점 설정 조합이 일치하지 않으면 서비스 활성화 중에 오류가 발생합니다.  
  
## 참고 항목  
 [인터넷 정보 서비스에서의 호스팅](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)   
 [인터넷 정보 서비스 호스팅을 위한 최선의 방법](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)   
 [Windows Server App Fabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkId=201276)