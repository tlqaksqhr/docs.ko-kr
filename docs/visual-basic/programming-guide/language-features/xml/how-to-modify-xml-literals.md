---
title: "방법: XML 리터럴 수정 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9c21ded9fdd8f49b469b9a712be304c0d4cabb8c
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="b06a6-102">방법: XML 리터럴 수정(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b06a6-102">How to: Modify XML Literals (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="b06a6-103">XML 리터럴 수정 하는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-103"> provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="b06a6-104">추가 하거나 요소 및 특성을 삭제할 수 있으며 기존 요소를 새 XML 요소로 바꿀 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="b06a6-105">이 항목에서는 기존 XML 리터럴 수정 하는 방법의 몇 가지 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-105">This topic provides several examples of how to modify an existing XML literal.</span></span>  
  
### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="b06a6-106">XML 리터럴 값을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="b06a6-106">To modify the value of an XML literal</span></span>  
  
1.  <span data-ttu-id="b06a6-107">XML 리터럴의 값을 수정 하려면 XML 리터럴 및 설정에 대 한 참조를 가져올는 `Value` 속성을 원하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>  
  
     <span data-ttu-id="b06a6-108">다음 코드 예제에서는 모든 값이 업데이트는 \<가격 > XML 문서의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>  
  
     <span data-ttu-id="b06a6-109">[!code-vb[VbXmlSamples&#2;&4;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b06a6-109">[!code-vb[VbXmlSamples2#4](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]</span></span>  
  
     <span data-ttu-id="b06a6-110">다음은 샘플 소스 XML 및이 코드 예제에서 XML을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-110">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>47.20</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>48.25</Price>  
      </Book>  
    </Catalog>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="b06a6-111">`Value` 속성은 컬렉션의 첫 번째 XML 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-111">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="b06a6-112">컬렉션에 같은 이름을 가진 요소가 둘 이상 있으면 설정 된 `Value` 속성 컬렉션의 첫 번째 요소에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-112">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>  
  
### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="b06a6-113">XML 리터럴에서 특성을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="b06a6-113">To add an attribute to an XML literal</span></span>  
  
1.  <span data-ttu-id="b06a6-114">XML 리터럴 특성을 추가 하려면 먼저 리터럴 XML에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-114">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="b06a6-115">그런 다음 새 XML 특성 축 속성을 추가 하 여 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-115">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="b06a6-116">추가할 수도 있습니다 새 <xref:System.Xml.Linq.XAttribute>개체를 사용 하 여 리터럴 XML의 <xref:System.Xml.Linq.XContainer.Add%2A>메서드.</xref:System.Xml.Linq.XContainer.Add%2A> </xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="b06a6-116">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="b06a6-117">다음 예제에서는 두 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-117">The following example shows both options.</span></span>  
  
     <span data-ttu-id="b06a6-118">[!code-vb[VbXmlSamples&#2;&5;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b06a6-118">[!code-vb[VbXmlSamples2#5](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]</span></span>  
  
     <span data-ttu-id="b06a6-119">다음은 샘플 소스 XML 및이 코드 예제에서 XML을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-119">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
    ```  
  
     <span data-ttu-id="b06a6-120">XML 특성 축 속성에 대 한 자세한 내용은 참조 [XML 특성 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-120">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>  
  
### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="b06a6-121">XML 리터럴에서 요소를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="b06a6-121">To add an element to an XML literal</span></span>  
  
1.  <span data-ttu-id="b06a6-122">리터럴 xml 요소를 추가 하려면 먼저 리터럴 XML에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-122">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="b06a6-123">추가할 수 있습니다 새 <xref:System.Xml.Linq.XElement>개체를 사용 하 여 요소의 마지막 하위 요소로 <xref:System.Xml.Linq.XContainer.Add%2A>메서드.</xref:System.Xml.Linq.XContainer.Add%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b06a6-123">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="b06a6-124">새 추가할 수 있습니다 <xref:System.Xml.Linq.XElement>개체를 사용 하 여 첫 번째 하위 요소로 <xref:System.Xml.Linq.XContainer.AddFirst%2A>메서드.</xref:System.Xml.Linq.XContainer.AddFirst%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b06a6-124">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>  
  
     <span data-ttu-id="b06a6-125">다른 하위 요소를 기준으로 특정 위치에 새 요소를 추가 하려면 먼저 인접 하위 요소에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-125">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="b06a6-126">추가할 수 있습니다 새 <xref:System.Xml.Linq.XElement>개체를 사용 하 여 인접 한 하위 요소 앞의 <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>메서드.</xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b06a6-126">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="b06a6-127">추가할 수도 있습니다 새 <xref:System.Xml.Linq.XElement>인접 한 하위 요소를 사용 하 여 다음 개체는 <xref:System.Xml.Linq.XNode.AddAfterSelf%2A>메서드.</xref:System.Xml.Linq.XNode.AddAfterSelf%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b06a6-127">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>  
  
     <span data-ttu-id="b06a6-128">다음 예제에서는 이러한 기술을 각각의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-128">The following example shows examples of each of these techniques.</span></span>  
  
     <span data-ttu-id="b06a6-129">[!code-vb[VbXmlSamples&#2;&6;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b06a6-129">[!code-vb[VbXmlSamples2#6](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]</span></span>  
  
     <span data-ttu-id="b06a6-130">다음은 샘플 소스 XML 및이 코드 예제에서 XML을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-130">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331">  
        <Publisher>Microsoft Press</Publisher>  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
        <PublishDate>2005-2-14</PublishDate>  
      </Book>  
      <Book id="bk999"></Book>  
    </Catalog>  
    ```  
  
### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="b06a6-131">XML 리터럴에서 요소 또는 특성을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="b06a6-131">To remove an element or attribute from an XML literal</span></span>  
  
1.  <span data-ttu-id="b06a6-132">XML 리터럴에서 요소 또는 특성을 제거 하 고 요소 또는 특성 호출에 대 한 참조를 가져올는 `Remove` 메서드를 다음 예와에서 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-132">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>  
  
     <span data-ttu-id="b06a6-133">[!code-vb[VbXmlSamples&#2;&7;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="b06a6-133">[!code-vb[VbXmlSamples2#7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]</span></span>  
  
     <span data-ttu-id="b06a6-134">다음은 샘플 소스 XML 및이 코드 예제에서 XML을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-134">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
      <Book id="bk999"></Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book></Catalog>  
    ```  
  
     <span data-ttu-id="b06a6-135">XML 리터럴에서 모든 요소 또는 특성을 제거 하려면 리터럴 XML에 대 한 참조 가져오기 및 호출 된 <xref:System.Xml.Linq.XElement.RemoveAll%2A>메서드.</xref:System.Xml.Linq.XElement.RemoveAll%2A></span><span class="sxs-lookup"><span data-stu-id="b06a6-135">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>  
  
### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="b06a6-136">XML 리터럴 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="b06a6-136">To modify an XML literal</span></span>  
  
1.  <span data-ttu-id="b06a6-137">XML 요소의 이름을 변경 하려면 먼저 요소에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-137">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="b06a6-138">만들 수 있습니다 새 <xref:System.Xml.Linq.XElement>새 이름을 지정 하 고 새 전달 된 개체 <xref:System.Xml.Linq.XElement>개체는 <xref:System.Xml.Linq.XNode.ReplaceWith%2A>기존 방식의 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XNode.ReplaceWith%2A> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b06a6-138">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     <span data-ttu-id="b06a6-139">대체 하는 요소를 유지 해야 하는 하위 요소가 있으면, 새 값을 설정 합니다. <xref:System.Xml.Linq.XElement>개체는 <xref:System.Xml.Linq.XContainer.Nodes%2A>기존 요소의 속성입니다.</xref:System.Xml.Linq.XContainer.Nodes%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b06a6-139">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="b06a6-140">기존 요소의 내부 XML을 새 요소의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-140">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="b06a6-141">새 요소의 값을 설정할 수는 그렇지 않은 경우는 `Value` 기존 요소의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-141">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>  
  
     <span data-ttu-id="b06a6-142">다음 코드 예제에서는 모든 대체 \<설명 > 요소는 \<추상 > 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-142">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="b06a6-143">콘텐츠는 \<설명 > 요소는 새 유지 됩니다 \<추상 > 요소를 사용 하 여는 <xref:System.Xml.Linq.XContainer.Nodes%2A>의 속성은 \<설명 > <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer.Nodes%2A></span><span class="sxs-lookup"><span data-stu-id="b06a6-143">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     <span data-ttu-id="b06a6-144">[!code-vb[VbXmlSamples&#2;&8;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="b06a6-144">[!code-vb[VbXmlSamples2#8](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]</span></span>  
  
     <span data-ttu-id="b06a6-145">다음은 샘플 소스 XML 및이 코드 예제에서 XML을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b06a6-145">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
        <Description>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Description>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
        <Description>  
          Get the expert insights, practical code samples, and best  
          practices you need to advance your expertise with   
          <technology>Visual Basic .NET</technology>.   
          Learn how to create faster, more reliable applications  
          based on professional, pragmatic guidance by today's top  
          <audience>developers</audience>.  
        </Description>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <MSRP>44.95</MSRP>    <Abstract>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Abstract>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <MSRP>45.95</MSRP>    <Abstract>  
          Get the expert insights, practical code samples, and best  
          practices you need to advance your expertise with   
          <technology>Visual Basic .NET</technology>.   
          Learn how to create faster, more reliable applications  
          based on professional, pragmatic guidance by today's top  
          <audience>developers</audience>.  
        </Abstract>  
      </Book>  
    </Catalog>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b06a6-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b06a6-146">See Also</span></span>  
 <span data-ttu-id="b06a6-147">[Visual Basic에서 XML 조작](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="b06a6-147">[Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md) </span></span>  
<span data-ttu-id="b06a6-148"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="b06a6-148"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="b06a6-149"> [방법: 파일, 문자열 또는 스트림에서 XML 로드](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md) </span><span class="sxs-lookup"><span data-stu-id="b06a6-149"> [How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md) </span></span>  
<span data-ttu-id="b06a6-150"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="b06a6-150"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="b06a6-151"> [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="b06a6-151"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
