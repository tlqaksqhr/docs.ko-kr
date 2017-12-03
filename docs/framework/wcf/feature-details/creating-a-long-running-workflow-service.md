---
title: "장기 실행 워크플로 서비스 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c39bd04-5b8a-4562-a343-2c63c2821345
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 65aa61ec53c00ed69d55d36fb023dc92c77e1f13
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="creating-a-long-running-workflow-service"></a>장기 실행 워크플로 서비스 만들기
이 항목에서는 장기 실행 워크플로 서비스를 만드는 방법에 대해 설명합니다. 장기 실행 워크플로 서비스는 장기간 실행될 수 있습니다. 특정 지점에서 워크플로는 추가 정보를 기다리며 유휴 상태가 될 수 있습니다. 이 경우 워크플로는 SQL 데이터베이스에 유지되고 메모리에서 제거됩니다. 추가 정보를 사용할 수 있으면 워크플로 인스턴스가 다시 메모리에 로드되어 계속 실행됩니다.  이 시나리오에서는 매우 간단한 주문 시스템을 구현합니다.  클라이언트가 워크플로 서비스에 초기 메시지를 보내 주문을 시작하고, 워크플로 서비스는 주문 ID를 클라이언트에 반환합니다. 이 시점에서 워크플로 서비스가 클라이언트에서 다른 메시지를 기다리며 유휴 상태가 되고 SQL Server 데이터베이스에 유지됩니다.  클라이언트가 품목을 주문하기 위해 다음 메시지를 보내면 워크플로 서비스는 메모리에 다시 로드되고 주문 처리를 마칩니다. 코드 샘플에서 워크플로 서비스는 품목이 주문에 추가되었음을 나타내는 문자열을 반환합니다. 코드 샘플은 이 기술의 실제 응용 프로그램이라기보다는 장기 실행 워크플로 서비스를 보여 주는 간단한 샘플입니다. 이 항목에서는 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 프로젝트 및 솔루션을 만드는 방법을 알고 있다고 가정합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 사용하려면 다음 소프트웨어를 설치해야 합니다.  
  
1.  Microsoft SQL Server 2008  
  
2.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]  
  
3.  Microsoft [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]  
  
4.  WCF 및 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에 익숙하고 프로젝트/솔루션을 만드는 방법을 알고 있습니다.  
  
### <a name="to-setup-the-sql-database"></a>SQL 데이터베이스를 설정하려면  
  
1.  워크플로 서비스 인스턴스가 유지되려면 Microsoft SQL Server가 설치되어 있어야 하고 유지된 워크플로 인스턴스를 저장하도록 데이터베이스를 구성해야 합니다. 클릭 하 여 Microsoft SQL Management Studio를 실행 된 **시작** 단추를 선택 하면 **모든 프로그램**, **Microsoft SQL Server 2008**, 및 **Microsoft SQL Management Studio**합니다.  
  
2.  클릭는 **연결** SQL Server 인스턴스에 로그온 하는 단추  
  
3.  마우스 오른쪽 단추로 클릭 **데이터베이스** 트리 뷰 및 선택 **새 데이터베이스...** 라는 새 데이터베이스를 만들려면 `SQLPersistenceStore`합니다.  
  
4.  SQLPersistenceStore 데이터베이스의 C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en 디렉터리에 있는 SqlWorkflowInstanceStoreSchema.sql 스크립트 파일을 실행하여 필요한 데이터베이스 스키마를 설정합니다.  
  
5.  SQLPersistenceStore 데이터베이스의 C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en 디렉터리에 있는 SqlWorkflowInstanceStoreLogic.sql 스크립트 파일을 실행하여 필요한 데이터베이스 논리를 설정합니다.  
  
### <a name="to-create-the-web-hosted-workflow-service"></a>웹 호스팅 워크플로 서비스를 만들려면  
  
1.  비어 있는 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 솔루션을 만들고 `OrderProcessing`으로 이름을 지정합니다.  
  
2.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]라는 새 `OrderService` 워크플로 서비스 응용 프로그램 프로젝트를 솔루션에 추가합니다.  
  
3.  프로젝트 속성 대화 상자에서 선택 된 **웹** 탭 합니다.  
  
    1.  아래 **시작 작업** 선택 **특정 페이지** 지정 `Service1.xamlx`합니다.  
  
         ![워크플로 서비스 프로젝트 웹 속성](../../../../docs/framework/wcf/feature-details/media/startaction.png "StartAction")  
  
    2.  아래 **서버** 선택 **로컬 IIS 웹 서버**합니다.  
  
         ![로컬 웹 서버 설정](../../../../docs/framework/wcf/feature-details/media/uselocalwebserver.png "UseLocalWebServer")  
  
        > [!WARNING]
        >  이 설정을 지정하려면 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 관리자 모드로 실행해야 합니다.  
  
         이러한 두 단계에서는 IIS에서 호스팅하도록 워크플로 서비스 프로젝트를 구성합니다.  
  
4.  열고 `Service1.xamlx` 아직 열려 있고 기존 삭제 되지 경우 **ReceiveRequest** 및 **SendResponse** 활동입니다.  
  
5.  선택 된 **순차 서비스** 활동과 클릭은 **변수** 에 연결 하 고 다음 그림에 표시 된 변수를 추가 합니다. 이렇게 하면 워크플로 서비스에서 나중에 사용할 일부 변수가 추가됩니다.  
  
    > [!NOTE]
    >  CorrelationHandle이 변수 형식 드롭다운에 없는 경우 선택 **형식 찾아보기** 드롭다운 목록에서 합니다. 에 CorrelationHandle을 입력에서 **유형 이름** 상자 목록 상자에서 CorrelationHandle을 선택 하 고 클릭 **확인**합니다.  
  
     ![변수 추가](../../../../docs/framework/wcf/feature-details/media/addvariables.gif "AddVariables")  
  
6.  끌어서 놓기는 **ReceiveAndSendReply** 활동 템플릿을로 **순차 서비스** 활동입니다. 이 활동 집합은 클라이언트에서 메시지를 받고 회신을 보냅니다.  
  
    1.  선택 된 **수신** 활동과 다음 그림에 강조 표시 된 속성 집합입니다.  
  
         ![Receive 활동 속성 설정](../../../../docs/framework/wcf/feature-details/media/setreceiveproperties.png "SetReceiveProperties")  
  
         DisplayName 속성은 디자이너에서 표시되는 Receive 활동의 이름을 설정합니다. ServiceContractName 및 OperationName 속성은 Receive 활동으로 구현되는 서비스 계약 및 작업의 이름을 지정합니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]서비스 계약 워크플로에서 사용 되는 방법을 참조 하십시오 [워크플로에서 계약 사용 하 여](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)합니다.  
  
    2.  클릭는 **정의...**  연결에 **ReceiveStartOrder** 작업 하 고 다음 그림에 나와 있는 속성을 설정 합니다.  다음에 유의 **매개 변수** 라디오 단추를 선택 하면 매개 변수 이름 `p_customerName` 에 바인딩된는 `customerName` 변수입니다. 이렇게 하면 구성 된 **수신** 일부 데이터를 받아 해당 데이터를 로컬 변수에 바인딩하는 작업입니다.  
  
         ![Receive 활동에서 수신 하는 데이터 설정](../../../../docs/framework/wcf/feature-details/media/setreceivecontent.png "SetReceiveContent")  
  
    3.  선택 된 **SendReplyToReceive** 활동 및 강조 표시 된 다음 그림에 표시 된 속성을 설정 합니다.  
  
         ![SendReply 활동의 속성을 설정](../../../../docs/framework/wcf/feature-details/media/setreplyproperties.png "SetReplyProperties")  
  
    4.  클릭는 **정의...**  연결에 **SendReplyToStartOrder** 작업 하 고 다음 그림에 나와 있는 속성을 설정 합니다. 다음에 유의 **매개 변수** 라디오 단추가 선택 되 고, 매개 변수 이름이 `p_orderId` 바인딩되는 `orderId` 변수입니다. 이 설정은 SendReplyToStartOrder 활동이 문자열 형식의 값을 호출자에게 반환하도록 지정합니다.  
  
         ![SendReply 활동 콘텐츠 데이터 구성](../../../../docs/framework/wcf/feature-details/media/setreplycontent.png "SetReplyContent")  
  
    5.  Assign 활동을 중간에 끌어서는 **수신** 및 **SendReply** 활동 다음 그림에 나와 있는 것 처럼 속성을 설정 합니다.  
  
         ![Assign 활동 추가](../../../../docs/framework/wcf/feature-details/media/addassign.png "AddAssign")  
  
         이렇게 하면 새 주문 ID가 만들어지고 orderId 변수에 값이 배치됩니다.  
  
    6.  선택 된 **ReplyToStartOrder** 활동입니다. 속성 창에 대 한 줄임표 단추를 클릭 **CorrelationInitializers**합니다. 선택 된 **이니셜라이저 추가** 링크를 입력 `orderIdHandle` 고 이니셜라이저 텍스트 상자에서 상관 관계 형식의 쿼리 상관 관계 이니셜라이저를 선택 하 고 XPATH 쿼리 드롭다운 상자에서 p_orderId를 선택 합니다. 이러한 설정이 다음 그림에 나와 있습니다. **확인**을 클릭합니다.  클라이언트와 이 워크플로 서비스 인스턴스 간에 상관 관계가 초기화됩니다. 이 주문 ID가 포함된 메시지가 수신되면 이 워크플로 서비스 인스턴스로 라우팅됩니다.  
  
         ![상관 관계 이니셜라이저 추가](../../../../docs/framework/wcf/feature-details/media/addcorrelationinitializers.png "AddCorrelationInitializers")  
  
7.  끌어서 놓기 다른 **ReceiveAndSendReply** 활동을 워크플로의 끝 (외부의 **시퀀스** 첫 번째 포함 된 **수신** 및  **SendReply** 활동). 이 활동은 클라이언트에서 보낸 두 번째 메시지를 받고 응답합니다.  
  
    1.  선택 된 **시퀀스** 새로 추가 된 포함 된 **수신** 및 **SendReply** 활동과 클릭은 **변수** 단추 합니다. 다음 그림에 강조 표시된 변수를 추가합니다.  
  
         ![새 변수 추가](../../../../docs/framework/wcf/feature-details/media/addorderitemidvariable.png "AddOrderItemIdVariable")  
  
    2.  선택의 **수신** 활동 하 고 다음 그림에 나와 있는 속성을 설정 합니다.  
  
         ![Receive 활동 속성 설정](../../../../docs/framework/wcf/feature-details/media/setreceiveproperties2.png "SetReceiveProperties2")  
  
    3.  클릭는 **정의...**  링크를 **ReceiveAddItem** 활동 하 고 다음 그림에 표시 된 매개 변수 추가:이 주문 ID와 주문 되는 항목의 ID 두 개의 매개 변수를 수락 하도록 수신 작업을 구성 합니다.  
  
         ![두 번째 매개 변수를 받도록](../../../../docs/framework/wcf/feature-details/media/addreceive2parameters.png "AddReceive2Parameters")  
  
    4.  클릭는 **CorrelateOn** 줄임표 단추를 선택한 입력 `orderIdHandle`합니다. 아래 **XPath 쿼리**를 드롭다운 화살표를 클릭 하 고 `p_orderId`합니다. 이렇게 하면 두 번째 Receive 활동에 대한 상관 관계가 구성됩니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]상관 관계 참조 [상관 관계](../../../../docs/framework/wcf/feature-details/correlation.md)합니다.  
  
         ![CorrelatesOn 속성 설정](../../../../docs/framework/wcf/feature-details/media/correlateson.png "CorrelatesOn")  
  
    5.  끌어서 놓기는 **경우** 작업 바로 뒤의 **ReceiveAddItem** 활동입니다. 이 활동은 if 문처럼 작동합니다.  
  
        1.  설정의 **조건** 속성을`itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`  
  
        2.  끌어서 놓기는 **할당** 활동을는 **다음** 섹션과에 다른는 **Else** 의 속성을 설정 하는 섹션에서 **할당** 다음 그림과 같이 작업 합니다.  
  
             ![서비스 호출의 결과 할당](../../../../docs/framework/wcf/feature-details/media/resultassign.png "ResultAssign")  
  
             조건이 `true` 는 **다음** 섹션 실행 됩니다. 조건이 `false` 는 **Else** 섹션이 실행 됩니다.  
  
        3.  선택 된 **SendReplyToReceive** 활동 집합과 **DisplayName** 다음 그림에 표시 된 속성입니다.  
  
             ![SendReply 활동 속성 설정](../../../../docs/framework/wcf/feature-details/media/setreply2properties.png "SetReply2Properties")  
  
        4.  클릭는 **정의...**  연결에 **SetReplyToAddItem** 활동 다음 그림에 나와 있는 대로 구성 합니다. 이렇게 하면 구성는 **SendReplyToAddItem** 활동에서 값을 반환 하는 `orderResult` 변수입니다.  
  
             ![SendReply 활동에 대 한 데이터 바인딩 설정](../../../../docs/framework/wcf/feature-details/media/replytoadditemcontent.gif "ReplyToAddItemContent")  
  
8.  Web.config 파일을 열고 다음 요소에 추가 \<동작 > 섹션에 워크플로 지 속성을 사용 합니다.  
  
    ```xml  
    <sqlWorkflowInstanceStore connectionString="Data Source=your-machine\SQLExpress;Initial Catalog=SQLPersistenceStore;Integrated Security=True;Asynchronous Processing=True" instanceEncodingOption="None" instanceCompletionAction="DeleteAll" instanceLockedExceptionAction="BasicRetry" hostLockRenewalPeriod="00:00:30" runnableInstancesDetectionPeriod="00:00:02" />  
              <workflowIdle timeToUnload="0"/>  
    ```  
  
    > [!WARNING]
    >  이전 코드 조각의 호스트 및 SQL Server 인스턴스 이름을 바꿔야 합니다.  
  
9. 솔루션을 빌드합니다.  
  
### <a name="to-create-a-client-application-to-call-the-workflow-service"></a>클라이언트 응용 프로그램을 만들어 워크플로 서비스를 호출하려면  
  
1.  솔루션에 `OrderClient`라는 새 콘솔 응용 프로그램 프로젝트를 추가합니다.  
  
2.  다음 어셈블리에 대한 참조를 `OrderClient` 프로젝트에 추가합니다.  
  
    1.  System.ServiceModel.dll  
  
    2.  System.ServiceModel.Activities.dll  
  
3.  서비스 참조를 워크플로 서비스에 추가하고 `OrderService`를 네임스페이스로 지정합니다.  
  
4.  클라이언트 프로젝트의 `Main()` 메서드에서 다음 코드를 추가합니다.  
  
    ```  
    static void Main(string[] args)  
    {  
       // Send initial message to start the workflow service  
       Console.WriteLine("Sending start message");  
       StartOrderClient startProxy = new StartOrderClient();  
       string orderId = startProxy.StartOrder("Kim Abercrombie");  
  
       // The workflow service is now waiting for the second message to be sent  
       Console.WriteLine("Workflow service is idle...");  
       Console.WriteLine("Press [ENTER] to send an add item message to reactivate the workflow service...");  
       Console.ReadLine();  
  
       // Send the second message  
       Console.WriteLine("Sending add item message");  
       AddItemClient addProxy = new AddItemClient();  
       AddItem item = new AddItem();  
       item.p_itemId = "Zune HD";  
       item.p_orderId = orderId;  
  
       string orderResult = addProxy.AddItem(item);  
       Console.WriteLine("Service returned: " + orderResult);  
    }  
    ```  
  
5.  솔루션을 빌드하고 `OrderClient` 응용 프로그램을 실행합니다. 클라이언트에서 다음 텍스트가 표시됩니다.  
  
    ```Output  
    Sending start messageWorkflow service is idle...Press [ENTER] to send an add item message to reactivate the workflow service...  
    ```  
  
6.  워크플로 서비스가 유지 되었는지 있는지를 확인 하려면 SQL Server Management Studio를 시작으로 이동 하 여는 **시작** 메뉴 선택 **모든 프로그램**, **Microsoft SQL Server 2008**, **SQL Server Management Studio**합니다.  
  
    1.  왼쪽 창에서 확장을 **데이터베이스**, **SQLPersistenceStore**, **뷰** 마우스 오른쪽 단추로 클릭 하 고 **System.Activities.DurableInstancing.Instances**  선택 **상위 1000 개 행 선택**합니다. 에 **결과** 창 나열 된 인스턴스를 하나 이상 참조를 확인 합니다. 실행하는 동안 예외가 발생한 경우 이전 실행의 다른 인스턴스가 있을 수 있습니다. 마우스 오른쪽 단추로 클릭 하 여 기존 행을 삭제할 수 **System.Activities.DurableInstancing.Instances** 선택 하 고 **편집 상위 200 개 행**를 누르면는 **Execute** 단추를 결과 창에서 모든 행을 선택 하 고 선택 하면 **삭제**합니다.  데이터베이스에 표시되는 인스턴스가 응용 프로그램에서 만든 인스턴스인지 확인하려면 클라이언트를 실행하기 전에 인스턴스 뷰가 비어 있는지 확인합니다. 클라이언트가 실행되고 있으면 쿼리(상위 1000개의 행 선택)를 다시 실행하고 새 인스턴스가 추가되었는지 확인합니다.  
  
7.  Enter 키를 눌러 워크플로 서비스에 품목 추가 메시지를 보냅니다. 클라이언트에서 다음 텍스트가 표시됩니다.  
  
    ```Output  
    Sending add item messageService returned: Item added to orderPress any key to continue . . .  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [워크플로 서비스](../../../../docs/framework/wcf/feature-details/workflow-services.md)
