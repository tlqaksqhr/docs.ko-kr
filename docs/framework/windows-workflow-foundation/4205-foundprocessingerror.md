---
title: 4205 - FoundProcessingError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2235a15-dd87-439e-8cb9-8b1b89a3dacf
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 376e90de00759a88c6c938f2125653161d8e5201
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="4205---foundprocessingerror"></a>4205 - FoundProcessingError
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|4205|  
|키워드|WFInstanceStore|  
|수준|오류|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그|  
  
## <a name="description"></a>설명  
 SQL 공급자 명령이 실패했음을 나타냅니다.  
  
## <a name="message"></a>메시지  
 명령 실패: %1  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|ExceptionMessage|xs:string|SQL 예외로부터의 메시지입니다.|  
|예외|xs:string|예외에 대한 예외 정보|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
