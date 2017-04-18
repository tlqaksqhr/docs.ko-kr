---
title: "방법: 워크플로 응용 프로그램에서 서비스 액세스 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 925ef8ea-5550-4c9d-bb7b-209e20c280ad
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 방법: 워크플로 응용 프로그램에서 서비스 액세스
이 항목에서는 워크플로 콘솔 응용 프로그램에서 워크플로 서비스를 호출하는 방법에 대해 설명합니다.이 방법은 [방법: 메시징 작업을 사용하여 워크플로 서비스 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md) 항목에서 수행한 작업 결과에 따라 다릅니다.이 항목에서는 워크플로 응용 프로그램에서 워크플로 서비스를 호출하는 방법에 대해 설명하지만 동일한 방법을 사용하여 워크플로 응용 프로그램에서 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 호출할 수도 있습니다.  
  
### 워크플로 콘솔 응용 프로그램 프로젝트 만들기  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 시작합니다.  
  
2.  [방법: 메시징 작업을 사용하여 워크플로 서비스 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md) 항목에서 만든 MyWFService 프로젝트를 로드합니다.  
  
3.  **솔루션 탐색기**에서 **MyWFService** 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가**를 클릭한 다음 **새 프로젝트**를 선택합니다.**설치된 템플릿**에서 **워크플로**를 선택하고 워크플로 형식 목록에서 **워크플로 콘솔 응용 프로그램**을 선택합니다.다음 그림과 같이 프로젝트 이름을 MyWFClient로 지정하고 기본 위치를 사용합니다.  
  
     ![새 프로젝트 추가 대화 상자](../../../../docs/framework/wcf/feature-details/media/addnewprojectdlg.JPG "AddNewProjectDlg")  
  
     **확인** 단추를 클릭하여 **새 프로젝트 추가 대화 상자** 닫습니다.  
  
4.  프로젝트가 만들어진 후 디자이너에서 Workflow1.xaml 파일이 열립니다.도구 상자가 아직 열려 있지 않으면 **도구 상자** 탭을 클릭하여 도구 상자를 열고 압정을 클릭하여 도구 상자 창을 열린 상태로 유지합니다.  
  
5.  Ctrl\+F5를 눌러 서비스를 빌드하고 시작합니다.이전과 마찬가지로 ASP.NET Development Server가 시작되고 Internet Explorer에 WCF 도움말 페이지가 표시됩니다.이 페이지의 URI는 다음 단계에서도 사용됩니다.  
  
     ![WCF 도움말 페이지 및 URI를 표시하는 IE](../../../../docs/framework/wcf/feature-details/media/iewcfhelppagewuri.JPG "IEWCFHelpPageWURI")  
  
6.  **솔루션 탐색기**에서 **MyWFClient** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **서비스 참조 추가**를 선택합니다.**검색** 단추를 클릭하여 서비스에 대한 현재 솔루션을 검색합니다.서비스 목록에서 Service1.xamlx 옆에 있는 삼각형을 클릭합니다.Service1 옆에 있는 삼각형을 클릭하여 Service1 서비스에 의해 구현되는 계약을 나열합니다.**서비스** 목록에서 **Service1** 노드를 확장합니다.다음 그림과 같이 **작업** 목록에 Echo 작업이 표시됩니다.  
  
     ![서비스 참조 추가 대화 상자](../../../../docs/framework/wcf/feature-details/media/addservicereference.JPG "AddServiceReference")  
  
     기본 네임스페이스를 유지하고 **확인**을 클릭하여 **서비스 참조 추가** 대화 상자를 닫습니다.다음 대화 상자가 표시됩니다.  
  
     ![서비스 참조 추가 알림 대화 상자](../../../../docs/framework/wcf/feature-details/media/asrdlg.JPG "ASRDlg")  
  
     **확인**을 클릭하여 대화 상자를 닫습니다.그런 다음 Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.도구 상자에 **MyWFClient.ServiceReference1.Activities**라는 새 섹션이 추가되었습니다.다음 그림과 같이 이 섹션을 확장하고 추가된 Echo 작업을 확인합니다.  
  
     ![도구 상자의 Echo 작업](../../../../docs/framework/wcf/feature-details/media/echoactivity.JPG "EchoActivity")  
  
7.  디자이너 화면으로 <xref:System.ServiceModel.Activities.Sequence> 작업을 끌어서 놓습니다.이 작업은 도구 상자의 **제어 흐름** 섹션 아래에 있습니다.  
  
8.  <xref:System.ServiceModel.Activities.Sequence> 작업에 포커스가 있는 상태에서 **변수** 링크를 클릭하고 `inString`이라는 문자열 변수를 추가합니다.다음 그림과 같이 이 변수에 기본값인 `“Hello, world”`를 지정하고 `outString`이라는 문자열 변수를 추가합니다.  
  
     ![변수 추가](../../../../docs/framework/wcf/feature-details/media/instringvar.JPG "inStringVar")  
  
9. <xref:System.ServiceModel.Activities.Sequence>로 **Echo** 작업을 끌어서 놓습니다.속성 창에서 다음 그림과 같이 \_string 인수를 `inString` 변수에 바인딩하고 `out_string` 인수를 outString 변수에 바인딩합니다.그러면 `inString` 변수의 값이 작업에 전달되고 반환 값이 `outString` 변수에 추가됩니다.  
  
     ![변수에 인수 바인딩](../../../../docs/framework/wcf/feature-details/media/argumentbind.JPG "ArgumentBind")  
  
10. **Echo** 작업 아래로 **WriteLine** 작업을 끌어서 놓아 서비스 호출에 의해 반환되는 문자열을 표시합니다.**WriteLine** 작업은 도구 상자의 **기본 형식** 노드에 있습니다.**WriteLine** 작업의 입력란에 `outString`을 입력하여 **WriteLine** 작업의 **텍스트** 인수를 `outString` 변수에 바인딩합니다.그러면 워크플로가 다음 그림과 같이 표시됩니다.  
  
     ![완료된 클라이언트 워크플로](../../../../docs/framework/wcf/feature-details/media/completeclientwf.JPG "CompleteClientWF")  
  
11. MyWFService 솔루션을 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트 설정...**을 선택합니다.다음 그림과 같이 **여러 개의 시작 프로젝트** 라디오 단추를 선택하고 **동작** 열의 각 프로젝트에 대해 **시작**을 선택합니다.  
  
     ![시작 프로젝트 옵션](../../../../docs/framework/wcf/feature-details/media/startupprojects.JPG "StartupProjects")  
  
12. Ctrl\+F5를 눌러 서비스와 클라이언트를 둘 다 시작합니다.ASP.NET Development Server에서 서비스가 호스팅되고, Internet Explorer에 WCF 도움말 페이지가 표시되며, 콘솔 창에서 클라이언트 워크플로 응용 프로그램이 시작되고 서비스에서 반환되는 문자열\(“Hello, world”\)이 표시됩니다.  
  
## 참고 항목  
 [워크플로 서비스](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [방법: 메시징 작업을 사용하여 워크플로 서비스 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)   
 [웹 프로젝트의 워크플로에서 WCF 서비스 사용](http://go.microsoft.com/fwlink/?LinkId=207725)