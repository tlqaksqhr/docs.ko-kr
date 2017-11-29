---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a00a6a06fd5214f1f65bdb6369839d717078da77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a>Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
WS-AT 프로토콜 서비스가 Prepare 메시지에 응답하지 않은 영속 참가자로부터 Replay 메시지를 받았습니다. 따라서 트랜잭션이 중단되었습니다.  
  
## <a name="description"></a>설명  
 영속 참가자가 준비하는 동안 Reply 메시지를 받을 경우 추적됩니다. 이 상태에 대한 잘못된 메시지로 트랜잭션이 중단됩니다.  
  
## <a name="troubleshooting"></a>문제 해결  
 이 오류를 받는다면, Subordinate TransactionManager 등 영속 참가자가 오류를 복구했지만 트랜잭션 결과가 불확실함을 나타낼 수 있어 상태를 요청할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [추적을 사용 하 여 응용 프로그램 문제를 해결 하려면](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)
