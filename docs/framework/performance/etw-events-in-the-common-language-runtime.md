---
title: 공용 언어 런타임의 ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7855007c7566d3be0012bbff2cb124ee2681cb6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="etw-events-in-the-common-language-runtime"></a>공용 언어 런타임의 ETW 이벤트
CLR(공용 언어 런타임)은 다양한 디버깅 및 프로파일링 이벤트를 통해 ETW(Windows용 이벤트 추적) 진단 정보에 대한 유용한 이벤트 추적을 제공합니다. CLR ETW 이벤트는 Windows ETW 추적 시스템을 사용하여 공용 언어 런타임에서 제공되는 기존 프로파일링 및 디버깅 지원을 확장합니다.  
  
 ETW에 대한 자세한 내용은 MSDN의 [Improve Debugging and Performance Tuning with ETW](http://go.microsoft.com/fwlink/?LinkID=161142)(ETW를 사용한 디버깅 및 성능 조정 개선)를 참조하세요. Xperf에 대한 자세한 내용은 NTDebugging 블로그의 [Windows Performance Toolkit - Xperf](http://go.microsoft.com/fwlink/?LinkID=161144)(Windows 성능 도구 키트 - Xperf) 항목에서 찾을 수 있습니다.  
  
 이벤트 항목에 설명된 모든 이벤트를 지원하려면 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 이상이 필요합니다. Windows Vista 운영 체제가 최소 지원 클라이언트이고, Windows Server 2008이 최소 지원 서버입니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [.NET Framework 로깅 제어](../../../docs/framework/performance/controlling-logging.md)  
 ETW 이벤트를 캡처하고 보기 위한 도구와 명령을 설명합니다.  
  
 [CLR ETW 공급자](../../../docs/framework/performance/clr-etw-providers.md)  
 런타임 및 런다운 공급자와 ETW 데이터 수집에 이러한 공급자를 사용하는 방법을 설명합니다.  
  
 [CLR ETW 키워드 및 수준](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)  
 범주별 이벤트 필터링을 가능하게 하는 런타임 및 런다운 공급자에 대한 키워드를 설명합니다.  
  
 [CLR ETW 이벤트](../../../docs/framework/performance/clr-etw-events.md)  
 CLR ETW 이벤트, 해당 키워드 및 이벤트 데이터를 자세히 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [.NET Framework의 ETW 이벤트](../../../docs/framework/performance/etw-events.md)
