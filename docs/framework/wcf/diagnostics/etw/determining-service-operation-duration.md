---
title: 서비스 작업 기간 확인
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: 8c86ccc09979071e0678be792f4937d526e23fa7
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="determining-service-operation-duration"></a><span data-ttu-id="0d3db-102">서비스 작업 기간 확인</span><span class="sxs-lookup"><span data-stu-id="0d3db-102">Determining service operation duration</span></span>
<span data-ttu-id="0d3db-103">Windows Communication Foundation (WCF) 응용 프로그램에서 분석 추적을 사용 하는 경우 서비스 작업에 대 한 실행 기간 동안 이벤트 로그를 검사 하 여 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d3db-103">If analytic tracing is enabled in a Windows Communication Foundation (WCF) application, the duration of execution for a service operation can easily be determined by examining the event log.</span></span>  <span data-ttu-id="0d3db-104">이 항목에서는 서비스 작업을 완료하는 데 소요되는 시간을 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d3db-104">This topic demonstrates how to determine the amount of time a service operation takes to complete.</span></span>  
  
### <a name="determining-service-operation-execution-duration"></a><span data-ttu-id="0d3db-105">서비스 작업 실행 기간 확인</span><span class="sxs-lookup"><span data-stu-id="0d3db-105">Determining service operation execution duration</span></span>  
  
1.  <span data-ttu-id="0d3db-106">클릭 하 여 이벤트 뷰어를 열고 **시작**, **실행**, 입력 및 `eventvwr.exe`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3db-106">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
2.  <span data-ttu-id="0d3db-107">분석 추적을 활성화 하지 않은 확장 **Applications and Services Logs**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용 프로그램** .</span><span class="sxs-lookup"><span data-stu-id="0d3db-107">If you haven’t enabled analytic tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="0d3db-108">선택 **보기**, **분석 및 디버그 로그 표시**합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3db-108">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="0d3db-109">마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3db-109">Right-click **Analytic** and select **Enable Log**.</span></span> <span data-ttu-id="0d3db-110">서비스 작업이 실행된 후 추적 내용을 볼 수 있도록 이벤트 뷰어를 열어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="0d3db-110">Leave Event Viewer open so that traces can be viewed after the service operation is run.</span></span>  
  
3.  <span data-ttu-id="0d3db-111">다음으로 서비스 프로젝트 및 해당 서비스와 상호 작용 하는 클라이언트 프로젝트가 포함 된 WCF 응용 프로그램을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0d3db-111">Next, open a WCF application that includes a service project and a client project that interacts with that service.</span></span>  <span data-ttu-id="0d3db-112">수행 하 여 이러한 응용 프로그램을 만들 수 있습니다는 [초보자를 위한 자습서](../../../../../docs/framework/wcf/getting-started-tutorial.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3db-112">You can create such an application by following the [Getting Started Tutorial](../../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  <span data-ttu-id="0d3db-113">WCF 샘플 설치 되어 있는 경우 열 수 있습니다는 [시작](../../../../../docs/framework/wcf/samples/getting-started-sample.md), 자습서에서 만든 완료 된 프로젝트를 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3db-113">If you have the WCF samples installed, you can open the [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), which contains the completed project created in the tutorial.</span></span>  
  
4.  <span data-ttu-id="0d3db-114">키를 눌러 서버 응용 프로그램을 실행 **F5**합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3db-114">Execute the server application by pressing **F5**.</span></span> <span data-ttu-id="0d3db-115">클라이언트 응용 프로그램을 마우스 오른쪽 단추로 클릭 하 여 실행는 **클라이언트** 프로젝트를 선택 하 고 **디버그**, **새 인스턴스 시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3db-115">Execute the client application by right-clicking on the **Client** project and selecting **Debug**, **Start New Instance**.</span></span>  
  
5.  <span data-ttu-id="0d3db-116">이벤트 뷰어에서 분석 로그를 새로 고친 다음 이벤트 ID를 기준으로 이벤트를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3db-116">In Event Viewer, refresh the Analytic log and sort the events by Event ID.</span></span>  <span data-ttu-id="0d3db-117">이벤트 이벤트 ID를 확인 [214-OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0d3db-117">Look for events with Event ID [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).</span></span>  <span data-ttu-id="0d3db-118">이 이벤트는 완료된 작업과 해당 작업의 기간을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d3db-118">These events will show which operations have completed, and what the duration of the operation was.</span></span>  <span data-ttu-id="0d3db-119">다음 이벤트는 Add 작업의 기간을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d3db-119">The following event shows the duration of an Add operation.</span></span>  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
