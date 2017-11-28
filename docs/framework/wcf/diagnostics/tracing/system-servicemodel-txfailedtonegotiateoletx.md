---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 61360eff4f2c403eea98bbc0a2eae36e516b3d7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a>System.ServiceModel.TxFailedToNegotiateOleTx
지정된 코디네이션 컨텍스트에 대해 OleTransactions 프로토콜 협상을 완료하지 못했습니다.  
  
## <a name="description"></a>설명  
 OleTx 정보가 포함된 들어오는 트랜잭션이 첨부된 OleTx 정보를 사용할 수 없고 대신 WS-AT를 사용하는 경우 추적됩니다.  
  
## <a name="troubleshooting"></a>문제 해결  
 시스템 간의 MSDTC RPC 통신 관련 잠재적 문제를 나타냅니다. 이렇게 많은 추적이 로그에 나타날 경우 성능이 많이 떨어질 수 있습니다.  OleTx를 사용하지 않는 경우 WS-AT 레지스트리 구성에서 `OleTxUpgradeEnabled`를 0으로 설정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [추적을 사용 하 여 응용 프로그램 문제를 해결 하려면](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)
