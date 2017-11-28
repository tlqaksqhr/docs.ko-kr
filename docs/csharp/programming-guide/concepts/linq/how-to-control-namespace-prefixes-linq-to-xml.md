---
title: "방법: 네임스페이스 접두사 제어(C#)(LINQ to XML)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 64de5186-b81a-4ddd-8327-8693df59a01b
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fc8d652c54be62fdf38e0aa05fcf6a81af3f719b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-control-namespace-prefixes-c-linq-to-xml"></a><span data-ttu-id="533af-102">방법: 네임스페이스 접두사 제어(C#)(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="533af-102">How to: Control Namespace Prefixes (C#) (LINQ to XML)</span></span>
<span data-ttu-id="533af-103">이 항목에서는 XML 트리를 serialize할 때 네임스페이스 접두사를 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="533af-103">This topic describes how you can control namespace prefixes when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="533af-104">대부분의 경우에는 네임스페이스 접두사를 제어할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="533af-104">In many situations, it is not necessary to control namespace prefixes.</span></span>  
  
 <span data-ttu-id="533af-105">그러나 일부 XML 프로그래밍 도구를 사용할 때는 네임스페이스 접두사를 특수하게 제어해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="533af-105">However, certain XML programming tools require specific control of namespace prefixes.</span></span> <span data-ttu-id="533af-106">예를 들어, 특정 네임스페이스 접두사를 참조하는 포함된 XPath 식이 들어 있는 XSLT 스타일시트나 XAML 문서를 조작할 수 있습니다. 이 경우 해당 문서가 특정 접두사를 사용하여 serialize되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="533af-106">For example, you might be manipulating an XSLT style sheet or a XAML document that contains embedded XPath expressions that refer to specific namespace prefixes; in this case, it is important that the document be serialized with those specific prefixes.</span></span>  
  
 <span data-ttu-id="533af-107">이는 네임스페이스 접두사를 제어해야 하는 가장 일반적인 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="533af-107">This is the most common reason for controlling namespace prefixes.</span></span>  
  
 <span data-ttu-id="533af-108">네임스페이스 접두사를 제어하는 또 다른 일반적인 경우는 사용자가 XML 문서를 수동으로 편집하도록 하고 사용자가 입력하기 편한 네임스페이스 접두사를 만들려고 할 때입니다.</span><span class="sxs-lookup"><span data-stu-id="533af-108">Another common reason for controlling namespace prefixes is that you want users to edit the XML document manually, and you want to create namespace prefixes that are convenient for the user to type.</span></span> <span data-ttu-id="533af-109">예를 들어, XSD 문서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="533af-109">For example, you might be generating an XSD document.</span></span> <span data-ttu-id="533af-110">스키마 규칙에서는 스키마 네임스페이스의 접두사로 `xs` 또는 `xsd`를 사용하도록 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="533af-110">Conventions for schemas suggest that you use either `xs` or `xsd` as the prefix for the schema namespace.</span></span>  
  
 <span data-ttu-id="533af-111">네임스페이스 접두사를 제어하려면 네임스페이스를 선언하는 특성을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="533af-111">To control namespace prefixes, you insert attributes that declare namespaces.</span></span> <span data-ttu-id="533af-112">특정 접두사가 포함된 네임스페이스를 선언하는 경우 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서는 serialize할 때 네임스페이스 접두사를 고려하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="533af-112">If you declare the namespaces with specific prefixes, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will attempt to honor the namespace prefixes when serializing.</span></span>  
  
 <span data-ttu-id="533af-113">접두사가 포함된 네임스페이스를 선언하는 특성을 만들려면 특성 이름의 네임스페이스가 <xref:System.Xml.Linq.XNamespace.Xmlns%2A>이고 특성의 이름이 네임스페이스 접두사인 특성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="533af-113">To create an attribute that declares a namespace with a prefix, you create an attribute where the namespace of the name of the attribute is <xref:System.Xml.Linq.XNamespace.Xmlns%2A>, and the name of the attribute is the namespace prefix.</span></span> <span data-ttu-id="533af-114">특성 값은 네임스페이스의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="533af-114">The value of the attribute is the URI of the namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="533af-115">예제</span><span class="sxs-lookup"><span data-stu-id="533af-115">Example</span></span>  
 <span data-ttu-id="533af-116">이 예제에서는 두 네임스페이스를 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="533af-116">This example declares two namespaces.</span></span> <span data-ttu-id="533af-117">`http://www.adventure-works.com` 네임스페이스가 `aw` 접두사를 갖고 `www.fourthcoffee.com`네임스페이스가 `fc` 접두사를 갖도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="533af-117">It specifies that the `http://www.adventure-works.com` namespace has the prefix of `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="533af-118">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="533af-118">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="533af-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="533af-119">See Also</span></span>  
 [<span data-ttu-id="533af-120">XML 네임스페이스 작업(C#)</span><span class="sxs-lookup"><span data-stu-id="533af-120">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
