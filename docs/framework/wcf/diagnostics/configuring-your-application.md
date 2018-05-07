---
title: 응용 프로그램 구성
ms.date: 03/30/2017
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
ms.openlocfilehash: 7dfd662fafa636e0fa97f118217ad1786d5aa444
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="configuring-your-application"></a>응용 프로그램 구성
Windows Communication Foundation (WCF).NET 구성 시스템을 사용 하 고 시스템 및 응용 프로그램 범위에서 서비스를 구성할 수 있습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 정의한 구성 설정은 `<system.serviceModel>` 섹션 그룹에 있습니다. 구성 하는 방법에 대 한 자세한 내용은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 다음 항목을 참조 하십시오.  
  
-   [서비스 구성](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 응용 프로그램에서 정의한 구성 설정은 `<appSettings>` 섹션 그룹에 정의되어 있습니다. .NET 구성 파일에서 응용 프로그램 설정에 대 한 자세한 내용은 참조 [ \<g s >](http://go.microsoft.com/fwlink/?LinkId=95159)합니다.  
  
## <a name="using-the-configuration-editor"></a>Configuration Editor 사용  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] [Configuration Editor 도구 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) 관리자와 개발자가 생성 및 구성 설정을 수정할 수 있습니다 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 그래픽 사용자 인터페이스를 사용 하 여 서비스입니다. 이 도구를 사용하면 XML 구성 파일을 직접 수정하지 않고도 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 바인딩, 동작, 서비스 및 진단에 대한 설정을 관리할 수 있습니다.  
  
## <a name="editing-configuration-files-in-visual-studio"></a>Visual Studio에서 구성 파일 편집  
 구성 파일을 편집 하려면는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Visual Studio에서 프로젝트 서비스를 마우스 오른쪽 단추로 클릭에서 **솔루션 탐색기** 선택 하 고는 **WCF 구성 편집** 상황에 맞는 메뉴 항목입니다. 그러면는 [Configuration Editor 도구 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)합니다.  
  
> [!NOTE]
>  구성 파일을 편집 하는 경우는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 에서 마우스 오른쪽 단추로 클릭 하 여 Visual Studio에서 웹 서비스 프로젝트 **솔루션 탐색기**, 다음에 유의 **WCF 구성 편집** 상황에 맞는 메뉴 항목이 누락 되었습니다. 이 문제를 해결 하려면, 클릭는 **도구** 메뉴 선택 **WCF 서비스 구성 편집기**합니다. 그런 다음 구성 파일을 마우스 오른쪽 단추로 클릭 하 사용할 수는 **WCF 구성 편집** 상황에 맞는 메뉴 항목입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Configuration Editor 도구(SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)  
 [서비스 구성](../../../../docs/framework/wcf/configuring-services.md)  
 [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)
