---
title: "WCF 서비스 게시 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c806b253-cd47-4b96-b831-e73cbf08808f
caps.latest.revision: 22
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# WCF 서비스 게시
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스 게시는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 호스트 및 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트에서 제공하는 초기 개발 환경에서부터 테스트 목적으로 프로덕션 환경에 응용 프로그램을 실제로 배포하는 것에 이르기까지 프로세스를 진행하도록 도와 줍니다.  최종 배포 계획에 커밋하기 전에 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스 게시를 사용하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스가 올바르게 수행되고 게시할 준비가 되었는지 확인할 수 있습니다.  또한 테스트 목적으로 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리를 여러 대상 위치에 배포할 수도 있습니다.  
  
## 지원되는 서비스 및 대상 위치  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 게시에서는 다음과 같은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리 템플릿 집합과 해당하는 항목 템플릿에서 만든 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 게시할 수 있습니다.  
  
-   [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리 템플릿과 항목 템플릿  
  
-   순차 워크플로 서비스 라이브러리 템플릿과 항목 템플릿  
  
-   상태 시스템 워크플로 서비스 라이브러리 템플릿과 항목 템플릿  
  
-   배포 서비스 라이브러리  
  
 **파일** \-\> **새 프로젝트** \-\> **Visual Basic** 또는 **Visual C\#** \-\> **WCF**를 선택하여 이러한 서비스 템플릿을 찾을 수 있습니다.  
  
 다음과 같은 대상 위치에 서비스를 게시할 수 있습니다.  
  
-   로컬 IIS  
  
-   파일 시스템  
  
-   FTP 사이트  
  
-   원격 사이트  
  
## WCF 서비스 게시 사용  
 서비스 구현을 배포하려면 다음 단계를 수행합니다.  
  
1.  높은 권한으로 Visual Studio를 엽니다. 즉, 실행 파일을 마우스 오른쪽 단추로 클릭하고 "관리자 권한으로 실행"을 사용하여 실행합니다.  IIS 7.0 이상을 사용하는 경우 제어판에서 "Windows 기능 사용\/사용 안 함"을 사용하여 "IIS 메타베이스 및 IIS 6 구성 호환성" 구성 요소를 설치했는지 확인합니다.  
  
2.  서비스 프로젝트를 열고 주 메뉴에서 **빌드**\-\>**\<프로젝트 이름\> 게시**를 선택하거나 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **게시**를 클릭합니다.  
  
3.  **게시** 창이 나타납니다.  **…** 단추를 클릭하여 서비스를 배포할 대상 위치를 지정합니다.  로컬 IIS, 파일 시스템, FTP 사이트 또는 원격 사이트에 응용 프로그램을 배포할 수 있습니다.  응용 프로그램을 로컬 IIS에 배포하는 경우 오른쪽 위 모퉁이에서 **새 웹 응용 프로그램 만들기** 아이콘을 클릭하여 웹 사이트를 선택하고 그 아래에 웹 응용 프로그램을 만들 수 있습니다.  
  
4.  주 창에서 **게시**를 클릭하면 응용 프로그램이 지정된 대상 위치에 배포되고 Web.config, .svc 및 어셈블리 파일이 대상 디렉터리에 복사됩니다.  .  .svc의 이름은 “ProjectName.ServiceName.svc”가 됩니다.  서비스가 성공적으로 게시된 후 Visual Studio 출력 창에서 “http:\/\/localhost\/WebApplicationFolderName에 연결하는 중...”과 유사한 핫링크를 찾을 수 있습니다.  Ctrl 키를 누르고 링크를 클릭하여 Visual Studio 내에서 브라우저 페이지를 열고 서비스 디렉터리 구조를 볼 수 있습니다.  
  
     사이트를 찾을 수 없으면 IIS에서 디렉터리 브라우저를 사용하도록 설정되지 않았을 수 있습니다.  "가능한 해결 방법" 단원의 팁에 따라 디렉터리 브라우저를 사용하도록 설정하세요.  또는 “http:\/\/localhost\/WebApplicationFolderName\/ProjectName.ServiceName.svc”를 직접 입력하여 서비스 페이지를 볼 수 있습니다.  
  
 **게시**를 사용하여 프로젝트에 정의된 모든 서비스의 어셈블리, 구성 및 .svc 파일을 대상 위치에 복사하고 대상의 기존 파일을 덮어쓸 수 있습니다.  
  
 응용 프로그램을 로컬 IIS에 배포하도록 선택하면 IIS 설치와 관련된 오류가 발생할 수 있습니다.  IIS가 제대로 설치되었는지 확인하세요.  브라우저에 “http:\/\/localhost”를 입력하고 IIS 기본 페이지가 나타나는지 확인할 수 있습니다.  경우에 따라 IIS에서 ASP.NET 또는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]의 잘못된 등록 때문에 문제가 발생할 수도 있습니다.  Visual Studio 명령 프롬프트를 열고 “aspnet\_regiis.exe \-ir” 명령을 실행하여 ASP.NET 등록 문제를 해결하거나 “ServiceModelReg.exe –ia” 명령을 실행하여 WCF 등록 문제를 해결할 수 있습니다.  
  
## 게시를 위해 생성되는 파일  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리가 웹 호스트되기 전에 도구에서 어셈블리 파일, Web.config 파일 및 .svc 파일이 생성됩니다.  이러한 파일이 모두 대상 위치에 복사된 후에  서비스가 게시됩니다.  
  
### 어셈블리 파일  
 이 도구를 사용하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 게시하면 먼저 서비스가 자동으로 빌드되고 빌드 후에 서비스 프로젝트에서 어셈블리 파일이 생성됩니다.  
  
### .SVC 파일  
 게시 작업에서는 각 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스에 대해 버전 유효성 확인을 위해 \*.svc 파일이 기존에 있는지 여부와 관계없이 생성됩니다.  [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리 및 배포 서비스 라이브러리용과 순차 및 상태 시스템 워크플로 서비스 라이브러리용의 서로 다른 두 가지 svc 파일이 있습니다.  생성된 \*.svc 파일은 대상 위치의 루트 폴더에 복사됩니다.  
  
### Web.config 파일  
 서비스 프로젝트를 특정 대상 위치에 게시할 때마다 Web.config 파일이 만들어집니다.  
  
 생성된 Web.config 파일에는 웹 호스팅에 사용되는 웹 섹션 및 다음과 같은 변경 내용과 함께 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 라이브러리에 대한 App.config의 내용이 포함됩니다.  
  
-   기본 주소는 제외됩니다.  
  
-   `<diagnostics>` 요소의 설정은 대상 플랫폼의 추적 설정을 유지하기 위해 제외됩니다.  
  
## HTTP가 아닌 바인딩을 사용하여 WCF 서비스를 IIS에 게시  
 IIS 7.0 이상을 사용하는 경우 HTTP가 아닌 바인딩을 사용하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 IIS에 게시할 수 있습니다.  몇 가지 사전 구성 작업을 수행해야 합니다.  자세한 내용은 [Windows Process Activation Service에서의 호스팅](../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)의 항목을 참조하세요.  
  
## 보안  
 IIS는 관리자 계정으로 실행해야 하므로 로컬 IIS에 게시하려면 관리자 권한이 필요합니다.  관리자 권한이 없는 사용자가 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 게시를 여는 경우 IIS를 대상 위치로 사용할 수 없습니다.  파일 시스템, FTP 사이트 또는 원격 사이트에는 관리자 권한 없이도 게시할 수 있습니다.  
  
## 참고 항목  
 [WCF Visual Studio 템플릿](../../../docs/framework/wcf/wcf-vs-templates.md)   
 [WCF 서비스 호스트\(WcfSvcHost.exe\)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)   
 [WCF 테스트 클라이언트\(WcfTestClient.exe\)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)