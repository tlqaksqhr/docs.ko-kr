---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: ad05a2b8552cc09d45e950e2c3336d86be918963
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33479133"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a>System.ServiceModel.Channels.MsmqMessageDropped
MSMQ에서 메시지를 삭제했습니다.  
  
## <a name="description"></a>설명  
 추적은 MSMQ 메시지가 삭제되었음을 나타냅니다. Windows Communication Foundation (WCF) (NetMsmqBinding 또는 MsmqIntegrationBinding과 함께 사용 됨)를 처리할 수 없는 경우에 MSMQ 메시지가 삭제 될 수 있습니다. 이러한 메시지를 포이즌 메시지라고 합니다.  
  
 포이즌 메시지는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Drop`으로 설정할 경우 삭제됩니다. 삭제된 메시지는 큐에서 제거되고 더 이상 복구될 수 없습니다.  
  
 참조 [포이즌 메시지 처리](http://go.microsoft.com/fwlink/?LinkID=99546) 경우 메시지가 포이즌이 되 고 적절히 처리 하도록 서비스를 구성 하는 방법에 대 한 자세한 내용은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [추적을 사용하여 응용 프로그램 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)  
 [포이즌 메시지 처리](http://go.microsoft.com/fwlink/?LinkID=99546)
