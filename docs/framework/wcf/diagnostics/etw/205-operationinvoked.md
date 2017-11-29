---
title: 205 - OperationInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2b0a96f1e3ba72a226d9b1a871382a27db61c57e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="205---operationinvoked"></a>205 - OperationInvoked
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|205|  
|키워드가|문제 해결, ServiceModel|  
|수준|정보|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석|  
  
## <a name="description"></a>설명  
 이 이벤트는 서비스 모델의 기본 `OperationInvoker`가 메서드에 대한 호출을 시작하기 바로 전에 내보내집니다.  
  
## <a name="message"></a>메시지  
 OperationInvoker가 '%1' 메서드를 호출했습니다. 호출자 정보: '%2'.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|메서드 이름|`xs:string`|`OperationInvoker`의 호출을 받은 메서드의 CLR 이름입니다.|  
|호출자 정보|`xs:string`|'IPAddress:PortNumber' 형식으로 된 클라이언트의 IP 주소와 포트 번호입니다. 이 두 값은 작업 컨텍스트 내의 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' 메시지 속성에서 검색됩니다. 비 TCP 바인딩의 경우 이 값은 `null`입니다.|  
|HostReference|`xs:string`|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다. 해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'. 예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
