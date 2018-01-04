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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: be200882b59af3604a88c33ad1b3a99687ded860
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="formatting-messages-in-workflow-services"></a>워크플로 서비스에서 메시지 서식 지정
이 샘플에서는 메시징 활동(WF 서비스)에서 여러 가지 사용자 형식을 사용하는 방법을 보여 줍니다. 샘플 서비스는 간단한 비용 승인 서비스이며 세 가지 작업을 노출합니다. `ApproveExpense`는 데이터 계약 형식을 사용하며 알려진 형식을 사용하는 방법을 보여줍니다. 작업은 비용 금액을 기준으로 `true` 또는 `false`를 반환합니다. `ApprovePO`XmlSerializer 형식을 사용 하 고 반환 `true` 또는 `false` 은 비용 금액에 따라 합니다.`ApprovedVendor` 메시지 계약 형식을 사용 하 고 반환 `true` 또는 `false` 승인 된 공급 업체 목록에 있는 경우 또는 요청 (재무 부서의 모든 공급 업체를 사용할 수 있음)는 재무 부서에서 온 경우.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에 프로젝트 솔루션을 로드하고 프로젝트를 빌드합니다.  
  
2.  먼저 [solution base directory]\FormatterService\bin\debug\에 생성된 서비스를 실행합니다.  
  
3.  그런 다음 [solution base directory]\FormatterClient\bin\debug에 생성된 클라이언트 응용 프로그램을 실행합니다.  
  
4.  클라이언트에서 서비스에 대한 세 가지 작업을 호출하고 결과를 출력합니다. 완료되면 Enter 키를 눌러 클라이언트와 서비스를 차례로 종료합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Formatter`