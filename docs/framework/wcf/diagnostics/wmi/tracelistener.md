---
title: TraceListener
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2c0b595-a384-4eb3-b94d-1b3be7cc7a5c
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7c0bba558a7b0c727dd971960ab3f9120a6aaada
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="tracelistener"></a>TraceListener
TraceListener  
  
## <a name="syntax"></a>구문  
  
```  
class TraceListener  
{  
  string Name;  
  TraceListenerArgument TraceListenerArguments[];  
};  
```  
  
## <a name="methods"></a>메서드  
 TraceListener 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 TraceListener 클래스에는 다음 속성이 있습니다.  
  
### <a name="name"></a>이름  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 추적 수신기의 이름입니다.  
  
### <a name="tracelistenerarguments"></a>TraceListenerArguments  
 데이터 형식: TraceListenerArgument 배열  
  
 액세스 형식: 읽기 전용  
  
 추적 수신기의 인수입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|
