---
title: '방법: 메시징 작업을 사용하여 워크플로 서비스 만들기'
ms.date: 03/30/2017
ms.assetid: 53d094e2-6901-4aa1-88b8-024b27ccf78b
ms.openlocfilehash: b646d1e242d570ec758865b48ab3720033ea9302
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-workflow-service-with-messaging-activities"></a>방법: 메시징 작업을 사용하여 워크플로 서비스 만들기
이 항목에서는 메시징 작업을 사용하여 간단한 워크플로 서비스를 만드는 방법을 보여 줍니다. 이 항목에서는 서비스가 메시징 작업만으로 구성된 워크플로 서비스를 만드는 방법에 중점을 둡니다. 실제 서비스의 워크플로에는 다른 많은 작업이 포함되어 있습니다. 이 항목의 서비스에서는 문자열을 받아서 호출자에게 반환하는 Echo라는 하나의 작업을 구현합니다. 이 항목은 시리즈로 된 두 항목 중 첫 번째 항목입니다. 다음 항목에서는 [How To:는 서비스는 워크플로 응용 프로그램에서 액세스](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) 이 항목에서 만든 서비스를 호출할 수 있는 워크플로 응용 프로그램을 만드는 방법에 설명 합니다.  
  
### <a name="to-create-a-workflow-service-project"></a>워크플로 서비스 프로젝트를 만들려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]를 시작합니다.  
  
2.  클릭는 **파일** 메뉴 선택 **새로**, 차례로 **프로젝트** 표시 하는 **새 프로젝트 대화 상자**합니다. 선택 **워크플로** 설치 된 템플릿 목록에서 및 **WCF 워크플로 서비스 응용 프로그램** 프로젝트 형식 목록에서 합니다. 프로젝트 이름을 `MyWFService` 다음 그림에 나와 있는 것 처럼 기본 위치를 사용 합니다.  
  
     클릭는 **확인** 해제 단추는 **새 프로젝트 대화 상자**합니다.  
  
3.  프로젝트가 생성되면 다음 그림과 같이 Service1.xamlx 파일이 디자이너에서 열립니다.  
  
     ![디자이너에 표시 된 기본 워크플로](../../../../docs/framework/wcf/feature-details/media/defaultworkflowservice.JPG "DefaultWorkflowService")  
  
     레이블이 지정 된 활동을 마우스 오른쪽 단추로 클릭 **순차 서비스** 선택 **삭제**합니다.  
  
### <a name="to-implement-the-workflow-service"></a>워크플로 서비스를 구현하려면  
  
1.  선택 된 **도구 상자** 탭 창을 계속 열어에 압정을 클릭 하 고 도구 상자를 표시 하려면 화면 왼쪽에 있습니다. 확장 된 **메시징** 다음 그림에 나와 있는 것 처럼 여 메시징 작업과 메시징 작업 템플릿을 표시 하려면 도구 상자의 섹션.  
  
     ![메시징 탭 된 도구 상자 확장](../../../../docs/framework/wcf/feature-details/media/wfdesignertoolbox.JPG "WFDesignerToolbox")  
  
2.  끌어서 놓기는 **ReceiveAndSendReply** 템플릿을 워크플로 디자이너로 합니다. 그렇기 때문에 <!--zz <xref:System.ServiceModel.Activities.Sequence>--> `System.ServiceModel.Activities.Sequence` 활동과 **수신** 작업과 그 뒤는 <xref:System.ServiceModel.Activities.SendReply> 다음 그림과 같이 작업 합니다.  
  
     ![디자이너의 ReceiveAndSendReply 템플릿](../../../../docs/framework/wcf/feature-details/media/receiveandsendreply.JPG "ReceiveAndSendReply")  
  
     <xref:System.ServiceModel.Activities.SendReply> 작업의 <xref:System.ServiceModel.Activities.SendReply.Request%2A> 속성이 `Receive` 작업이 회신하는 <xref:System.ServiceModel.Activities.Receive> 작업의 이름인 <xref:System.ServiceModel.Activities.SendReply>로 설정됩니다.  
  
3.  에 <xref:System.ServiceModel.Activities.Receive> 활동 유형 `Echo` 이라는 입력란에 **OperationName**합니다. 그러면 서비스가 구현하는 작업의 이름이 정의됩니다.  
  
     ![작업 이름 지정](../../../../docs/framework/wcf/feature-details/media/defineoperation.JPG "DefineOperation")  
  
4.  와 <xref:System.ServiceModel.Activities.Receive> 활동을 선택한 경우 속성 창을 열고 클릭 하 여 열려 있지 않으면는 **보기** 메뉴에서 **속성 창**합니다. 에 **속성 창** 나타날 때까지 아래로 스크롤하여 **CanCreateInstance** 다음 그림에 나와 있는 것 처럼이 확인란을 클릭 합니다. 이렇게 설정하면 메시지를 받을 때 필요한 경우 워크플로 서비스 호스트가 서비스의 새 인스턴스를 만들 수 있습니다.  
  
     ![CanCreateInstance 속성](../../../../docs/framework/wcf/feature-details/media/cancreateinstance.JPG "CanCreateInstance")  
  
5.  선택은 <!--zz <xref:System.ServiceModel.Activities.Sequence>--> `System.ServiceModel.Activities.Sequence` 활동과 클릭은 **변수** 디자이너의 왼쪽된 아래 모서리에서 단추입니다. 그러면 변수 편집기가 표시됩니다. 클릭는 **변수 만들기** 링크 작업에 전송 하 여 문자열을 저장할 변수를 추가 합니다. 변수 이름을 `msg` 설정 하 고 해당 **변수** 다음 그림에 나와 있는 것 처럼 문자열을 입력 합니다.  
  
     ![변수 추가](../../../../docs/framework/wcf/feature-details/media/addvariable.JPG "AddVariable")  
  
     클릭는 **변수** 변수 편집기를 다시 단추입니다.  
  
6.  클릭는 **정의...** 연결에 **콘텐츠** 텍스트 상자에 <xref:System.ServiceModel.Activities.Receive> 표시 하는 활동의 **콘텐츠 정의** 대화입니다. 선택 된 **매개 변수** 라디오 단추를 클릭는 **새 매개 변수를 추가** 링크를 입력 `inMsg` 에 **이름** 텍스트 상자 **문자열**에 **형식** 드롭 다운 목록 상자 및 형식 `msg` 에 **에 할당할** 다음 그림에 나와 있는 것 처럼 텍스트 상자입니다.  
  
     ![매개 변수 콘텐츠 추가](../../../../docs/framework/wcf/feature-details/media/parameterscontent.jpg "ParametersContent")  
  
     그러면 받기 작업이 문자열 매개 변수를 받고 데이터가 `msg` 변수에 바인딩되도록 지정됩니다. 클릭 **확인** 를 닫으려면는 **콘텐츠 정의** 대화 상자.  
  
7.  클릭는 **정의...**  연결에 **콘텐츠** 상자에 <xref:System.ServiceModel.Activities.SendReply> 표시 하는 활동의 **콘텐츠 정의** 대화입니다. 선택은 **매개 변수** 라디오 단추를 클릭는 **새 매개 변수를 추가** 링크를 입력 `outMsg` 에 **이름** textbox, **문자열**에 **형식** 드롭다운 목록 상자 및 `msg` 에 **값** 다음 그림에 나와 있는 것 처럼 텍스트 상자입니다.  
  
     ![매개 변수 콘텐츠 추가](../../../../docs/framework/wcf/feature-details/media/parameterscontent2.jpg "ParametersContent2")  
  
     그러면 <xref:System.ServiceModel.Activities.SendReply> 작업이 메시지 또는 메시지 계약 형식을 보내고 데이터가 `msg` 변수에 바인딩되도록 지정됩니다. 이 작업이 <xref:System.ServiceModel.Activities.SendReply> 작업이므로 이는 이 작업이 클라이언트에 다시 보내는 메시지를 채우는 데 `msg`의 데이터가 사용됨을 의미합니다. 클릭 **확인** 를 닫으려면는 **콘텐츠 정의** 대화 상자.  
  
8.  저장 하 고 클릭 하 여 솔루션을 빌드합니다는 **빌드** 메뉴에서 **솔루션 빌드**합니다.  
  
## <a name="configure-the-workflow-service-project"></a>워크플로 서비스 프로젝트 구성  
 워크플로 서비스가 완료되었으므로 이 단원에서는 워크플로 서비스 솔루션을 손쉽게 호스팅하고 실행할 수 있도록 구성하는 방법에 대해 설명합니다. 이 솔루션은 ASP.NET Development Server를 사용하여 서비스를 호스팅합니다.  
  
#### <a name="to-set-project-start-up-options"></a>프로젝트 시작 옵션을 설정하려면  
  
1.  에 **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **MyWFService** 선택 **속성** 표시 하는 **프로젝트 속성** 대화 상자.  
  
2.  선택 된 **웹** 탭을 선택한 **특정 페이지** 아래 **시작 작업** 유형과 `Service1.xamlx` 다음 그림에 나와 있는 것 처럼 텍스트 상자에 합니다.  
  
     ![프로젝트 속성 대화 상자](../../../../docs/framework/wcf/feature-details/media/projectpropertiesdlg.JPG "ProjectPropertiesDlg")  
  
     그러면 ASP.NET Development Server에서 Service1.xamlx에 정의된 서비스가 호스팅됩니다.  
  
3.  Ctrl+F5를 눌러 서비스를 시작합니다. 그러면 다음 그림과 같이 바탕 화면의 오른쪽 아래에 ASP.NET Development Server 아이콘이 표시됩니다.  
  
     ![ASP.NET Developer Server 아이콘](../../../../docs/framework/wcf/feature-details/media/aspnetdevservericon.JPG "ASPNETDEVServerIcon")  
  
     또한 Internet Explorer에 서비스에 대한 WCF 서비스 도움말 페이지가 표시됩니다.  
  
     ![WCF 도움말 페이지](../../../../docs/framework/wcf/feature-details/media/wcfhelppate.JPG "WCFHelpPate")  
  
4.  계속 진행 하는 [How To:는 서비스는 워크플로 응용 프로그램에서 액세스](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) 이 서비스를 호출 하는 워크플로 클라이언트를 만드는 항목입니다.  
  
## <a name="see-also"></a>참고 항목  
 [워크플로 서비스](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [워크플로 서비스 호스팅 개요](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)  
 [메시징 작업](../../../../docs/framework/wcf/feature-details/messaging-activities.md)
