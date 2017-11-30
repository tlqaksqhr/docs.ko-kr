---
title: "공유 웹 호스팅을 위한 최적화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f423d867d4fada075800650627c94f9d09e9e7a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="optimization-for-shared-web-hosting"></a>공유 웹 호스팅을 위한 최적화
여러 개의 작은 웹 사이트를 호스트 하 여 공유 하는 서버에 대 한 관리자 인 경우 성능을 최적화 하 고 다음을 추가 하 여 사이트 용량을 늘릴 수 `gcTrimCommitOnLowMemory` 을로 설정 된 `runtime` .NET에 Aspnet.config 파일에 있는 노드 디렉터리:  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  이 설정은 호스팅 시나리오 공유 웹에만 권장 됩니다.  
  
 가비지 수집기는 이후 할당에 대 한 메모리를 보존, 때문에 커밋된 공간이 꼭 필요한 것 보다 클 수 있습니다. 이 공간 시간을 줄일 수 있으면 시스템 메모리에 상당한 부하를 합니다. 이 커밋된 공간 줄이기 성능이 향상 됩니다 하 고 더 많은 사이트를 호스트 하는 기능을 확장 합니다.  
  
 경우는 `gcTrimCommitOnLowMemory` 설정을 사용 하는, 가비지 수집기 시스템 메모리 로드를 평가 하 고 부하 90%에 도달할 때 트리밍 모드를 입력 합니다. 부하 85% 미만 떨어져야 트리밍 모드를 유지 합니다.  
  
 가비지 수집기를 결정할 수 조건이 충족 될 경우는 `gcTrimCommitOnLowMemory` 설정을 현재 응용 프로그램에 도움이 되지 않습니다 되며 무시 합니다.  
  
## <a name="example"></a>예제  
 다음 XML 조각은 방법을 볼 수는 `gcTrimCommitOnLowMemory` 설정 합니다. 타원에 있을 수 있는 다른 설정을 나타내는 `runtime` 노드.  
  
```xml  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [가비지 수집](../../../docs/standard/garbage-collection/index.md)
