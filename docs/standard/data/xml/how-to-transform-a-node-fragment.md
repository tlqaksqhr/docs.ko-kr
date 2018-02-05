---
title: "방법: 노드 조각 변형"
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
ms.assetid: 73a6c582-b9d7-4fa7-9a05-6d931e1f3de8
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2b85bcbf537f5306b0b4c30630523eaf511dd3d9
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-transform-a-node-fragment"></a><span data-ttu-id="220a3-102">방법: 노드 조각 변형</span><span class="sxs-lookup"><span data-stu-id="220a3-102">How to: Transform a Node Fragment</span></span>
<span data-ttu-id="220a3-103"><xref:System.Xml.XmlDocument> 또는 <xref:System.Xml.XPath.XPathDocument> 개체에 포함된 데이터를 변환하는 경우 XSLT 변환이 문서 전체에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="220a3-103">When you transform data contained in an <xref:System.Xml.XmlDocument> or <xref:System.Xml.XPath.XPathDocument> object the XSLT transformations apply to a document as a whole.</span></span> <span data-ttu-id="220a3-104">즉, 문서 루트 노드 이외의 노드에 전달해도 변환 프로세스에서 로드된 문서의 모든 노드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="220a3-104">In other words, if you pass in a node other than the document root node, this does not prevent the transformation process from accessing all nodes in the loaded document.</span></span> <span data-ttu-id="220a3-105">노드 조각을 변환하려면 노드 조각만 포함된 별도의 개체를 만들고 이 개체를 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드에 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="220a3-105">To transform a node fragment, you must create a separate object containing just the node fragment, and pass that object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="220a3-106">절차</span><span class="sxs-lookup"><span data-stu-id="220a3-106">Procedures</span></span>  
  
#### <a name="to-transform-a-node-fragment"></a><span data-ttu-id="220a3-107">노드 조각을 변형하려면</span><span class="sxs-lookup"><span data-stu-id="220a3-107">To transform a node fragment</span></span>  
  
1.  <span data-ttu-id="220a3-108">소스 문서가 포함된 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="220a3-108">Create an object containing the source document.</span></span>  
  
2.  <span data-ttu-id="220a3-109">변환할 노드 조각을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="220a3-109">Locate the node fragment you wish to transform.</span></span>  
  
3.  <span data-ttu-id="220a3-110">노드 조각만 포함된 별도의 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="220a3-110">Create separate object with just the node fragment.</span></span>  
  
4.  <span data-ttu-id="220a3-111">노드 조각을 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="220a3-111">Pass the node fragment to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="220a3-112">예</span><span class="sxs-lookup"><span data-stu-id="220a3-112">Example</span></span>  
 <span data-ttu-id="220a3-113">다음 예제에서는 노드 조각을 변형하고 결과를 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="220a3-113">The following example transforms a node fragment and outputs the results to the console.</span></span>  
  
 [!code-csharp[XSLT_NodeFrag#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_NodeFrag/CS/xslt_frag.cs#1)]
 [!code-vb[XSLT_NodeFrag#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_NodeFrag/VB/xslt_frag.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="220a3-114">입력</span><span class="sxs-lookup"><span data-stu-id="220a3-114">Input</span></span>  
  
##### <a name="booksxml"></a><span data-ttu-id="220a3-115">books.xml</span><span class="sxs-lookup"><span data-stu-id="220a3-115">books.xml</span></span>  
 [!code-xml[XML_Core_Files#1](../../../../samples/snippets/xml/VS_Snippets_Data/XML_Core_Files/XML/books.xml#1)]  
  
##### <a name="singlexsl"></a><span data-ttu-id="220a3-116">single.xsl</span><span class="sxs-lookup"><span data-stu-id="220a3-116">single.xsl</span></span>  
 [!code-xml[XSLT_NodeFrag#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_NodeFrag/XML/single.xsl#2)]  
  
### <a name="output"></a><span data-ttu-id="220a3-117">출력</span><span class="sxs-lookup"><span data-stu-id="220a3-117">Output</span></span>  
 <span data-ttu-id="220a3-118">책 제목은 The Confidence Man입니다.</span><span class="sxs-lookup"><span data-stu-id="220a3-118">Book title is The Confidence Man.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="220a3-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="220a3-119">See Also</span></span>  
 [<span data-ttu-id="220a3-120">XslCompiledTransform 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="220a3-120">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
