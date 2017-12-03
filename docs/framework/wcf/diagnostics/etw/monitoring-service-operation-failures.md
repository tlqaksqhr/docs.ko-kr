---
title: "서비스 작업 오류 모니터링"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59472ba3-8ebf-4479-bd7b-f440d5e636cb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c6030b1ad1dc3953137d3b068be1bceb99975a5f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="monitoring-service-operation-failures"></a><span data-ttu-id="8e1ca-102">서비스 작업 오류 모니터링</span><span class="sxs-lookup"><span data-stu-id="8e1ca-102">Monitoring Service Operation Failures</span></span>
<span data-ttu-id="8e1ca-103">응용 프로그램에 분석 추적을 사용하도록 설정된 경우 이벤트 뷰어에서 서비스 오류를 쉽게 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-103">If analytic tracing is enabled for an application, service failures can easily be monitored in the event viewer.</span></span>  <span data-ttu-id="8e1ca-104">이 항목에서는 서비스 작업이 실패한 경우를 확인하는 방법과 오류가 발생한 원인을 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-104">This topic demonstrates how to determine when a service operation fails, and how to determine what caused the failure.</span></span>  
  
### <a name="determining-service-operation-failure-information"></a><span data-ttu-id="8e1ca-105">서비스 작업 실패 정보 확인</span><span class="sxs-lookup"><span data-stu-id="8e1ca-105">Determining service operation failure information</span></span>  
  
1.  <span data-ttu-id="8e1ca-106">클릭 하 여 이벤트 뷰어를 열고 **시작**, **실행**, 입력 및 `eventvwr.exe`합니다.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-106">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
2.  <span data-ttu-id="8e1ca-107">분석 추적을 활성화 하지 않은 확장 **Applications and Services Logs**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용 프로그램** .</span><span class="sxs-lookup"><span data-stu-id="8e1ca-107">If you haven’t enabled analytic tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="8e1ca-108">선택 **보기**, **분석 및 디버그 로그 표시**합니다.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-108">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="8e1ca-109">마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-109">Right-click **Analytic** and select **Enable Log**.</span></span> <span data-ttu-id="8e1ca-110">서비스 작업이 실패한 후 추적 내용을 볼 수 있도록 이벤트 뷰어를 열어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-110">Leave Event Viewer open so that traces can be viewed after the service operation fails.</span></span>  
  
3.  <span data-ttu-id="8e1ca-111">만든 샘플을 열고는 [초보자를 위한 자습서](../../../../../docs/framework/wcf/getting-started-tutorial.md) 에 [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] 실행 해야 하는 참고 [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] 관리자 권한으로 서비스를 만들 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-111">Next, open the sample created in the [Getting Started Tutorial](../../../../../docs/framework/wcf/getting-started-tutorial.md) in [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] Note that you must run [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] as an administrator so that the service can be created.</span></span> <span data-ttu-id="8e1ca-112">있는 경우는 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 열 수 있습니다 설치 되어 있는 샘플의 [시작](../../../../../docs/framework/wcf/samples/getting-started-sample.md), 자습서에서 만든 완료 된 프로젝트를 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-112">If you have the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] samples installed, you can open the [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), which contains the completed project created in the tutorial.</span></span>  
  
4.  <span data-ttu-id="8e1ca-113">Server 프로젝트의 Program.cs 파일에서 `Divide` 클래스의 `CalculatorService` 메서드 시작 부분에 다음 코드 줄을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-113">In the Program.cs file in the Server project, add the following line of code to the start of the `Divide` method in the `CalculatorService` class:</span></span>  
  
    ```  
    if (n2 == 0) throw new DivideByZeroException();  
    ```  
  
5.  <span data-ttu-id="8e1ca-114">Client 프로젝트의 Program.cs 파일에서 value2에 할당된 값을 0으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-114">In the Program.cs file in the Client project, change the value assigned to value2 to zero:</span></span>  
  
    ```  
    //Call the Divide service operation  
    value1 = 22.00D;  
    value2 = 0.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0}, {1}) = {2}", value1, value2, result);  
    ```  
  
6.  <span data-ttu-id="8e1ca-115">서버 응용 프로그램 키를 눌러 디버깅 하지 않고 실행 **Ctrl + f 5**합니다.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-115">Execute the server application without debugging by pressing **Ctrl+F5**.</span></span>  
  
7.  <span data-ttu-id="8e1ca-116">Visual Studio 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-116">Open a Visual Studio command prompt.</span></span>  <span data-ttu-id="8e1ca-117">클라이언트 디렉터리로 이동하고 명령줄에서 클라이언트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-117">Navigate to the client directory and execute the client from the command line.</span></span>  
  
8.  <span data-ttu-id="8e1ca-118">이벤트 뷰어에서 분석 로그를 사용하지 않도록 설정하고 새로 고친 다음 이벤트 ID를 기준으로 이벤트를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-118">In Event Viewer, disable and refresh the Analytic log and sort the events by Event ID.</span></span>  <span data-ttu-id="8e1ca-119">이벤트 ID를 사용 하 여 이벤트를 찾아보십시오 [219-ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), 서비스 오류를 설명 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-119">Look for an event with Event ID [219 - ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), which describes the service failure.</span></span>  
  
    ```Output  
    There was an unhandled exception of type 'System.DivideByZeroException' during message processing.  Full Exception ToString: System.DivideByZeroException: Attempted to divide by zero.  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="8e1ca-120">이벤트는 이벤트 뷰어로 전송될 때 버퍼링되므로 실패 이벤트가 바로 나타나지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e1ca-120">Events are buffered when being sent to the event viewer; the failure event may not appear right away.</span></span>
