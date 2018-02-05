---
title: "사용자 정의 함수 및 변수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 4772f20e-1e7f-496e-93c2-1484473be555
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b6870861541a063c56f83dcb286d21a5a970d1b1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="user-defined-functions-and-variables"></a>사용자 정의 함수 및 변수
<xref:System.Xml.XPath.XPathNavigator> 클래스는 <xref:System.Xml.XPath.XPathDocument> 데이터와 상호 작용하는 데 사용되는 메서드 집합을 제공합니다. XPath 쿼리 식에서 사용되는 확장명 함수 및 변수를 구현하여 표준 XPath 함수를 보완할 수 있습니다. <xref:System.Xml.XPath.XPathExpression.SetContext%2A> 메서드는 <xref:System.Xml.Xsl.XsltContext>에서 파생되는 사용자 정의 컨텍스트를 적용할 수 있습니다. 사용자 정의 함수는 사용자 지정 컨텍스트로 확인됩니다.  
  
 확장명 함수 및 변수는 XML 삽입 공격을 방지하는 데 유용할 수 있습니다. 이러한 시나리오에서 사용자 입력은 처리 명령과 연결된 원시 입력이 아닌 사용자 지정 변수로 할당되고 확장명 함수로 처리됩니다. 확장 함수 및 변수에는 사용자 입력이 포함되어 있어서 디자이너에서 의도한 대로 XML 데이터에 대해서만 작업을 수행합니다.  
  
 확장을 사용하려면 확장 함수 및 변수를 지원하는 인터페이스 <xref:System.Xml.Xsl.XsltContext> 및 <xref:System.Xml.Xsl.IXsltContextFunction>과 함께 사용자 지정 <xref:System.Xml.Xsl.IXsltContextVariable> 클래스를 구현합니다. <xref:System.Xml.XPath.XPathExpression>은 사용자 입력을 <xref:System.Xml.Xsl.XsltArgumentList>와 함께 사용자 지정 <xref:System.Xml.Xsl.XsltContext>에 추가합니다.  
  
 <xref:System.Xml.XPath.XPathExpression>은 <xref:System.Xml.XPath.XPathNavigator>가 식에서 식별된 노드를 검색 및 처리하는 데 사용하는 컴파일된 쿼리를 나타냅니다.  
  
 다음 예제는 <xref:System.Xml.Xsl.XsltContext>에서 파생되는 사용자 지정 컨텍스트 클래스의 구현을 보여 줍니다. 코드의 주석은 클래스 멤버 및 사용자 지정 함수에서의 클래스 멤버 사용에 대해 설명합니다. 함수 및 변수 구현과 이러한 구현을 사용하는 샘플 응용 프로그램은 이 코드 세그먼트를 따릅니다.  
  
 [!code-csharp[XPathExtensionFunctions#2](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#2)]
 [!code-vb[XPathExtensionFunctions#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#2)]  
  
 다음 코드는 <xref:System.Xml.Xsl.IXsltContextFunction>을 구현합니다. <xref:System.Xml.Xsl.IXsltContextFunction>을 구현하는 클래스는 사용자 정의 함수를 확인 및 실행합니다. 이 예제는 `private int CountChar(string title, char charTocount)` 선언에서 식별된 함수를 사용합니다.  
  
 코드 주석은 클래스 멤버에 대해 설명합니다.  
  
 [!code-csharp[XPathExtensionFunctions#3](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#3)]
 [!code-vb[XPathExtensionFunctions#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#3)]  
  
 다음 코드는 <xref:System.Xml.Xsl.IXsltContextVariable>을 구현합니다. 이 클래스는 XPath 쿼리 식의 사용자 정의 변수에 대한 참조를 런타임에서 확인합니다. 이 클래스의 인스턴스는 사용자 지정 <xref:System.Xml.Xsl.XsltContext.ResolveVariable%2A> 클래스의 재정의된 <xref:System.Xml.Xsl.XsltContext> 메서드에서 생성 및 반환됩니다.  
  
 코드 주석은 클래스 멤버에 대해 설명합니다.  
  
 [!code-csharp[XPathExtensionFunctions#4](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#4)]
 [!code-vb[XPathExtensionFunctions#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#4)]  
  
 다음 코드는 범위에 있는 이전 클래스 정의를 통해 사용자 지정 함수를 사용하여 `Tasks.xml` 문서의 요소에서 문자 수를 카운트합니다. 코드의 주석은 사용자 지정 함수를 컴파일하고 `Tasks.xml` 문서에 대해 이를 실행하는 코드에 대해 설명합니다.  
  
 [!code-csharp[XPathExtensionFunctions#1](../../../../samples/snippets/csharp/VS_Snippets_Data/xpathextensionfunctions/cs/xpathextensionfunctions.cs#1)]
 [!code-vb[XPathExtensionFunctions#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/xpathextensionfunctions/vb/xpathextensionfunctions.vb#1)]  
  
 이 예제에서는 다음 XML 데이터를 사용합니다.  
  
 [!code-xml[XPathExtensionFunctions#5](../../../../samples/snippets/xml/VS_Snippets_Data/xpathextensionfunctions/XML/tasks.xml#5)]
