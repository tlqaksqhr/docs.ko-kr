---
title: MsmqTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 572a19723583a6bc717a71b3b46040148f29e1cd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="msmqtransportbindingelement"></a>MsmqTransportBindingElement
MsmqTransportBindingElement  
  
## <a name="syntax"></a>구문  
  
```  
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a>메서드  
 MsmqTransportBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 MsmqTransportBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="maxpoolsize"></a>MaxPoolSize  
 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 내부 MSMQ 메시지 개체가 포함된 풀의 최대 크기입니다.  
  
### <a name="queuetransferprotocol"></a>QueueTransferProtocol  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 이 바인딩에서 사용하는 대기 중인 통신 채널 전송을 나타내는 열거형 값입니다.  
  
### <a name="useactivedirectory"></a>UseActiveDirectory  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 Active Directory를 사용하여 큐 주소를 변환해야 하는지 여부를 나타내는 부울 값을 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
