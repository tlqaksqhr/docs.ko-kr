---
title: '방법: 노드 조각 변형'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 73a6c582-b9d7-4fa7-9a05-6d931e1f3de8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4cd35e469a16dc2fdb3a7f4afd89d04f67185cd5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-transform-a-node-fragment"></a>방법: 노드 조각 변형
<xref:System.Xml.XmlDocument> 또는 <xref:System.Xml.XPath.XPathDocument> 개체에 포함된 데이터를 변환하는 경우 XSLT 변환이 문서 전체에 적용됩니다. 즉, 문서 루트 노드 이외의 노드에 전달해도 변환 프로세스에서 로드된 문서의 모든 노드에 액세스할 수 있습니다. 노드 조각을 변환하려면 노드 조각만 포함된 별도의 개체를 만들고 이 개체를 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드에 전달해야 합니다.  
  
## <a name="procedures"></a>절차  
  
#### <a name="to-transform-a-node-fragment"></a>노드 조각을 변형하려면  
  
1.  소스 문서가 포함된 개체를 만듭니다.  
  
2.  변환할 노드 조각을 찾습니다.  
  
3.  노드 조각만 포함된 별도의 개체를 만듭니다.  
  
4.  노드 조각을 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드에 전달합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 노드 조각을 변형하고 결과를 콘솔에 출력합니다.  
  
 [!code-csharp[XSLT_NodeFrag#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_NodeFrag/CS/xslt_frag.cs#1)]
 [!code-vb[XSLT_NodeFrag#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_NodeFrag/VB/xslt_frag.vb#1)]  
  
### <a name="input"></a>입력  
  
##### <a name="booksxml"></a>books.xml  
 [!code-xml[XML_Core_Files#1](../../../../samples/snippets/xml/VS_Snippets_Data/XML_Core_Files/XML/books.xml#1)]  
  
##### <a name="singlexsl"></a>single.xsl  
 [!code-xml[XSLT_NodeFrag#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_NodeFrag/XML/single.xsl#2)]  
  
### <a name="output"></a>출력  
 책 제목은 The Confidence Man입니다.  
  
## <a name="see-also"></a>참고 항목  
 [XslCompiledTransform 클래스 사용](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
