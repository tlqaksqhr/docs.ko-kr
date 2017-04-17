---
title: "배열 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "클래스 라이브러리 디자인 지침 [.NET Framework] 배열"
  - "배열 [.NET Framework] 사용 지침"
  - "빈 배열"
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# 배열
**✓ 수행** 배열에는 공개 Api 통해 컬렉션을 사용 하는 것을 선호 합니다.[컬렉션](../../../docs/standard/design-guidelines/guidelines-for-collections.md) 섹션에서는 컬렉션 및 배열 중에서 선택 하는 방법에 대 한 세부 정보를 제공 합니다.  
  
 **X 하지 않으려면** 읽기 전용 배열 필드를 사용 합니다. 필드 자체 읽기 전용 이므로 변경할 수 없습니다. 하지만 배열의 요소를 변경할 수 있습니다.  
  
 **✓ 고려** 다차원 배열 대신 가변된 배열을 사용 합니다.  
  
 가변된 배열은 배열도 있는 요소가 있는 배열입니다. 요소를 구성 하는 배열의 크기는 서로 다를 다차원 배열에 비해 일부 \(예: 스파스 행렬\) 데이터 집합에 대 한 절약할 공간을 수 있습니다. 또한 CLR 하므로 일부 시나리오에서 더 나은 런타임 성능의 나타낼 수 있습니다 가변된 배열에 대 한 인덱스 작업을 최적화 합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 <xref:System.Array>   
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [사용 지침](../../../docs/standard/design-guidelines/usage-guidelines.md)