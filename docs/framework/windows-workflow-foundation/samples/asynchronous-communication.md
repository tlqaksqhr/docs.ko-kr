---
title: Asynchronous Communication
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ea2d705a38ddae1689d212bbd50196920fe73fe
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="asynchronous-communication"></a>Asynchronous Communication
이 샘플에서는 기본적으로 서로 다른 두 [!INCLUDE[wf](../../../../includes/wf-md.md)] 서비스 간에 비동기 통신이 이루어지는 방식을 보여 줍니다.  
  
## <a name="demonstrates"></a>세부 항목  
 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 서비스 간의 비동기 통신  
  
## <a name="discussion"></a>토론  
 이 샘플에서는 .NET Framework에서 제공되는 메시징 활동을 통해 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 응용 프로그램 간의 통신이 비동기적으로 이루어지는 방식을 보여 줍니다.  
  
 이 샘플은 다음 세 개의 프로젝트로 구성되어 있습니다.  
  
 CreditCheckService  
 이 서비스는 특정 개인의 신용 점수나 승인할 품목의 가치를 받은 다음 해당 개인에게 신용을 부여할지 여부를 결정합니다.  
  
 RentalApprovalService  
 이 서비스는 신용 거래를 필요로 하는 개인으로부터 신청을 받습니다. 이 서비스는 `CreditCheckService`와 비동기적으로 통신하여 신용 거래 신청이 유효한지 여부를 결정합니다.  
  
 클라이언트  
 클라이언트는 `RentalApprovalService`와 동기적으로 통신하여 신용 거래가 승인되었는지 여부를 확인합니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  마우스 오른쪽 단추로 클릭는 **AsynchronousCommunication** 솔루션과 선택 **속성**합니다.  
  
2.  **공용 속성**선택, **시작 프로젝트**를 선택 하 고 **여러 개의 시작 프로젝트**합니다.  
  
3.  이동 **RentalApprovalService** 하려면 목록에서 첫 번째 위치 뒤 **CreditCheckService**옵니다 **클라이언트**합니다. 설정의 **시작** 세 프로젝트 모두에서 작업 합니다.  
  
4.  클릭 **확인**, 샘플을 실행 하려면 F5 키를 누릅니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
