---
title: WCF 개발 도구 사용
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: bfe71c8f4ee515e1895f27166bcb5931806dabea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-wcf-development-tools"></a>WCF 개발 도구 사용
이 섹션에서는 개발에 도움이 되는 Visual Studio 개발 도구 설명에 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]서비스입니다.  
  
 하는 데 Visual Studio 템플릿 기반으로 신속 하 게 서비스를 작성 한 후 사용 하 여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 자동 호스트 및 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트를 디버깅 하 고 서비스를 테스트 합니다. 이러한 도구를 함께 사용하면 디버그 및 테스트를 원활하고 빠르게 수행할 수 있으며 초기 단계에서 호스팅 모델에 주력할 필요가 없습니다.  
  
## <a name="the-wcf-developer-tools"></a>WCF 개발자 도구  
 [WCF Visual Studio 템플릿](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 Visual Studio에서 미리 정의 된 Visual Studio 프로젝트 템플릿과 항목 템플릿을 사용 하 여 신속 하 게 작성할 수 있습니다 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 및 해당 응용 프로그램입니다.  
  
 [WCF 서비스 호스트(WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 자동 호스트 (WcfSvcHost.exe)를 사용 하면 (F5) 자동으로 호스팅하고 테스트할 구현한 서비스를 Visual Studio 디버거를 시작할 수 있습니다. 그런 다음 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트(wcfTestClient.exe) 또는 자체 클라이언트로 서비스를 테스트하여 잠재적인 오류를 찾아 수정할 수 있습니다.  
  
 [WCF 테스트 클라이언트(WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트(WcfTestClient.exe)는 임의 형식의 매개 변수를 입력하고, 서비스에 해당 입력 내용을 전송하고, 서비스에서 되돌려 보내는 응답을 보는 데 사용할 수 있는 GUI 도구입니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 자동 호스트와 이 도구를 함께 사용하면 서비스를 매끄럽게 테스트할 수 있습니다.  
  
 [XML에서 데이터 형식 클래스 생성](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 클립보드에 저장된 XML 데이터는 코드 페이지로 붙여 넣을 수 있습니다. 데이터에 정의된 클래스는 코드 형식으로 변환됩니다.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>관리자 권한 없이 도구 사용  
 개발 하는 관리자 권한이 없는 사용자도 사용할 수 있도록 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 ACL (액세스 제어 목록) 네임 스페이스에 대해 만들어집니다 "http://+:8731/Design_Time_Addresses" Visual Studio의 설치 중입니다. ACL은 (UI)로 설정되며 시스템에 로그온한 모든 대화식 사용자를 포함합니다. 관리자는 이 ACL에서 사용자를 추가 또는 제거하거나 추가 포트를 열 수 있습니다. WCF 또는 WF 템플릿에서 이 ACL을 사용하여 데이터를 기본 구성으로 보내거나 받을 수 있습니다. 또한 관리자 권한이 없는 사용자가 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 자동 호스트(wcfSvcHost.exe)를 사용할 수 있습니다.  
  
 [!INCLUDE[wv](../../../includes/wv-md.md)]의 강화된 관리자 계정으로 Netsh.exe를 사용하여 액세스 권한을 수정할 수 있습니다. 다음은 Netsh.exe를 사용하는 예입니다.  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Netsh.exe에 대 한 자세한 내용은 참조 [Netsh.exe 도구 및 명령줄 스위치를 사용 하는 방법을](http://go.microsoft.com/fwlink/?LinkId=97877)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF Visual Studio 템플릿](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [WCF 서비스 호스트(WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [WCF 테스트 클라이언트(WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
