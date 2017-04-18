---
title: "Optimization for Shared Web Hosting | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "garbage collection, Web hosting"
  - "garbage collection, optimizing"
  - "garbage collection, shared Web hosting"
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Optimization for Shared Web Hosting
여러 개의 작은 웹 사이트를 호스팅하여 공유되는 서버의 관리자는 .NET Framework 디렉터리에 있는 Aspnet.config 파일의 `runtime` 노드에 다음 `gcTrimCommitOnLowMemory` 설정을 추가하여 성능을 최적화하고 사이트 용량을 늘릴 수 있습니다.  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  이 설정은 공유 웹 호스팅 시나리오에 대해서만 권장됩니다.  
  
 가비지 수집기는 다음 할당을 위해 메모리를 유지하므로 커밋된 공간이 실질적으로 필요한 것보다 클 수 있습니다.  시스템 메모리에 로드가 많을 경우에 대비해 이 공간을 줄일 수 있습니다.  이러한 커밋된 공간을 줄이면 성능이 향상되고 용량이 확장되어 더 많은 사이트를 호스팅할 수 있습니다.  
  
 `gcTrimCommitOnLowMemory` 설정을 사용하면 가비지 수집기가 시스템 메모리 로드를 평가하여 로드가 90%에 도달할 경우 트리밍 모드로 들어가고.  로드가 85% 아래로 낮아질 때까지 트리밍 모드를 유지합니다.  
  
 조건이 충족될 경우 가비지 수집기는 `gcTrimCommitOnLowMemory` 설정이 현재 응용 프로그램에 도움이 안 된다고 판단하여 이 설정을 무시할 수 있습니다.  
  
## 예제  
 다음 XML 조각에서는 `gcTrimCommitOnLowMemory` 설정을 사용하도록 설정하는 방법을 보여 줍니다.  줄임표는 `runtime` 노드에 있을 수 있는 다른 설정을 나타냅니다.  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## 참고 항목  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)