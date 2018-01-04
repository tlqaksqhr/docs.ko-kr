---
title: "트랜잭션 예외"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d27ed51-7eda-477f-9eca-94fa129f3e07
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f13a39c251afd55dbb1f0d2dde4fc66fe38d30a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="transaction-exceptions"></a>트랜잭션 예외
이 항목에서는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 트랜잭션에 의해 생성된 모든 예외를 보여 줍니다.  
  
## <a name="exception-list"></a>예외 목록  
  
|리소스 코드|리소스 문자열|  
|-------------------|---------------------|  
|SFxCannotHaveDifferentTransactionProtocolsInOneBinding|메타데이터에서 가져오는 정책 정보는 각 작업의 TransactionProtocol에 여러 값을 지정하지만 각 끝점에는 하나의 TransactionProtocol만 지원됩니다.|  
|SFxTransactionAutoCompleteFalseAndInstanceContextMode|서비스의 InstanceContextMode가 PerSession이 아닐 경우 TransactionAutoComplete은 false일 수 없습니다. 지정된 계약 및 작업을 구현할 때 오류가 있습니다.|  
|SFxTransactionInvalidSetTransactionComplete|TransactionAutoComplete을 false로 설정하고 TransactionScopeRequired를 true로 설정하는 경우에만 작업에서 OperationContext.SetTransactionComplete을 호출할 수 있습니다. 잘못된 시나리오이므로 현재 트랜잭션이 종료되었습니다.|  
|TransactionFlowRequiredIssuedTokens|트랜잭션을 이동하려면 발급된 토큰의 이동도 지원되어야 합니다.|  
|TrustDriverVersionDoesNotSupportIssuedTokens|구성된 트러스트 버전이 발급된 토큰을 지원하지 않습니다. WSTrustFeb2005 이상을 사용하십시오.|
