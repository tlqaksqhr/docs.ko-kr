---
title: '끝점: Calls Failed Per Second'
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: c0273fc90ad5702663862612f52f03c42f410b8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473496"
---
# <a name="endpoint-calls-failed-per-second"></a>끝점: Calls Failed Per Second
카운터 이름: Calls Failed Per Second  
  
## <a name="description"></a>설명  
 처리되지 않은 예외가 있고 초당 이 끝점에서 받은 호출 수입니다.  
  
 이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 이 카운터는 이 끝점에서 처리되지 않은 예외가 발생할 때마다 증가됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [계약 및 서비스에서 오류 지정 및 처리](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
