---
title: "System.Xml 사용법 | Microsoft Docs"
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
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# System.Xml 사용법
이 섹션에 있는 여러 유형의 사용에 대 한 이야기 <xref:System.Xml?displayProperty=fullName> 네임 스페이스는 XML 데이터를 나타내는 데 사용할 수 있습니다.  
  
 **X 하지 않으려면** 사용 <xref:System.Xml.XmlNode> 또는 <xref:System.Xml.XmlDocument> XML 데이터를 표시 하도록 합니다. 인스턴스를 사용 하 여 유리한 <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, 또는의 하위 형식을 <xref:System.Xml.Linq.XNode> 대신 합니다.`XmlNode` 및 `XmlDocument` 는 공용 Api를 노출 하기 위한 설계 되지 않았습니다.  
  
 **✓ 수행** 사용 `XmlReader`, `IXPathNavigable`, 또는의 하위 형식을 `XNode` 받아들이거나 XML을 반환 하는 멤버의 입력 또는 출력으로 합니다.  
  
 대신 이러한 추상화를 사용 하 여 `XmlDocument`, `XmlNode`, 또는 <xref:System.Xml.XPath.XPathDocument>, 이 메서드는 메모리 내 XML 문서의 특정 구현에서 분리 하 고 노출 하는 가상 XML 데이터 원본을 사용 하도록 허용 하기 때문에, `XNode`, `XmlReader`, 또는 <xref:System.Xml.XPath.XPathNavigator>합니다.  
  
 **X 하지 않으려면** 하위 클래스 `XmlDocument` 경우 만들려면 기본 개체 모델 또는 데이터 원본에 대 한 XML 뷰를 나타내는 형식입니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [사용 지침](../../../docs/standard/design-guidelines/usage-guidelines.md)