---
title: "Windows Communication Foundation에 대해 Internet Information Services 7.0 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Windows Communication Foundation에 대해 Internet Information Services 7.0 구성
IIS\(인터넷 정보 서비스\) 7.0은 필요한 구성 요소를 선택적으로 설치할 수 있는 모듈형 디자인입니다.이러한 디자인은 [!INCLUDE[wv](../../../../includes/wv-md.md)]에 도입된 새로운 매니페스트 기반의 컴포넌트화 기술을 바탕으로 합니다.[!INCLUDE[iisver](../../../../includes/iisver-md.md)]에는 개별적으로 설치할 수 있는 40개 이상의 독립 실행형 기능 구성 요소가 있습니다.따라서 IT 전문가는 필요에 따라 편리하게 설치를 사용자 지정할 수 있습니다.이 항목에서는 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]을 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]와 함께 사용할 수 있도록 구성하는 방법과 필요한 구성 요소를 결정하는 방법에 대해 설명합니다.  
  
## 최소 설치: WAS 설치  
 전체 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 패키지를 최소 설치하려면 WAS\(Windows Process Activation Service\)를 설치합니다.WAS는 독립 실행형 기능으로, 모든 [!INCLUDE[wv](../../../../includes/wv-md.md)] 운영 체제\(Home Basic, Home Premium, Business, Ultimate 및 Enterprise\)에서 사용할 수 있는 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]의 유일한 기능입니다.  
  
 제어판에서 **프로그램**을 클릭한 다음 **프로그램 및 기능** 아래에 나열된 **Windows 기능 사용\/사용 안 함**을 클릭하면 다음 그림과 같이 WAS 구성 요소가 목록에 표시됩니다.  
  
 ![Windows 기능 사용&#47;사용 안 함 대화 상자](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc\_TurnFeaturesOnOrOffs")  
  
 이 기능에는 다음과 같은 하위 구성 요소가 있습니다.  
  
-   .NET 환경  
  
-   구성 API  
  
-   프로세스 모델  
  
 WAS의 루트 노드를 선택하면, **프로세스 모델** 하위 노드만 기본적으로 선택됩니다.이 설치에서는 웹 서버에 대한 지원이 없으므로 WAS만 설치됩니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 또는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램을 작동하려면 **.NET 환경** 확인란을 선택합니다.이는 모든 WAS 구성 요소가 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 작동에 필요함을 의미합니다.이러한 구성 요소는 일단 설치되면 자동으로 선택됩니다.  
  
## IIS 7.0: 기본 설치  
 **인터넷 정보 서비스** 기능을 선택하면 다음 그림과 같이 하위 노드 일부가 자동으로 선택됩니다.  
  
 ![IIS 7.0 기능에 대한 기본 설정](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc\_TurningFeaturesOnOrOff2")  
  
 이것은 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]의 기본 설치입니다.이 설치에서는 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]을 사용하여 HTML 페이지나 기타 콘텐츠와 같은 정적 콘텐츠를 제공할 수 있습니다.하지만 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 또는 CGI 응용 프로그램을 실행하거나 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호스팅할 수 없습니다.  
  
## IIS 7.0: ASP.NET 지원과 함께 설치  
 IIS 7.0에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]이 작동하도록 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]을 설치해야 합니다.**ASP.NET**을 선택하면 화면이 다음 그림과 같이 표시됩니다.  
  
 ![Asp.NET 필수 설정](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc\_TrunFeaturesOnOrOFf3s")  
  
 이는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램이 모두 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]에서 작동하기 위한 최소 환경입니다.  
  
## IIS 7.0: IIS 6.0 호환성 구성 요소와 함께 설치  
 Visual Studio 2005 또는 [!INCLUDE[iis601](../../../../includes/iis601-md.md)] Metabase API가 사용되는 가상 응용 프로그램을 구성하는 기타 자동화 스크립트나 도구\(예: Adsutil.vbs\)가 있는 시스템에 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]을 설치하려면 [!INCLUDE[iis601](../../../../includes/iis601-md.md)]**스크립팅 도구**를 선택해야 합니다.그러면 [!INCLUDE[iis601](../../../../includes/iis601-md.md)]**관리 호환성**의 다른 하위 노드가 자동으로 선택됩니다.이 작업이 끝나면 화면이 다음 그림과 같이 표시됩니다.  
  
 ![IIS 6.0 관리 호환성 설정](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc\_TurnFeaturesOnOrOff5s")  
  
 이 설치에서는 [!INCLUDE[iisver](../../../../includes/iisver-md.md)], [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 및 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 기능을 사용하는 데 필요한 모든 요소와 웹에서 사용할 수 있는 샘플이 제공됩니다.  
  
## 요청 제한  
 IIS 7이 설치된 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 `maxUri` 및 `maxQueryStringSize` 설정의 기본값이 변경되었습니다.기본적으로 IIS 7.0의 요청 필터링은 URL 길이로 4096자를 허용하며 쿼리 문자열 길이로 2048자를 허용합니다.이러한 기본값을 변경하려면 다음 XML을 App.config 파일에 추가합니다.  
  
 `<system.webServer>`  
  
 `<security>`  
  
 `<requestFiltering>`  
  
 `<requestLimits maxUrl=”8192” maxQueryString=”8192” />`  
  
 `</requestFiltering>`  
  
 `</security>`  
  
 `</system.webServer>`  
  
## 참고 항목  
 [WAS Activation 아키텍처](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)   
 [WCF와 함께 사용하도록 WAS 구성](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)   
 [방법: WCF Activation 구성 요소 설치 및 구성](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)   
 [Windows Server AppFabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkId=201276)