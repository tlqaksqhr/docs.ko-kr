---
title: WCF 서비스 게시
ms.date: 03/30/2017
ms.assetid: c806b253-cd47-4b96-b831-e73cbf08808f
ms.openlocfilehash: 258c7e65b69648477e58880f35b100a9378dc9c0
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806463"
---
# <a name="wcf-service-publishing"></a>WCF 서비스 게시
Windows Communication Foundation (WCF) 서비스 게시 사용 하면 실제로 테스트 목적으로 프로덕션 환경에 응용 프로그램을 배포 하려면 WCF 서비스 호스트 및 WCF 테스트 클라이언트에서 제공 하는 초기 개발 환경에서 진행 하 고 있습니다. 최종 배포 계획에 커밋하기 전에 사용할 수 있습니다 Windows Communication Foundation (WCF) 서비스 게시 WCF 서비스가 올바르게 수행 하 고 게시할 준비가 됩니다. 또한 WCF 서비스 라이브러리를 테스트 하기 위한 다양 한 대상 위치에 배포할 수 있습니다.  
  
## <a name="supported-services-and-target-locations"></a>지원되는 서비스 및 대상 위치  
 WCF 서비스 게시는 WCF 서비스 라이브러리 템플릿 및 다음과 같은 해당 항목 템플릿 집합에서 생성 하는 WCF 서비스 게시를 지원 합니다.  
  
-   WCF 서비스 라이브러리 템플릿과 항목 템플릿  
  
-   배포 서비스 라이브러리  
  
 이러한 서비스 템플릿을 선택 하 여 찾을 수 있습니다 **파일** -> **새 프로젝트** -> **Visual Basic** 또는 **Visual C#**  ->  **WCF**합니다. 사용 하 여 게시할 수 있습니다 (WCF 워크플로 서비스 응용 프로그램 및 WCF 서비스 응용 프로그램 포함)이이 위치에서 다른 WCF 템플릿을 [One-click 웹 응용 프로그램에 대 한 게시](https://msdn.microsoft.com/library/dd465337\(v=vs.110\).aspx)합니다.  
  
 다음과 같은 대상 위치에 서비스를 게시할 수 있습니다.  
  
-   로컬 IIS  
  
-   파일 시스템  
  
-   FTP 사이트  
  
## <a name="using-wcf-service-publishing"></a>WCF 서비스 게시 사용  
 서비스 구현을 배포하려면 다음 단계를 수행합니다.  
  
1.  상승 된 권한으로 Visual Studio를 엽니다 (실행 파일을 마우스 오른쪽 단추로 클릭 하 고 유틸리티를 실행 하려면 "관리자 권한으로 실행"을 사용 하 여).  이상 버전에서는 사용 하 여 "IIS 메타 베이스 및 iis 6 구성 호환성" 구성 요소를 설치 했는지를 확인 또는 IIS 7.0을 사용 하는 경우 "' Windows 기능 사용 설정 하거나 해제" 제어판에서.  
  
2.  서비스 프로젝트를 열고, 선택 **빌드**->**게시 \<프로젝트 이름 >** 주 메뉴에서에서 프로젝트를 마우스 오른쪽 단추로 클릭 하거나 **솔루션 탐색기**클릭 **게시**합니다.  
  
3.  **게시** 창이 나타납니다. 클릭는 **...** . 단추를 클릭하여 서비스를 배포할 대상 위치를 지정합니다. 로컬 IIS, 파일 시스템 또는 FTP 사이트에 응용 프로그램을 배포 하도록 선택할 수 있습니다. 로컬 IIS에 응용 프로그램을 배포할 경우 웹 사이트를 선택 하 고, 대상 웹 응용 프로그램을 클릭 하 여 만들 수는 **새 웹 응용 프로그램 만들기** 오른쪽 위 모퉁이에서 아이콘입니다.  
  
4.  클릭 한 후 **게시** 주 창에서 Visual Studio 응용 프로그램을 지정한 대상 위치에 배포 및 대상 디렉터리에 Web.config,.svc 및 어셈블리 파일을 복사 합니다. 이어야 합니다. .Svc의 이름은 됩니다 "projectname.servicename.svc"입니다. 서비스를 성공적으로 게시 된 후 Visual Studio 출력 창의 "하이퍼링크로 연결" 비슷합니다는 옥을 찾을 수 있습니다http://localhost/WebApplicationFolderName" http://localhost/WebApplicationFolderName ...". Ctrl 키를 누르고 링크를 클릭하여 Visual Studio 내에서 브라우저 페이지를 열고 서비스 디렉터리 구조를 볼 수 있습니다.  
  
     사이트를 찾을 수 없으면 IIS에서 디렉터리 브라우저를 사용하도록 설정되지 않았을 수 있습니다. 사용 하도록 설정 하려면 "가능한 해결 방법" 섹션의 팁을 따르십시오. 또는 있습니다 직접 입력할 수"하이퍼링크"http://localhost/WebApplicationFolderName" http://localhost/WebApplicationFolderName/ProjectName.ServiceName.svc를" 서비스 페이지를 표시 합니다.  
  
 사용할 수 있습니다 **게시** 을 어셈블리, 구성 및 대상 위치에 프로젝트에 정의 된 모든 서비스에 대 한.svc 파일을 복사 하려면 지정한 대상에 기존 파일을 덮어씁니다.  
  
 응용 프로그램을 로컬 IIS에 배포하도록 선택하면 IIS 설치와 관련된 오류가 발생할 수 있습니다. IIS가 제대로 설치되었는지 확인하세요. "하이퍼링크"를 입력할 수 있습니다http://localhost" http://localhost" 브라우저에서 확인 여부를 IIS 기본 페이지가 표시 합니다.  일부 경우에도 IIS에서 ASP.NET 또는 WCF 잘못 된 등록 하 여 대 문제 발생할 수 있습니다. Visual Studio 명령 프롬프트를 열고 및 ASP.NET 등록 문제를 해결 하는 명령 "aspnet_regiis.exe-ir"를 실행 하거나 "ServiceModelReg.exe – ia" 명령을 실행 하는 WCF 등록 문제를 해결 수 있습니다.  
  
## <a name="files-generated-for-publishing"></a>게시를 위해 생성되는 파일  
 다음 파일은 도구에서 생성 하는 WCF 서비스 라이브러리를 하려면 먼저 웹 호스팅: 어셈블리 파일, Web.config 파일 및.svc 파일입니다. 이러한 파일이 모두 대상 위치에 복사된 후에 서비스가 게시됩니다.  
  
### <a name="assembly-files"></a>어셈블리 파일  
 WCF 서비스를 게시할 때이 도구를 사용 하 여 서비스는 자동으로 먼저 만들어지고 어셈블리 파일이 만든 후 서비스 프로젝트에서 생성 됩니다.  
  
### <a name="svc-file"></a>.SVC 파일  
 게시 작업은 파일 버전 유효성을 확인할 여부를 존재 여부 각 WCF 서비스에 대 한 *.svc 파일을 생성 합니다. Svc 파일이 서로 다른 두: WCF 서비스 라이브러리 및 배포 서비스 라이브러리 및 다른 순차 및 상태 시스템 워크플로 서비스 라이브러리에 대 한 합니다. 생성 된 \*.svc 파일은 대상 위치의 루트 폴더로 복사 합니다.  
  
### <a name="webconfig-file"></a>Web.config 파일  
 서비스 프로젝트를 특정 대상 위치에 게시할 때마다 Web.config 파일이 만들어집니다.  
  
 생성 된 Web.config 파일에 다음 변경 내용으로 WCF 서비스 라이브러리에 대 한 App.config의 내용이 및 웹 호스팅에 대해 사용 되는 웹 섹션에 포함 됩니다.  
  
-   기본 주소는 제외됩니다.  
  
-   `<diagnostics>` 요소의 설정은 대상 플랫폼의 추적 설정을 유지하기 위해 제외됩니다.  
  
## <a name="publishing-wcf-services-with-non-http-bindings-to-iis"></a>HTTP가 아닌 바인딩을 사용하여 WCF 서비스를 IIS에 게시  
 Iis 7.0을 사용 하는 경우 이상 버전에서는 IIS에 HTTP가 아닌 바인딩을 사용 하는 WCF 서비스를 게시할 수 있습니다. 몇 가지 사전 구성 작업을 수행해야 합니다. 자세한 내용은 항목을 참조 하십시오 [Windows Process Activation Service에서의 호스팅](../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)합니다.  
  
## <a name="security"></a>보안  
 IIS는 관리자 계정으로 실행해야 하므로 로컬 IIS에 게시하려면 관리자 권한이 필요합니다. 관리자 권한 없이 사용자가 WCF 서비스 게시를 하는 경우 IIS를 대상 위치로 사용할 수 없는 경우 파일 시스템 또는 FTP 사이트에 게시 하는 관리자 권한 없이 작동합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF Visual Studio 템플릿](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [WCF 서비스 호스트(WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [WCF 테스트 클라이언트(WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
