---
title: 441- StopSignPostEvent
ms.date: 03/30/2017
ms.assetid: fc9850a5-0dc3-4b84-a09a-744301c7c18e
ms.openlocfilehash: 69430372a472b19caaa9f1de9c0f06886001353e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511298"
---
# <a name="441--stopsignpostevent1"></a>441- StopSignPostEvent
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|441|  
|키워드|문제 해결|  
|수준|정보|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석|  
  
## <a name="description"></a>설명  
 동작 추적에서 보내거나 받을 메시지가 동작 경계 넘기를 완료했음을 나타냅니다.  
  
## <a name="message"></a>메시지  
 동작 경계입니다.  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|Extended Data|`xs:string`|작업의 이름입니다.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
