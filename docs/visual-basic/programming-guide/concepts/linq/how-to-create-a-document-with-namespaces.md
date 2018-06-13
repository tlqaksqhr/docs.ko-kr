---
title: '방법: 네임스페이스로 문서 만들기(LINQ to XML)(Visual Basic)'
ms.date: 07/20/2015
ms.assetid: cc5b0d4d-360c-4ada-94fa-2d2916e989be
ms.openlocfilehash: 204d8a9cbb6ce47c6334c7309d27910c75b90ae0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643080"
---
# <a name="how-to-create-a-document-with-namespaces-linq-to-xml-visual-basic"></a><span data-ttu-id="7bb5f-102">방법: 네임스페이스로 문서 만들기(LINQ to XML)(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7bb5f-102">How to: Create a Document with Namespaces (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="7bb5f-103">이 항목에서는 Visual Basic에서 네임스페이스를 사용하여 문서를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-103">This topic shows how to create a document with namespaces in Visual Basic.</span></span>  
  
 <span data-ttu-id="7bb5f-104">Visual Basic에서 XML 리터럴을 사용할 때 사용자는 하나의 전역 기본 XML 네임스페이스를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-104">When using XML literals in Visual Basic, users can define one global default XML namespace.</span></span> <span data-ttu-id="7bb5f-105">이 네임스페이스는 XML 리터럴과 XML 속성의 기본 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-105">This namespace is the default namespace for both XML literals and XML properties.</span></span> <span data-ttu-id="7bb5f-106">기본 XML 네임스페이스는 프로젝트 수준이나 파일 수준에서 정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-106">The default XML namespace can be defined at either the project level or the file level.</span></span> <span data-ttu-id="7bb5f-107">기본 XML 네임스페이스가 파일 수준에서 정의되면 프로젝트 수준의 기본 네임스페이스가 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-107">If it is defined at the file level, it overrides the default namespace at the project level.</span></span>  
  
 <span data-ttu-id="7bb5f-108">다른 네임스페이스를 정의하고 해당 네임스페이스의 네임스페이스 접두사를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-108">You can also define other namespaces, and specify the namespace prefixes for those namespaces.</span></span>  
  
 <span data-ttu-id="7bb5f-109">`Imports` 키워드를 사용하여 기본 네임스페이스와 접두사가 포함된 네임스페이스를 모두 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-109">You define both default namespaces and namespaces with a prefix by using the `Imports` keyword.</span></span>  
  
 <span data-ttu-id="7bb5f-110">자세한 내용은 참조 [Visual basic에서 XML 리터럴 소개](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-xml-literals.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-110">For more information, see [Introduction to XML Literals in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-xml-literals.md).</span></span>  
  
 <span data-ttu-id="7bb5f-111">기본 XML 네임스페이스는 요소에만 적용되고 특성에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-111">Note that the default XML namespace only applies to elements and not to attributes.</span></span> <span data-ttu-id="7bb5f-112">특성은 기본적으로 항상 네임스페이스에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-112">Attributes are by default always in no namespace.</span></span> <span data-ttu-id="7bb5f-113">그러나 네임스페이스 접두사를 사용하여 특성을 네임스페이스에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-113">However, you can use a namespace prefix to put an attribute in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bb5f-114">예제</span><span class="sxs-lookup"><span data-stu-id="7bb5f-114">Example</span></span>  
 <span data-ttu-id="7bb5f-115">이 예제에서는 네임스페이스가 포함된 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-115">This example creates a document that contains a namespace.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child aw:Att="attvalue"/>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="7bb5f-116">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-116">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child aw:Att="attvalue" />  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="7bb5f-117">예제</span><span class="sxs-lookup"><span data-stu-id="7bb5f-117">Example</span></span>  
 <span data-ttu-id="7bb5f-118">이 예제에서는 두 네임스페이스가 포함된 문서를 만듭니다. 두 네임스페이스 중 하나는 기본 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-118">This example creates a document that contains two namespaces, one of which is the default namespace.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child Att="attvalue"/>  
                <fc:Child2>child2 content</fc:Child2>  
            </Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="7bb5f-119">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-119">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns:fc="www.fourthcoffee.com" xmlns="http://www.adventure-works.com">  
  <Child Att="attvalue" />  
  <fc:Child2>child2 content</fc:Child2>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="7bb5f-120">예제</span><span class="sxs-lookup"><span data-stu-id="7bb5f-120">Example</span></span>  
 <span data-ttu-id="7bb5f-121">다음 예제에서는 네임스페이스 접두사가 포함된 여러 네임스페이스가 포함된 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-121">The following example creates a document that contains multiple namespaces, both with namespace prefixes.</span></span>  
  
 <span data-ttu-id="7bb5f-122">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서는 XML 트리를 serialize할 때 각 요소가 지정된 네임스페이스에 있도록 필요에 따라 네임스페이스 선언을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-122">When serializing an XML tree, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] emits namespace declarations as required so that each element is in its designated namespace.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="7bb5f-123">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb5f-123">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7bb5f-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bb5f-124">See Also</span></span>  
 [<span data-ttu-id="7bb5f-125">XML 네임 스페이스 (Visual Basic) 작업</span><span class="sxs-lookup"><span data-stu-id="7bb5f-125">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
