---
title: "워크플로에서 계약 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ff40241bd48a4355738ca93ef2c80ceec55db11
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="using-contracts-in-workflow"></a>워크플로에서 계약 사용
서비스를 구현하는 경우 서비스를 설명하는 많은 계약과 서비스가 보내고 받는 데이터를 정의합니다. 이러한 데이터는 데이터 계약 및 메시지 계약 정의로 표현되기 때문에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 워크플로 서비스에서는 데이터 계약과 메시지 계약을 서비스 설명의 일부로 사용합니다. 서비스 자체에서는 서비스의 작업을 설명하기 위해 메타데이터(WSDL 형식)를 노출합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 서비스 계약과 작업 계약을 사용하여 서비스와 서비스가 지원하는 작업을 정의합니다. 그러나 워크플로 서비스에서는 이러한 계약이 비즈니스 프로세스 자체의 일부이기 때문에 계약 유추라고 하는 프로세스에 의해 메타데이터로 노출됩니다.  
  
## <a name="contract-inference"></a>계약 유추  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>를 사용하여 워크플로 서비스가 호스트되면 워크플로 정의가 검사되고 워크플로에 있는 메시징 작업 집합을 기반으로 계약이 생성됩니다. 특히 계약을 생성하는 데는 다음 작업과 속성이 사용됩니다.  
  
 <xref:System.ServiceModel.Activities.Receive> 작업  
  
-   <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
-   <xref:System.ServiceModel.Activities.Receive.OperationName%2A>
  
-   <xref:System.ServiceModel.Activities.Receive.Action%2A>   
 
 <xref:System.ServiceModel.Activities.SendReply> 작업  
  
-   <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 작업  
  
 계약 유추의 최종 결과는 WCF 서비스 및 작업 계약과 동일한 데이터 구조를 사용하는 서비스에 대한 설명입니다. 이 정보는 나중에 워크플로 서비스에 대한 WSDL을 노출하는 데 사용됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [워크플로 서비스](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [메시징 작업](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 [방법: 메시징 작업을 사용하여 워크플로 서비스 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 [방법: 기존 서비스 계약을 사용하는 워크플로 서비스 만들기](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
