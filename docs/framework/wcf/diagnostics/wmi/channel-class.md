---
title: "Channel 클래스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 073f0a2a2731a08acd914a7dd85cb2b419d98128
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="channel-class"></a>Channel 클래스
채널  
  
## <a name="syntax"></a>구문  
  
```  
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a>메서드  
 Channel 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 Channel 클래스에는 다음 속성이 있습니다.  
  
### <a name="localaddress"></a>LocalAddress  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 채널에 대한 로컬 끝점입니다.  
  
### <a name="ref"></a>ref  
 데이터 형식: Endpoint  
  
 액세스 형식: 읽기 전용  
  
 채널이 연결되는 끝점에 대한 참조입니다.  
  
### <a name="remoteaddress"></a>RemoteAddress  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 채널과 연결된 원격 주소입니다.  
  
### <a name="sessionid"></a>SessionId  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 현재 세션 ID(있는 경우)입니다.  
  
### <a name="type"></a>형식  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 채널 형식입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.ChannelBase>
