---
title: "방법: LINQ to XML (Visual Basic)를 사용 하 여 사전 작업"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cb3f969-1986-414a-b850-87418712edea
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dc7290a3afca22ffc92914efacdb768a72e2aef7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-visual-basic"></a><span data-ttu-id="c7c95-102">방법: LINQ to XML (Visual Basic)를 사용 하 여 사전 작업</span><span class="sxs-lookup"><span data-stu-id="c7c95-102">How to: Work with Dictionaries Using LINQ to XML (Visual Basic)</span></span>
<span data-ttu-id="c7c95-103">다양한 데이터 구조를 XML로 변환하고 XML을 다시 다른 데이터 구조로 변환하는 것이 편리한 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="c7c95-103">It is often convenient to convert varieties of data structures to XML, and XML back to other data structures.</span></span> <span data-ttu-id="c7c95-104">이 항목에서는 <xref:System.Collections.Generic.Dictionary%602>를 XML로 변환하고 다시 그 반대로 변환하여 이 일반적인 방법을 구체적으로 구현하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7c95-104">This topic shows a specific implementation of this general approach by converting a <xref:System.Collections.Generic.Dictionary%602> to XML and back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7c95-105">예제</span><span class="sxs-lookup"><span data-stu-id="c7c95-105">Example</span></span>  
 <span data-ttu-id="c7c95-106">이 예제에서는 포함된 된 식에 XML 리터럴 및 쿼리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7c95-106">This example uses XML literals and a query in an embedded expression.</span></span> <span data-ttu-id="c7c95-107">쿼리는 새 <xref:System.Xml.Linq.XElement> 개체를 프로젝션하고 이 개체는 `Root` <xref:System.Xml.Linq.XElement> 개체의 새 내용이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7c95-107">The query projects new <xref:System.Xml.Linq.XElement> objects, which then become the new content for the `Root` <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```vb  
Dim dict As Dictionary(Of String, String) = New Dictionary(Of String, String)()  
dict.Add("Child1", "Value1")  
dict.Add("Child2", "Value2")  
dict.Add("Child3", "Value3")  
dict.Add("Child4", "Value4")  
Dim root As XElement = _  
    <Root>  
        <%= From keyValue In dict _  
            Select New XElement(keyValue.Key, keyValue.Value) %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="c7c95-108">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c7c95-108">This code produces the following output:</span></span>  
  
```xml  
          <Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="c7c95-109">예제</span><span class="sxs-lookup"><span data-stu-id="c7c95-109">Example</span></span>  
 <span data-ttu-id="c7c95-110">다음 코드에서는 XML에서 사전을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c7c95-110">The following code creates a dictionary from XML.</span></span>  
  
```vb  
Dim root As XElement = _  
        <Root>  
            <Child1>Value1</Child1>  
            <Child2>Value2</Child2>  
            <Child3>Value3</Child3>  
            <Child4>Value4</Child4>  
        </Root>  
  
Dim dict As Dictionary(Of String, String) = New Dictionary(Of String, String)  
For Each el As XElement In root.Elements  
    dict.Add(el.Name.LocalName, el.Value)  
Next  
For Each str As String In dict.Keys  
    Console.WriteLine("{0}:{1}", str, dict(str))  
Next  
```  
  
 <span data-ttu-id="c7c95-111">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c7c95-111">This code produces the following output:</span></span>  
  
```  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
  
## <a name="see-also"></a><span data-ttu-id="c7c95-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7c95-112">See Also</span></span>  
 [<span data-ttu-id="c7c95-113">프로젝션 및 변형 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7c95-113">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
