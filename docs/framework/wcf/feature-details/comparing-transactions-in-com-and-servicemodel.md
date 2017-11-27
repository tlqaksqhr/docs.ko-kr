---
title: "COM+ 및 ServiceModel의 트랜잭션 비교"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 712f8a7a153d7255275ff7ebaa647d5a624f8ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>COM+ 및 ServiceModel의 트랜잭션 비교
이 항목에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 네임스페이스가 제공하는 <xref:System.ServiceModel> 특성을 사용하여 트랜잭션 COM+ 서비스의 동작을 시뮬레이션하는 방법에 대해 설명합니다.  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>ServiceModel 특성을 사용하여 COM+ 에뮬레이트  
 다음 표에서는 <xref:System.EnterpriseServices.TransactionOption> 트랜잭션을 만드는 데 사용되는 `EnterpriseServices` 열거 및 이러한 열거가 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 네임스페이스에서 제공하는 <xref:System.ServiceModel> 특성과 상호 관련된 방식을 비교합니다.  
  
|COM+ 특성|[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 특성|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|<xref:System.ServiceModel.TransactionFlowAttribute>이 <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>로 설정됩니다.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>가 `true`인 경우<br /><br /> 바인딩 요소의 `TransactionFlow` 특성이 `false`인 경우|  
|필수|<xref:System.ServiceModel.TransactionFlowAttribute>이 <xref:System.ServiceModel.TransactionFlowOption.Allowed>로 설정됩니다.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>가 `true`인 경우<br /><br /> 바인딩 요소의 `TransactionFlow` 특성이 `true`인 경우|  
|지원함|직접 대응하는 특성이 없습니다. 일반적으로 `Required`에 지정된 동작을 대신 사용해야 합니다.|  
|NotSupported|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>가 `false`인 경우<br /><br /> 바인딩 요소의 `TransactionFlow` 특성이 `false`인 경우|  
|Disabled|직접 대응하는 특성이 없습니다. 일반적으로 `NotSupported`에 지정된 동작을 대신 사용해야 합니다.|
