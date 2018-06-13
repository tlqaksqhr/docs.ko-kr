---
title: 1150 - CompensationState
ms.date: 03/30/2017
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
ms.openlocfilehash: 61613a27c4d4d8fb0b206246fef25ae87def47a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510683"
---
# <a name="1150---compensationstate"></a>1150 - CompensationState
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1150|  
|키워드|WFActivities|  
|수준|정보|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그|  
  
## <a name="description"></a>설명  
 CompensableActivity에서 상태 변경을 나타냅니다.  
  
## <a name="message"></a>메시지  
 CompensableActivity '%1'은(는) '%2' 상태입니다.  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|상태|xs:string|보정 상태입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
