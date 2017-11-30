---
title: "변형의 결과 트리 조각"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df363480-ba02-4233-9ddf-8434e421c4f1
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1a4b585fe34a841061f8e5bab7cb18a58f53cfe8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="result-tree-fragment-in-transformations"></a><span data-ttu-id="d34e3-102">변형의 결과 트리 조각</span><span class="sxs-lookup"><span data-stu-id="d34e3-102">Result Tree Fragment in Transformations</span></span>
> [!NOTE]
>  <span data-ttu-id="d34e3-103"><xref:System.Xml.Xsl.XslTransform> 클래스는 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="d34e3-104"><xref:System.Xml.Xsl.XslCompiledTransform> 클래스를 사용하여 XSLT(Extensible Stylesheet Language for Transformations) 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="d34e3-105">참조 [XslCompiledTransform 클래스를 사용 하 여](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) 및 [마이그레이션 XslTransform 클래스에서](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) 자세한 정보에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-105">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="d34e3-106">결과 트리 조각이라고도 하는 노드 조각은 특수한 형식의 노드 집합과 크게 다르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-106">Result tree fragments, also known as result tree fragments, are nothing more than a special type of node set.</span></span> <span data-ttu-id="d34e3-107">노드 집합에 대해 수행될 수 있는 함수는 노드 조각에 대해서도 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-107">You can perform any function on them that can be performed on a node set.</span></span> <span data-ttu-id="d34e3-108">또는 `node-set()` 함수를 사용하여 결과 트리 조각을 노드 집합으로 변환한 후 나중에 노드 집합을 사용할 수 있는 위치에서 변환된 해당 노드 집합을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-108">Or, you can also convert a result tree fragment to a node set using the `node-set()` function and subsequently use it any place that a node set can be used.</span></span>  
  
 <span data-ttu-id="d34e3-109">결과 트리 조각은 스타일시트에서 `<xsl:variable>` 또는 `<xsl:param>` 요소를 특정한 방식으로 사용하여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-109">A result tree fragment is created as a result of using an `<xsl:variable>` or `<xsl:param>` element in a specific manner in a style sheet.</span></span> <span data-ttu-id="d34e3-110">`variable` 및 `parameter` 요소의 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-110">The syntax for the `variable` and `parameter` elements is as follows:</span></span>  
  
```xml  
<xsl:param name=Qname select= XPath Expression >  
    template body  
</xsl:param>  
  
<xsl:variable name=Qname select=XPath Expression >  
    template body  
</xsl:variable>  
```  
  
 <span data-ttu-id="d34e3-111">`parameter` 요소의 경우 해당 값이 여러 방법으로 정규화된 이름(`Qname`)에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-111">For the `parameter` element, the value is assigned to the qualified name (`Qname`) in several ways.</span></span> <span data-ttu-id="d34e3-112">`select` 특성의 XPath(XML Path Language) 식에서 내용을 반환하거나 해당 매개 변수를 템플릿 본문의 내용에 지정하는 방법으로 매개 변수에 기본값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-112">You can assign a default value to the parameter by returning content from the XML Path Language (XPath) expression in the `select` attribute, or by assigning it the contents of the template body.</span></span>  
  
 <span data-ttu-id="d34e3-113">`variable` 요소의 경우에도 해당 값이 여러 방법으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-113">For the `variable` element, the value is also assigned in several ways.</span></span> <span data-ttu-id="d34e3-114">`select` 특성의 XPath 식에서 내용을 반환하거나 해당 값을 템플릿 본문의 내용에 지정하는 방법으로 값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-114">You can assign it by returning content from the XPath expression in the `select` attribute, or by assigning it the contents of the template body.</span></span>  
  
 <span data-ttu-id="d34e3-115">`parameter` 및 `variable` 요소의 경우, XPath 식에 값이 지정되면 네 가지 기본 XPath 형식인 부울, 문자열, 숫자 또는 노드 집합 중 하나가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-115">For both the `parameter` and `variable` elements, if a value is assigned by the XPath expression, then one of the four basic XPath types will be returned: Boolean, string, number, or node set.</span></span> <span data-ttu-id="d34e3-116">비어 있지 않은 템플릿 본문을 사용하여 해당 값이 지정되면 XPath 이외의 데이터 형식이 반환된 후 결과 트리 조각이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-116">When the value is given by using a non-empty template body, then a non-XPath data type is returned, and that will be a result tree fragment.</span></span>  
  
 <span data-ttu-id="d34e3-117">변수가 이러한 네 가지 기본 XPath 데이터 형식에 속하지 않는 결과 트리 조각에 바인딩될 때가 바로 XPath 쿼리가 네 가지 XPath 개체 형식에 속하지 않는 형식을 반환하는 유일한 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-117">When a variable is bound to a result tree fragment instead of one of the four basic XPath data types, this is the only time that an XPath query returns a type that is not one of the four XPath object types.</span></span> <span data-ttu-id="d34e3-118">결과 트리 조각 및 해당 동작은 www.w3.org/XSLT 사이트에 있는 W3C(World Wide Web 컨소시엄) 사양의 11.1단원 "결과 트리 조각"에서 11.6단원 "템플릿에 매개 변수 전달"에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-118">Result tree fragments and their behavior are discussed in the World Wide Web Consortium (W3C) specification at www.w3.org/XSLT, section 11.1 Result Tree Fragments through section 11.6 Passing Parameters to Templates.</span></span> <span data-ttu-id="d34e3-119">또한 1단원의 "소개"에서는 결과 트리 조각을 반환하거나 만드는 XSLT 네임스페이스에서 템플릿이 요소를 얻는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-119">Also, section 1 Introduction discusses how templates can contain elements from the XSLT namespace that return or create result tree fragments.</span></span>  
  
 <span data-ttu-id="d34e3-120">개념적으로 볼 때 결과 트리 조각은 단일 루트 노드만 있는 노드 집합과 동일하게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-120">A result tree fragment, in concept, behaves like a node set with nothing more than a single root node.</span></span> <span data-ttu-id="d34e3-121">그러나 반환된 노드의 나머지는 자식 노드에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-121">However, the rest of the nodes returned are child nodes.</span></span> <span data-ttu-id="d34e3-122">자식 노드를 프로그래밍 방식으로 나타내려면 `<xsl:copy-of>` 요소를 사용하여 결과 트리 조각을 결과 트리로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-122">To programmatically see the child nodes, copy the result tree fragment to the result tree using the `<xsl:copy-of>` element.</span></span> <span data-ttu-id="d34e3-123">copy-of가 수행될 때 모든 자식 노드도 순서대로 결과 트리에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-123">When the copy-of is performed, all the child nodes are also copied to the result tree in sequence.</span></span> <span data-ttu-id="d34e3-124">`copy` 또는 `copy-of`가 사용될 때까지 결과 트리 조각은 결과 트리 또는 변환 결과에 속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-124">Until a `copy` or `copy-of` is used, a result tree fragment is not part of the result tree or the output from the transformation.</span></span>  
  
 <span data-ttu-id="d34e3-125">결과 트리 조각의 반환된 노드를 검색하기 위해 <xref:System.Xml.XPath.XPathNavigator>가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-125">To iterate over the returned nodes of a result tree fragment, an <xref:System.Xml.XPath.XPathNavigator> is used.</span></span> <span data-ttu-id="d34e3-126">다음 코드 샘플에서는 XML을 포함하는 매개 변수 `fragment`로 함수를 호출하여 스타일시트 내부에서 결과 트리 조각을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-126">The following code sample shows how to create a result tree fragment within a style sheet by calling the function with a parameter `fragment`, which contains XML.</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.adventure-works.com"  
                version="1.0">  
    <xsl:var name="fragment">  
        <node1>  
            <node2/>  
        </node1>  
    <xsl:var>  
  
  <msxsl:script language="C#" implements-prefix="user">  
    function NodeFragment(XPathNavigator nav)  
    {  
      if (nav.HasSelection == false)  
        XPathNavigator.MoveToNext();  
      return;  
    }  
  </msxsl:script>  
  
    <xsl:template match="/">  
            <xsl:value-of select="user:NodeFragment(msxml:node-set($fragment))"/>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
 <span data-ttu-id="d34e3-127">다음은 RTF(서식 있는 텍스트), 즉 노드 집합으로 변환되지 않은 결과 트리 집합 형식으로 된 변수를 보여 주는 또 다른 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-127">Here is another sample showing a variable, which is in Rich Text Format (RTF), and hence, a type of result tree fragment, that is not converted to a node set.</span></span> <span data-ttu-id="d34e3-128">대신 이 변수는 스크립트 함수로 전달되며 <xref:System.Xml.XPath.XPathNavigator>를 사용하여 노드를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-128">Instead, it is passed to a script function, and the <xref:System.Xml.XPath.XPathNavigator> is used to navigate over the nodes.</span></span>  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
        xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
        xmlns:user="urn:books"  
        exclude-result-prefixes="msxsl">  
  
<xsl:output method="xml" indent="yes" omit-xml-declaration="yes"/>  
  
<xsl:variable name="node-fragment">  
    <book>Book1</book>  
    <book>Book2</book>  
    <book>Book3</book>  
    <book>Book4</book>  
</xsl:variable>  
  
<msxsl:script implements-prefix="user" language="c#">  
  
<![CDATA[  
    string func(XPathNavigator nav)  
    {  
        bool b = nav.MoveToFirstChild();  
        if (b)  
            return nav.Value;  
        else  
            return "Does not exist";  
    }  
  
]]>  
  
</msxsl:script>  
  
<xsl:template match="/">  
    <first_book>  
        <xsl:value-of select="user:func($node-fragment)"/>  
    </first_book>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
 <span data-ttu-id="d34e3-129">다음 출력에서는 이 스타일시트를 사용하여 XML을 변환한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-129">The result of transforming any XML with this style sheet is shown in the following output.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d34e3-130">출력</span><span class="sxs-lookup"><span data-stu-id="d34e3-130">Output</span></span>  
  
```xml  
<first_book xmlns:user="urn:books">Book1</first_book>  
```  
  
 <span data-ttu-id="d34e3-131">위의 설명대로 `node-set` 함수를 사용하면 결과 트리 조각을 노드 집합으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-131">As stated above, the `node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="d34e3-132">이렇게 만들어지는 노드는 항상 트리의 루트 노드인 단일 노드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-132">The resulting node always contains a single node that is the root node of the tree.</span></span> <span data-ttu-id="d34e3-133">결과 트리 조각을 노드 집합으로 변환하면 해당 노드 집합을 for-each 문이나 `select` 특성 값 등 일반 노드 집합의 어디에서든 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-133">If you convert a result tree fragment to a node set, then you can use it anywhere a regular node set is used, such as in a for-each statement or in the value of a `select` attribute.</span></span> <span data-ttu-id="d34e3-134">다음 코드 줄에서는 노드 집합으로 변환되어 노드 집합으로 사용되는 조각을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-134">The following lines of code show the fragment being converted to a node set and used as a node set:</span></span>  
  
 `<xsl:for-each select="msxsl:node-set($node-fragment)">`  
  
 `<xsl:value-of select="user:func(msxsl:node-set($node-fragment))"/>`  
  
 <span data-ttu-id="d34e3-135">조각이 노드 집합으로 변환되면 더 이상 <xref:System.Xml.XPath.XPathNavigator>를 사용하여 노드 집합을 탐색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-135">When a fragment is converted to a node set, you no longer use the <xref:System.Xml.XPath.XPathNavigator> to navigate over it.</span></span> <span data-ttu-id="d34e3-136">노드 집합을 탐색하려면 <xref:System.Xml.XPath.XPathNodeIterator>를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-136">For a node set, you use the <xref:System.Xml.XPath.XPathNodeIterator> instead.</span></span>  
  
 <span data-ttu-id="d34e3-137">다음 예제에서 `$var`는 스타일시트의 노드 트리인 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-137">In the following example, `$var` is a variable that is a node tree in the style sheet.</span></span> <span data-ttu-id="d34e3-138">for-each 문과 `node-set` 함수를 함께 사용하면 이러한 노드 트리를 노드 집합으로 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-138">The for-each statement, combined with the `node-set` function, allows the user to iterate over this tree as a node set.</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.adventure-works.com"  
                version="1.0">  
    <xsl:variable name="states">  
        <node1>AL</node1>  
        <node1>CA</node1>  
        <node1>CO</node1>  
        <node1>WA</node1>  
    </xsl:variable>  
  
    <xsl:template match="/">  
            <xsl:for-each select="msxsl:node-set($states)"/>   
    </xsl:template>  
</xsl:stylesheet>  
```  
  
 <span data-ttu-id="d34e3-139">다음은 RTF, 즉 XPathNodeIterator로 스크립트 함수에 전달되기 전에 노드 집합으로 변환되는 결과 트리 조각 형식의 변수를 보여 주는 또 다른 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-139">Here is another example of a variable that is in RTF, and hence of type result tree fragment, that is converted to a node set before being passed to a script function as XPathNodeIterator.</span></span>  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
        xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
        xmlns:user="urn:books"  
        exclude-result-prefixes="msxsl">  
  
<xsl:output method="xml" indent="yes" omit-xml-declaration="yes"/>  
  
<xsl:variable name="node-fragment">  
    <book>Book1</book>  
    <book>Book2</book>  
    <book>Book3</book>  
    <book>Book4</book>  
</xsl:variable>  
  
<msxsl:script implements-prefix="user" language="c#">  
  
<![CDATA[  
    string func(XPathNodeIterator it)  
    {  
        it.MoveNext();   
        return it.Current.Value;   
        //it.Current returns XPathNavigator positioned on the current node  
    }  
  
]]>  
  
</msxsl:script>  
<xsl:template match="/">  
    <books>  
        <xsl:value-of select="user:func(msxsl:node-set($node-fragment))"/>  
    </books>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
 <span data-ttu-id="d34e3-140">다음은 이 스타일시트를 사용하여 XML을 변형한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="d34e3-140">The following is the result of transforming XML with this style sheet:</span></span>  
  
```xml  
<books xmlns:user="urn:books">Book1Book2Book3Book4</books>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d34e3-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d34e3-141">See Also</span></span>  
 <xref:System.Xml.XPath.XPathNodeIterator>  
 <xref:System.Xml.XPath.XPathNodeIterator>  
 [<span data-ttu-id="d34e3-142">XslTransform 클래스와 함께 XSLT 변환</span><span class="sxs-lookup"><span data-stu-id="d34e3-142">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 [<span data-ttu-id="d34e3-143">XslTransform 클래스의 XSLT 프로세서 구현</span><span class="sxs-lookup"><span data-stu-id="d34e3-143">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
