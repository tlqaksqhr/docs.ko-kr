---
title: "어셈블리 위치 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "어셈블리[.NET Framework], 위치"
  - "어셈블리 찾기"
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# 어셈블리 위치
어셈블리 위치는 공용 언어 런타임에서 참조 시에 이 어셈블리를 찾을 수 있는지를 결정합니다. 또한 이 어셈블리를 다른 어셈블리와 공유할 수 있는지를 결정합니다.  다음과 같은 위치에 어셈블리를 배포할 수 있습니다.  
  
-   응용 프로그램 디렉터리 또는 하위 디렉터리  
  
     가장 일반적인 어셈블리 배포 위치입니다.  응용 프로그램 루트 디렉터리의 하위 디렉터리는 언어나 Culture를 기반으로 할 수 있습니다.  어셈블리의 Culture 특성에 정보가 들어 있는 경우, 이 어셈블리는 이 Culture와 이름이 동일한 응용 프로그램 디렉터리의 하위 디렉터리에 존재해야 합니다.  
  
-   전역 어셈블리 캐시  
  
     이 캐시는 공용 언어 런타임이 설치될 때마다 설치되는 시스템 수준의 캐시입니다.  다중 응용 프로그램에서 어셈블리를 공유하려는 경우, 대부분은 이 어셈블리를 전역 어셈블리 캐시에 배포해야 합니다.  
  
-   HTTP 서버  
  
     HTTP 서버에 배포된 어셈블리는 강력한 이름을 사용해야 합니다. 이 이름은 응용 프로그램 구성 파일의 코드베이스 섹션에서 어셈블리를 가리킵니다.  
  
## 참고 항목  
 [어셈블리 만들기](../../../docs/framework/app-domains/create-assemblies.md)   
 [전역 어셈블리 캐시](../../../docs/framework/app-domains/gac.md)   
 [런타임에서 어셈블리를 찾는 방법](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [어셈블리를 사용한 프로그래밍](../../../docs/framework/app-domains/programming-with-assemblies.md)