---
title: "WCF 개발 도구 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9532363adafd492ca35e10e6d20c788ddf5b1d17
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-wcf-development-tools"></a>WCF 개발 도구 사용
이 단원에서는 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 서비스를 개발하는 데 사용할 수 있는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)][!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 개발 도구에 대해 설명합니다.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 템플릿을 기반으로 사용하여 서비스를 직접 신속하게 빌드한 다음 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 자동 호스트와 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트를 사용하여 서비스를 디버깅하고 테스트할 수 있습니다. 이러한 도구를 함께 사용하면 디버그 및 테스트를 원활하고 빠르게 수행할 수 있으며 초기 단계에서 호스팅 모델에 주력할 필요가 없습니다.  
  
## <a name="the-wcf-developer-tools"></a>WCF 개발자 도구  
 [WCF Visual Studio 템플릿](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에서 미리 정의된 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 프로젝트 및 항목 템플릿을 사용하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스와 관련 응용 프로그램을 신속하게 빌드할 수 있습니다.  
  
 [WCF 서비스 호스트(WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 자동 호스트(WcfSvcHost.exe)를 사용하면 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 디버거를 시작(F5)하여 구현한 서비스를 자동으로 호스팅하고 테스트할 수 있습니다. 그런 다음 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트(wcfTestClient.exe) 또는 자체 클라이언트로 서비스를 테스트하여 잠재적인 오류를 찾아 수정할 수 있습니다.  
  
 [WCF 테스트 클라이언트(WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트(WcfTestClient.exe)는 임의 형식의 매개 변수를 입력하고, 서비스에 해당 입력 내용을 전송하고, 서비스에서 되돌려 보내는 응답을 보는 데 사용할 수 있는 GUI 도구입니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 자동 호스트와 이 도구를 함께 사용하면 서비스를 매끄럽게 테스트할 수 있습니다.  
  
 [XML에서 데이터 형식 클래스 생성](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 클립보드에 저장된 XML 데이터는 코드 페이지로 붙여 넣을 수 있습니다. 데이터에 정의된 클래스는 코드 형식으로 변환됩니다.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>관리자 권한 없이 도구 사용  
 관리자 권한이 없는 사용자도 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 개발할 수 있도록 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]를 설치하는 동안 "http://+:8731/Design_Time_Addresses" 네임스페이스에 대한 ACL(액세스 제어 목록)이 만들어집니다. ACL은 (UI)로 설정되며 시스템에 로그온한 모든 대화식 사용자를 포함합니다. 관리자는 이 ACL에서 사용자를 추가 또는 제거하거나 추가 포트를 열 수 있습니다. WCF 또는 WF 템플릿에서 이 ACL을 사용하여 데이터를 기본 구성으로 보내거나 받을 수 있습니다. 또한 관리자 권한이 없는 사용자가 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 자동 호스트(wcfSvcHost.exe)를 사용할 수 있습니다.  
  
 [!INCLUDE[wv](../../../includes/wv-md.md)]의 강화된 관리자 계정으로 Netsh.exe를 사용하여 액세스 권한을 수정할 수 있습니다. 다음은 Netsh.exe를 사용하는 예입니다.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]Netsh.exe, 참조 [Netsh.exe 도구 및 명령줄 스위치를 사용 하는 방법을](http://go.microsoft.com/fwlink/?LinkId=97877)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF Visual Studio 템플릿](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [WCF 서비스 호스트(WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [WCF 테스트 클라이언트(WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
