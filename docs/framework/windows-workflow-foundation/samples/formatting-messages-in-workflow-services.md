---
title: "워크플로 서비스에서 메시지 서식 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d15d44b-20f8-4cb7-bd4f-598c32781ebc
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d2367f4fe4ebe576eb9a5e2f707eb043e5ee7ccb
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="formatting-messages-in-workflow-services"></a><span data-ttu-id="72da8-102">워크플로 서비스에서 메시지 서식 지정</span><span class="sxs-lookup"><span data-stu-id="72da8-102">Formatting messages in Workflow Services</span></span>
<span data-ttu-id="72da8-103">이 샘플에서는 메시징 활동(WF 서비스)에서 여러 가지 사용자 형식을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="72da8-103">This sample shows how different user types can be used in messaging activities (WF services).</span></span> <span data-ttu-id="72da8-104">샘플 서비스는 간단한 비용 승인 서비스이며 세 가지 작업을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="72da8-104">The sample service is a simple expense approval service and exposes three operations.</span></span> <span data-ttu-id="72da8-105">`ApproveExpense`는 데이터 계약 형식을 사용하며 알려진 형식을 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="72da8-105">`ApproveExpense` takes a data contract type and shows how to use known types.</span></span> <span data-ttu-id="72da8-106">작업은 비용 금액을 기준으로 `true` 또는 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="72da8-106">The operation returns `true` or `false` based on the expense amount.</span></span> <span data-ttu-id="72da8-107">`ApprovePO`XmlSerializer 형식을 사용 하 고 반환 `true` 또는 `false` 은 비용 금액에 따라 합니다.`ApprovedVendor`</span><span class="sxs-lookup"><span data-stu-id="72da8-107">`ApprovePO` takes an XmlSerializer type and returns `true` or `false` based on the expense amount.`ApprovedVendor`</span></span> <span data-ttu-id="72da8-108">메시지 계약 형식을 사용 하 고 반환 `true` 또는 `false` 승인 된 공급 업체 목록에 있는 경우 또는 요청 (재무 부서의 모든 공급 업체를 사용할 수 있음)는 재무 부서에서 온 경우.</span><span class="sxs-lookup"><span data-stu-id="72da8-108">takes a message contract type and returns `true` or `false` if the vendor is in the list of approved vendors or if the request came from the finance department (the finance department can use any vendor).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="72da8-109">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="72da8-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="72da8-110">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에 프로젝트 솔루션을 로드하고 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="72da8-110">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="72da8-111">먼저 [solution base directory]\FormatterService\bin\debug\에 생성된 서비스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="72da8-111">First run the service, generated in [solution base directory]\FormatterService\bin\debug\\</span></span>  
  
3.  <span data-ttu-id="72da8-112">그런 다음 [solution base directory]\FormatterClient\bin\debug에 생성된 클라이언트 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="72da8-112">Second, run the Client application generated in [solution base directory]\FormatterClient\bin\debug.</span></span>  
  
4.  <span data-ttu-id="72da8-113">클라이언트에서 서비스에 대한 세 가지 작업을 호출하고 결과를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="72da8-113">The client calls three operations on the service and prints the results.</span></span> <span data-ttu-id="72da8-114">완료되면 Enter 키를 눌러 클라이언트와 서비스를 차례로 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="72da8-114">When complete, press ENTER to exit the client and then the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="72da8-115">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72da8-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="72da8-116">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="72da8-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="72da8-117">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="72da8-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="72da8-118">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72da8-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Formatter`