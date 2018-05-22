---
title: XSLT 매개 변수
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: fe60aaa0-ae43-4b1c-9be1-426af66ba757
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ef57d16c52100398919563205a97205be3c5dd7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="xslt-parameters"></a><span data-ttu-id="a679f-102">XSLT 매개 변수</span><span class="sxs-lookup"><span data-stu-id="a679f-102">XSLT Parameters</span></span>
<span data-ttu-id="a679f-103"><xref:System.Xml.Xsl.XsltArgumentList> 메서드를 사용하여 <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>에 XSLT 매개 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a679f-103">XSLT parameters are added to the <xref:System.Xml.Xsl.XsltArgumentList> using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span> <span data-ttu-id="a679f-104">이 때 정규화된 이름 및 네임스페이스 URI가 매개 변수 개체와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="a679f-104">A qualified name and namespace URI are associated with the parameter object at that time.</span></span>  
  
### <a name="to-use-an-xslt-parameter"></a><span data-ttu-id="a679f-105">XSLT 매개 변수를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="a679f-105">To use an XSLT parameter</span></span>  
  
1.  <span data-ttu-id="a679f-106"><xref:System.Xml.Xsl.XsltArgumentList> 메서드를 사용하여 <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> 개체를 만들고 매개 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a679f-106">Create an <xref:System.Xml.Xsl.XsltArgumentList> object and add the parameter using the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method.</span></span>  
  
2.  <span data-ttu-id="a679f-107">스타일시트에서 매개 변수를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a679f-107">Call the parameter from the style sheet.</span></span>  
  
3.  <span data-ttu-id="a679f-108"><xref:System.Xml.Xsl.XsltArgumentList> 개체를 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="a679f-108">Pass the <xref:System.Xml.Xsl.XsltArgumentList> object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="parameter-types"></a><span data-ttu-id="a679f-109">매개 변수 형식</span><span class="sxs-lookup"><span data-stu-id="a679f-109">Parameter Types</span></span>  
 <span data-ttu-id="a679f-110">매개 변수 개체는 W3C 형식과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a679f-110">The parameter object should correspond to a W3C type.</span></span> <span data-ttu-id="a679f-111">다음 표에서는 해당 W3C 형식, 해당 Microsoft .NET 클래스(형식) 및 W3C 형식이 XPath 형식인지 또는 XSLT 형식인지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a679f-111">The following table shows the corresponding W3C types, the equivalent Microsoft .NET classes (type), and whether the W3C type is an XPath type or XSLT type.</span></span>  
  
|<span data-ttu-id="a679f-112">W3C 형식</span><span class="sxs-lookup"><span data-stu-id="a679f-112">W3C type</span></span>|<span data-ttu-id="a679f-113">해당 .NET 클래스(형식)</span><span class="sxs-lookup"><span data-stu-id="a679f-113">Equivalent .NET class (type)</span></span>|<span data-ttu-id="a679f-114">XPath 또는 XSLT 형식</span><span class="sxs-lookup"><span data-stu-id="a679f-114">XPath or XSLT type</span></span>|  
|--------------|------------------------------------|------------------------|  
|`String`|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="a679f-115">XPath</span><span class="sxs-lookup"><span data-stu-id="a679f-115">XPath</span></span>|  
|`Boolean`|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="a679f-116">XPath</span><span class="sxs-lookup"><span data-stu-id="a679f-116">XPath</span></span>|  
|`Number`|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="a679f-117">XPath</span><span class="sxs-lookup"><span data-stu-id="a679f-117">XPath</span></span>|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|<span data-ttu-id="a679f-118">XSLT</span><span class="sxs-lookup"><span data-stu-id="a679f-118">XSLT</span></span>|  
|`Node*`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|<span data-ttu-id="a679f-119">XPath</span><span class="sxs-lookup"><span data-stu-id="a679f-119">XPath</span></span>|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator><br /><br /> <span data-ttu-id="a679f-120">**XPathNavigator[]**</span><span class="sxs-lookup"><span data-stu-id="a679f-120">**XPathNavigator[]**</span></span>|<span data-ttu-id="a679f-121">XPath</span><span class="sxs-lookup"><span data-stu-id="a679f-121">XPath</span></span>|  
  
 <span data-ttu-id="a679f-122">\*단일 노드가 포함된 노드 집합과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a679f-122">\*This is equivalent to a node set that contains a single node.</span></span>  
  
 <span data-ttu-id="a679f-123">매개 변수 개체가 위 클래스에 해당하지 않으면 다음 규칙에 따라 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a679f-123">If the parameter object is not one of the above classes, it is converted according to the following rules.</span></span> <span data-ttu-id="a679f-124">CLR(공용 언어 런타임) 숫자 형식은 <xref:System.Double>로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a679f-124">Common language runtime (CLR) numeric types are converted to <xref:System.Double>.</span></span> <span data-ttu-id="a679f-125"><xref:System.DateTime> 형식은 <xref:System.String>으로 변환되고,</span><span class="sxs-lookup"><span data-stu-id="a679f-125">The <xref:System.DateTime> type is converted to <xref:System.String>.</span></span> <span data-ttu-id="a679f-126"><xref:System.Xml.XPath.IXPathNavigable> 형식은 <xref:System.Xml.XPath.XPathNavigator>로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a679f-126"><xref:System.Xml.XPath.IXPathNavigable> types are converted to <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="a679f-127">**XPathNavigator[]** 는 <xref:System.Xml.XPath.XPathNodeIterator>로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a679f-127">**XPathNavigator[]** is converted to <xref:System.Xml.XPath.XPathNodeIterator>.</span></span>  
  
 <span data-ttu-id="a679f-128">다른 모든 형식은 오류를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="a679f-128">All other types throw an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a679f-129">예</span><span class="sxs-lookup"><span data-stu-id="a679f-129">Example</span></span>  
 <span data-ttu-id="a679f-130">다음 예제에서는 <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> 메서드를 사용하여 계산된 할인 기간을 유지하는 매개 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a679f-130">The following example uses the <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> method to create a parameter to hold calculated discount date.</span></span> <span data-ttu-id="a679f-131">할인 기간은 주문 날짜로부터 20일 동안으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="a679f-131">The discount date is calculated to be 20 days from the order date.</span></span>  
  
 [!code-csharp[XSLT_Param#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Param/CS/xsltparam.cs#1)]
 [!code-vb[XSLT_Param#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Param/VB/xsltparam.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="a679f-132">입력</span><span class="sxs-lookup"><span data-stu-id="a679f-132">Input</span></span>  
  
##### <a name="orderxml"></a><span data-ttu-id="a679f-133">order.xml</span><span class="sxs-lookup"><span data-stu-id="a679f-133">order.xml</span></span>  
 [!code-xml[XSLT_Param#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/order.xml#2)]  
  
##### <a name="discountxsl"></a><span data-ttu-id="a679f-134">discount.xsl</span><span class="sxs-lookup"><span data-stu-id="a679f-134">discount.xsl</span></span>  
 [!code-xml[XSLT_Param#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/discount.xsl#3)]  
  
### <a name="output"></a><span data-ttu-id="a679f-135">출력</span><span class="sxs-lookup"><span data-stu-id="a679f-135">Output</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<order>  
  <total>36.9</total>  
     15% discount if paid by: 2/4/2004 12:00:00 AM  
</order>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a679f-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a679f-136">See Also</span></span>  
 [<span data-ttu-id="a679f-137">XSLT 변환</span><span class="sxs-lookup"><span data-stu-id="a679f-137">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
