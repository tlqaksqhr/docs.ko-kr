---
title: "사용 지침 | Microsoft Docs"
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
  - "클래스 라이브러리 디자인 지침 [.NET Framework] 사용 지침"
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 사용 지침
이 섹션에서는 일반 종류를 사용 하 여 공개적으로 액세스할 수 있는 Api에 대 한 지침입니다. 기본 제공 프레임 워크 형식 \(예: 직렬화 특성\) 및 일반적인 연산자 오버 로드를 직접 사용 하 여 다룹니다.  
  
 <xref:System.IDisposable?displayProperty=fullName> 인터페이스는이 섹션에서 다루지 않습니다 하지만에 대해서는 설명의 [삭제 패턴](../../../docs/standard/design-guidelines/dispose-pattern.md) 섹션입니다.  
  
> [!NOTE]
>  지침 및 다른 일반적인 방법에 대 한 추가 정보에 대 한.NET Framework의 기본 제공 형식 참조는 다음에 대 한 참조 항목: <xref:System.DateTime?displayProperty=fullName>, <xref:System.DateTimeOffset?displayProperty=fullName>, <xref:System.ICloneable?displayProperty=fullName>, <xref:System.IComparable%601?displayProperty=fullName>, <xref:System.IEquatable%601?displayProperty=fullName>, <xref:System.Nullable%601?displayProperty=fullName>, <xref:System.Object?displayProperty=fullName>, <xref:System.Uri?displayProperty=fullName>합니다.  
  
## 단원 내용  
 [배열](../../../docs/standard/design-guidelines/arrays.md)  
 [특성](../../../docs/standard/design-guidelines/특성.md)  
 [컬렉션](../../../amples/snippets/cpp/VS_Snippets_Misc/cx_collections/cpp/collections.vcxproj)  
 [Serialization](../../../docs/standard/design-guidelines/serialization.md)  
 [System.Xml 사용법](../../../docs/standard/design-guidelines/system-xml-usage.md)  
 [같음 연산자](../../../docs/standard/design-guidelines/equality-operators.md)  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)