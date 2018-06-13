---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: 0a28eec659b48d5add4c53bc8c16972892e65099
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487908"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a>System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
메시지를 이동하거나 삭제할 수 없습니다.  
  
## <a name="description"></a>설명  
 이 추적은 MSMQ 메시지를 이동, 삭제 및 거부하는 동안 오류가 발생했음을 나타냅니다.  
  
 Windows Communication Foundation (WCF에서) (NetMsmqBinding 또는 MsmqIntegrationBinding과 함께 사용) 하는 경우 MSMQ 메시지를 사용 합니다. 이 추적은의 선택된 된 값은 관련이 `ReceiveErrorHandling` NetMsmqBinding 또는 MsmqIntegrationBinding의 속성입니다.  
  
 이 추적은 전체 시스템 오류를 의미하지는 않습니다. 그러나 메시지에서 선택한 포이즌 메시지를 처리하지 못했음을 나타냅니다. 참조 [포이즌 메시지 처리](http://go.microsoft.com/fwlink/?LinkID=99546) 경우 메시지가 포이즌이 되 고 적절히 처리 하도록 서비스를 구성 하는 방법에 대 한 자세한 내용은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [추적을 사용하여 응용 프로그램 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)
