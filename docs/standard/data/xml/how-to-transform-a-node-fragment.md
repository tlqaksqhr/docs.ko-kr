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
ms.locfileid: "33568565"
---
# <a name="how-to-transform-a-node-fragment"></a><span data-ttu-id="c4d92-102">방법: 노드 조각 변형</span><span class="sxs-lookup"><span data-stu-id="c4d92-102">How to: Transform a Node Fragment</span></span>
<span data-ttu-id="c4d92-103"><xref:System.Xml.XmlDocument> 또는 <xref:System.Xml.XPath.XPathDocument> 개체에 포함된 데이터를 변환하는 경우 XSLT 변환이 문서 전체에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4d92-103">When you transform data contained in an <xref:System.Xml.XmlDocument> or <xref:System.Xml.XPath.XPathDocument> object the XSLT transformations apply to a document as a whole.</span></span> <span data-ttu-id="c4d92-104">즉, 문서 루트 노드 이외의 노드에 전달해도 변환 프로세스에서 로드된 문서의 모든 노드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d92-104">In other words, if you pass in a node other than the document root node, this does not prevent the transformation process from accessing all nodes in the loaded document.</span></span> <span data-ttu-id="c4d92-105">노드 조각을 변환하려면 노드 조각만 포함된 별도의 개체를 만들고 이 개체를 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드에 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d92-105">To transform a node fragment, you must create a separate object containing just the node fragment, and pass that object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="c4d92-106">절차</span><span class="sxs-lookup"><span data-stu-id="c4d92-106">Procedures</span></span>  
  
#### <a name="to-transform-a-node-fragment"></a><span data-ttu-id="c4d92-107">노드 조각을 변형하려면</span><span class="sxs-lookup"><span data-stu-id="c4d92-107">To transform a node fragment</span></span>  
  
1.  <span data-ttu-id="c4d92-108">소스 문서가 포함된 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4d92-108">Create an object containing the source document.</span></span>  
  
2.  <span data-ttu-id="c4d92-109">변환할 노드 조각을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c4d92-109">Locate the node fragment you wish to transform.</span></span>  
  
3.  <span data-ttu-id="c4d92-110">노드 조각만 포함된 별도의 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4d92-110">Create separate object with just the node fragment.</span></span>  
  
4.  <span data-ttu-id="c4d92-111">노드 조각을 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d92-111">Pass the node fragment to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4d92-112">예</span><span class="sxs-lookup"><span data-stu-id="c4d92-112">Example</span></span>  
 <span data-ttu-id="c4d92-113">다음 예제에서는 노드 조각을 변형하고 결과를 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d92-113">The following example transforms a node fragment and outputs the results to the console.</span></span>  
  
 [!code-csharp[XSLT_NodeFrag#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_NodeFrag/CS/xslt_frag.cs#1)]
 [!code-vb[XSLT_NodeFrag#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_NodeFrag/VB/xslt_frag.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="c4d92-114">입력</span><span class="sxs-lookup"><span data-stu-id="c4d92-114">Input</span></span>  
  
##### <a name="booksxml"></a><span data-ttu-id="c4d92-115">books.xml</span><span class="sxs-lookup"><span data-stu-id="c4d92-115">books.xml</span></span>  
 [!code-xml[XML_Core_Files#1](../../../../samples/snippets/xml/VS_Snippets_Data/XML_Core_Files/XML/books.xml#1)]  
  
##### <a name="singlexsl"></a><span data-ttu-id="c4d92-116">single.xsl</span><span class="sxs-lookup"><span data-stu-id="c4d92-116">single.xsl</span></span>  
 [!code-xml[XSLT_NodeFrag#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_NodeFrag/XML/single.xsl#2)]  
  
### <a name="output"></a><span data-ttu-id="c4d92-117">출력</span><span class="sxs-lookup"><span data-stu-id="c4d92-117">Output</span></span>  
 <span data-ttu-id="c4d92-118">책 제목은 The Confidence Man입니다.</span><span class="sxs-lookup"><span data-stu-id="c4d92-118">Book title is The Confidence Man.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4d92-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4d92-119">See Also</span></span>  
 [<span data-ttu-id="c4d92-120">XslCompiledTransform 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="c4d92-120">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
