---
title: "방법: 메시징 작업을 사용하여 워크플로 서비스 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 53d094e2-6901-4aa1-88b8-024b27ccf78b
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# 방법: 메시징 작업을 사용하여 워크플로 서비스 만들기
이 항목에서는 메시징 작업을 사용하여 간단한 워크플로 서비스를 만드는 방법을 보여 줍니다.  이 항목에서는 서비스가 메시징 작업만으로 구성된 워크플로 서비스를 만드는 방법에 중점을 둡니다.  실제 서비스의 워크플로에는 다른 많은 작업이 포함되어 있습니다.  이 항목의 서비스에서는 문자열을 받아서 호출자에게 반환하는 Echo라는 하나의 작업을 구현합니다.  이 항목은 시리즈로 된 두 항목 중 첫 번째 항목입니다.  다음 항목인 [방법: 워크플로 응용 프로그램에서 서비스 액세스](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md)에서는 이 항목에서 만든 서비스를 호출할 수 있는 워크플로 응용 프로그램을 만드는 방법을 설명합니다.  
  
### 워크플로 서비스 프로젝트를 만들려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]를 시작합니다.  
  
2.  **파일** 메뉴를 클릭하고 **새로 만들기**를 선택한 다음 **프로젝트**를 선택하여 **새 프로젝트 대화 상자**를 표시합니다.  설치된 템플릿 목록에서 **워크플로**를 선택하고 프로젝트 형식 목록에서 **WCF 워크플로 서비스 응용 프로그램**을 선택합니다.  다음 그림과 같이 프로젝트 이름을 `MyWFService`로 지정하고 기본 위치를 사용합니다.  
  
     **확인** 단추를 클릭하여 **새 프로젝트 대화 상자** 닫습니다.  
  
3.  프로젝트가 생성되면 다음 그림과 같이 Service1.xamlx 파일이 디자이너에서 열립니다.  
  
     ![디자이너에 표시된 기본 워크플로](../../../../docs/framework/wcf/feature-details/media/defaultworkflowservice.JPG "DefaultWorkflowService")  
  
     **순차 서비스**라는 작업을 마우스 오른쪽 단추로 클릭하고 **삭제**를 선택합니다.  
  
### 워크플로 서비스를 구현하려면  
  
1.  화면 왼쪽에 있는 **도구 상자** 탭을 선택하여 도구 상자를 표시하고 압정을 클릭하여 창을 열린 상태로 유지합니다.  다음 그림과 같이 도구 상자의 **메시징** 섹션을 확장하여 메시징 작업과 메시징 작업 템플릿을 표시합니다.  
  
     ![메시징 탭이 확장된 도구 상자](../../../../docs/framework/wcf/feature-details/media/wfdesignertoolbox.JPG "WFDesignerToolbox")  
  
2.  **ReceiveAndSendReply** 템플릿을 워크플로 디자이너로 끌어서 놓습니다.  그러면 다음 그림과 같이 <xref:System.ServiceModel.Activities.Sequence>Receive 작업과 그 뒤에  작업이 포함된 <xref:System.ServiceModel.Activities.SendReply> 작업이 만들어집니다.  
  
     ![디자이너의 ReceiveAndSendReply 템플릿](../../../../docs/framework/wcf/feature-details/media/receiveandsendreply.JPG "ReceiveAndSendReply")  
  
     <xref:System.ServiceModel.Activities.SendReply> 작업의 <xref:System.ServiceModel.Activities.SendReply.Request%2A> 속성이 `Receive` 작업이 회신하는 <xref:System.ServiceModel.Activities.Receive> 작업의 이름인 <xref:System.ServiceModel.Activities.SendReply>로 설정됩니다.  
  
3.  <xref:System.ServiceModel.Activities.Receive> 작업에서 `OperationName`이라는 입력란에 **Echo**를 입력합니다.  그러면 서비스가 구현하는 작업의 이름이 정의됩니다.  
  
     ![작업 이름 지정](../../../../docs/framework/wcf/feature-details/media/defineoperation.JPG "DefineOperation")  
  
4.  <xref:System.ServiceModel.Activities.Receive> 작업이 선택되어 있는 상태에서 속성 창이 아직 열려 있지 않은 경우 **보기** 메뉴를 클릭하고 **속성 창**을 선택하여 속성 창을 엽니다.  다음 그림과 같이 **속성 창**에서 **CanCreateInstance**가 나타날 때까지 아래로 스크롤하고 확인란을 클릭합니다.  이렇게 설정하면 메시지를 받을 때 필요한 경우 워크플로 서비스 호스트가 서비스의 새 인스턴스를 만들 수 있습니다.  
  
     ![CanCreateInstance 속성](../../../../docs/framework/wcf/feature-details/media/cancreateinstance.JPG "CanCreateInstance")  
  
5.  디자이너의 왼쪽 아래 모퉁이에서 <xref:System.ServiceModel.Activities.Sequence> 작업을 선택하고 **변수** 단추를 클릭합니다.  그러면 변수 편집기가 표시됩니다.  **변수 만들기** 링크를 클릭하여 작업에 보내진 문자열을 저장하는 변수를 추가합니다.  다음 그림과 같이 변수 이름을 `msg`로 지정하고 해당 **변수** 형식을 문자열로 설정합니다.  
  
     ![변수 추가](../../../../docs/framework/wcf/feature-details/media/addvariable.JPG "AddVariable")  
  
     **변수** 단추를 다시 클릭하여 변수 편집기를 닫습니다.  
  
6.  작업의 **콘텐츠** 입력란에 있는 <xref:System.ServiceModel.Activities.Receive> **정의...** 링크를 클릭하여 **콘텐츠 정의** 대화 상자를 표시합니다.  다음 그림과 같이 **매개 변수** 라디오 단추를 선택하고 **새 매개 변수 추가** 링크를 클릭한 다음 `이름` 입력란에 **inMsg**를 입력합니다. 그런 다음 **형식** 드롭다운 목록 상자에서 **문자열**을 선택하고 `할당 대상` 입력란에 **msg**를 입력합니다.  
  
     ![매개 변수 콘텐츠 추가](../../../../docs/framework/wcf/feature-details/media/parameterscontent.jpg "ParametersContent")  
  
     그러면 받기 작업이 문자열 매개 변수를 받고 데이터가 `msg` 변수에 바인딩되도록 지정됩니다.  **확인**을 클릭하여 **콘텐츠 정의** 대화 상자를 닫습니다.  
  
7.  **정의...** 작업의 **콘텐츠** 상자에 있는 <xref:System.ServiceModel.Activities.SendReply> 링크를 클릭하여 **콘텐츠 정의** 대화 상자를 표시합니다.  다음 그림과 같이 **매개 변수** 라디오 단추를 선택하고 **새 매개 변수 추가** 링크를 클릭한 다음 `이름` 입력란에 **msg**를 입력합니다. 그런 다음 **형식** 드롭다운 목록 상자에서 **문자열**을 선택하고 `값` 입력란에 **msg**를 입력합니다.  
  
     ![매개 변수 콘텐츠 추가](../../../../docs/framework/wcf/feature-details/media/parameterscontent2.jpg "ParametersContent2")  
  
     그러면 <xref:System.ServiceModel.Activities.SendReply> 작업이 메시지 또는 메시지 계약 형식을 보내고 데이터가 `msg` 변수에 바인딩되도록 지정됩니다.  이 작업이 <xref:System.ServiceModel.Activities.SendReply> 작업이므로 이는 이 작업이 클라이언트에 다시 보내는 메시지를 채우는 데 `msg`의 데이터가 사용됨을 의미합니다.  **확인**을 클릭하여 **콘텐츠 정의** 대화 상자를 닫습니다.  
  
8.  **빌드** 메뉴를 클릭하고 **솔루션 빌드**를 선택하여 솔루션을 저장하고 빌드합니다.  
  
## 워크플로 서비스 프로젝트 구성  
 워크플로 서비스가 완료되었으므로  이 단원에서는 워크플로 서비스 솔루션을 손쉽게 호스팅하고 실행할 수 있도록 구성하는 방법에 대해 설명합니다.  이 솔루션은 ASP.NET Development Server를 사용하여 서비스를 호스팅합니다.  
  
#### 프로젝트 시작 옵션을 설정하려면  
  
1.  **솔루션 탐색기**에서 **MyWFService**를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택하여 **프로젝트 속성** 대화 상자를 표시합니다.  
  
2.  다음 그림과 같이 **웹** 탭을 선택하고 **시작 작업** 아래에서 **특정 페이지**를 선택한 다음 입력란에 `Service1.xamlx`를 입력합니다.  
  
     ![프로젝트 속성 대화 상자](../../../../docs/framework/wcf/feature-details/media/projectpropertiesdlg.JPG "ProjectPropertiesDlg")  
  
     그러면 ASP.NET Development Server에서 Service1.xamlx에 정의된 서비스가 호스팅됩니다.  
  
3.  Ctrl\+F5를 눌러 서비스를 시작합니다.  그러면 다음 그림과 같이 바탕 화면의 오른쪽 아래에 ASP.NET Development Server 아이콘이 표시됩니다.  
  
     ![ASP.NET Developer Server 아이콘](../../../../docs/framework/wcf/feature-details/media/aspnetdevservericon.JPG "ASPNETDEVServerIcon")  
  
     또한 Internet Explorer에 서비스에 대한 WCF 서비스 도움말 페이지가 표시됩니다.  
  
     ![WCF 도움말 페이지](../../../../docs/framework/wcf/feature-details/media/wcfhelppate.JPG "WCFHelpPate")  
  
4.  [방법: 워크플로 응용 프로그램에서 서비스 액세스](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) 항목을 계속 진행하여 이 서비스를 호출하는 워크플로 클라이언트를 만듭니다.  
  
## 참고 항목  
 [워크플로 서비스](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [워크플로 서비스 호스팅 개요](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)   
 [메시징 활동](../../../../docs/framework/wcf/feature-details/messaging-activities.md)