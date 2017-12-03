---
title: TransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c2605e1a1f88434a9052059ac3ebdce429d6d6c8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="transportbindingelement"></a>TransportBindingElement
TransportBindingElement  
  
## <a name="syntax"></a>구문  
  
```  
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a>메서드  
 TransportBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 TransportBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="manualaddressing"></a>ManualAddressing  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 사용자가 메시지 주소 지정을 제어하는지 여부를 지정하는 부울 값입니다.  
  
### <a name="maxbufferpoolsize"></a>MaxBufferPoolSize  
 데이터 형식: sint64  
  
 액세스 형식: 읽기 전용  
  
 바인딩에 대한 최대 버퍼 풀 크기입니다.  
  
### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize  
 데이터 형식: sint64  
  
 액세스 형식: 읽기 전용  
  
 이 바인딩에서 처리하는 메시지의 최대 크기입니다.  
  
### <a name="scheme"></a>Scheme  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 전송을 위한 URI 스키마입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.TransportBindingElement>
