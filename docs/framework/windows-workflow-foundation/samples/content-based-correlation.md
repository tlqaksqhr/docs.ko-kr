---
title: "내용 기반 상관 관계"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8638b5d6-1d59-456d-8acd-179a5b39b260
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0490dcc854a6686c69ebc480df42e6086d1fdc52
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="content-based-correlation"></a>내용 기반 상관 관계
이 샘플에서는 여러 내용 기반 상관 관계와 내용 기반 상관 관계에 메시징 활동(<xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply>)을 사용하는 방법을 보여 줍니다. 이 시나리오에서는 먼저 구매 주문 ID를 기반으로 상관 관계를 초기화한 다음, 나중에 고객 ID를 기반으로 다른 상관 관계를 만듭니다. 여기에서는 <xref:System.ServiceModel.Activities.Receive> 활동이 기존 상관 관계를 따르고 들어오는 동일한 메시지를 기반으로 새 상관 관계를 초기화하는 방법을 보여 줍니다.  
  
## <a name="demonstrates"></a>세부 항목  
 메시징 활동 및 내용 기반 상관 관계  
  
## <a name="discussion"></a>토론  
 이 샘플에서는 여러 내용 기반 상관 관계를 사용하는 방법을 보여 줍니다.  이 시나리오에서는 먼저 구매 주문 ID를 기반으로 상관 관계를 초기화한 다음, 나중에 고객 ID를 기반으로 다른 상관 관계를 만듭니다.  상관 관계는 기존 상관 관계(PurchaseOrderId)를 따르고 들어오는 동일한 메시지를 기반으로 새 상관 관계(CustomerId)를 초기화하는 <xref:System.ServiceModel.Activities.Receive> 활동을 사용하여 연계됩니다.  이를 수행하기 위해 <xref:System.ServiceModel.Activities.Receive> 활동은 <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A>, <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> 및 <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> 속성을 사용합니다.  
  
## <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  열기 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 마우스 오른쪽 단추로 클릭 하 여 승격 된 권한으로는 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 아이콘을 선택 하면 **관리자 권한으로 실행**합니다.  
  
2.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 CascadingCorrelation.sln 솔루션 파일을 엽니다.  
  
3.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
4.  F5 키를 눌러 서버를 실행합니다.  
  
5.  서버가 메시지를 수신할 준비가 되어 있으면 솔루션 탐색기에서 클라이언트 프로젝트를 마우스 오른쪽 단추로 클릭하고 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\ContentBasedCorrelation`  
  
## <a name="see-also"></a>참고 항목
