---
title: "&lt;commonBehaviors&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;commonBehaviors&gt;
`commonBehaviors` 섹션은 machine.config 파일에만 정의할 수 있습니다.  이 섹션은 두 자식 컬렉션 `endpointBehaviors` 및 `serviceBehaviors`를 정의합니다.  각 컬렉션은 컴퓨터의 모든 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 끝점 및 서비스가 사용하는 동작 요소를 각각 정의합니다.  `endpointBehaviors`에 정의된 동작은 클라이언트에만 적용되고 `serviceBehaviors`에 정의된 동작은 서비스에만 적용됩니다.  두 `commonBehaviors` 및 `behaviors` 섹션 모두에서 동작이 정의되는 경우 `behaviors` 섹션의 동작이 우선합니다.