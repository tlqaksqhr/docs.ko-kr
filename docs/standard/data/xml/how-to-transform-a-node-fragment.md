---
title: "방법: 노드 조각 변환 | Microsoft Docs"
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
ms.assetid: 73a6c582-b9d7-4fa7-9a05-6d931e1f3de8
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# 방법: 노드 조각 변환
<xref:System.Xml.XmlDocument> 또는 <xref:System.Xml.XPath.XPathDocument> 개체에 포함된 데이터를 변환하는 경우 XSLT 변환이 문서 전체에 적용됩니다.  즉, 문서 루트 노드 이외의 노드에 전달해도 변환 프로세스에서 로드된 문서의 모든 노드에 액세스할 수 있습니다.  노드 조각을 변환하려면 노드 조각만 포함된 별도의 개체를 만들고 이 개체를 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드에 전달해야 합니다.  
  
## 절차  
  
#### 노드 조각을 변환하려면  
  
1.  소스 문서가 포함된 개체를 만듭니다.  
  
2.  변환할 노드 조각을 찾습니다.  
  
3.  노드 조각만 포함된 별도의 개체를 만듭니다.  
  
4.  노드 조각을 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드에 전달합니다.  
  
## 예제  
 다음 예제에서는 노드 조각을 변환하고 결과를 콘솔에 출력합니다.  
  
 [!code-csharp[XSLT_NodeFrag#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_NodeFrag/CS/xslt_frag.cs#1)]
 [!code-vb[XSLT_NodeFrag#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_NodeFrag/VB/xslt_frag.vb#1)]  
  
### 입력  
  
##### books.xml  
 [!code-xml[XML_Core_Files#1](../../../../samples/snippets/xml/VS_Snippets_Data/XML_Core_Files/XML/books.xml#1)]  
  
##### single.xsl  
 [!code-xml[XSLT_NodeFrag#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_NodeFrag/XML/single.xsl#2)]  
  
### 출력  
 책 제목은 The Confidence Man입니다.  
  
## 참고 항목  
 [XslCompiledTransform 클래스 사용](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)