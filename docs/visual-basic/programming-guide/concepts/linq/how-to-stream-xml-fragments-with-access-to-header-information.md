---
title: "방법: 헤더 정보 (Visual Basic)에 액세스할 수 있는 XML 조각 스트림 | Microsoft 문서"
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
ms.assetid: effd10df-87c4-4d7a-8a9a-1434d829dca5
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 2ec1d189daa5460d3b90ea8609ea74eefcd70b7f
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017

---
# <a name="how-to-stream-xml-fragments-with-access-to-header-information-visual-basic"></a><span data-ttu-id="a0b64-102">방법: 헤더 정보 (Visual Basic)에 액세스할 수 있는 XML 조각 스트리밍</span><span class="sxs-lookup"><span data-stu-id="a0b64-102">How to: Stream XML Fragments with Access to Header Information (Visual Basic)</span></span>
<span data-ttu-id="a0b64-103">예상할 수 없는 큰 크기의 XML 파일을 읽고 응용 프로그램의 메모리 사용 공간이 예상 가능하도록 응용 프로그램을 작성해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-103">Sometimes you have to read arbitrarily large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="a0b64-104">XML 트리를 큰 XML 파일로 채우려는 경우 파일 크기에 비례하여 메모리가 사용되므로 메모리 사용량이 지나치게 증가하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-104">If you attempt to populate an XML tree with a large XML file, your memory usage will be proportional to the size of the file—that is, excessive.</span></span> <span data-ttu-id="a0b64-105">따라서 스트리밍 기법을 대신 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-105">Therefore, you should use a streaming technique instead.</span></span>  
  
 <span data-ttu-id="a0b64-106"><xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> 를 사용 하 여 응용 프로그램을 작성 하는 한 가지 방법은</span><span class="sxs-lookup"><span data-stu-id="a0b64-106">One option is to write your application using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="a0b64-107">그러나 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]를 사용하여 XML 트리를 쿼리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-107">However, you might want to use [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] to query the XML tree.</span></span> <span data-ttu-id="a0b64-108">이 경우에는 사용자 지정 축 메서드를 직접 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-108">If this is the case, you can write your own custom axis method.</span></span> <span data-ttu-id="a0b64-109">자세한 내용은 참조 [하는 방법: LINQ to XML 축 메서드 (Visual Basic) 작성](../../../../visual-basic/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-109">For more information, see [How to: Write a LINQ to XML Axis Method (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md).</span></span>  
  
 <span data-ttu-id="a0b64-110">사용 하는 작은 메서드를 작성 자신의 축 메서드를 작성 하는 <xref:System.Xml.XmlReader>관심이 있는 노드 중 하나에 도달할 때까지 노드를 읽을 수 있습니다.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="a0b64-110">To write your own axis method, you write a small method that uses the <xref:System.Xml.XmlReader> to read nodes until it reaches one of the nodes in which you are interested.</span></span> <span data-ttu-id="a0b64-111">메서드를 호출 <xref:System.Xml.Linq.XNode.ReadFrom%2A>에서 읽는 <xref:System.Xml.XmlReader>XML 조각을 인스턴스화하 및.</xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XNode.ReadFrom%2A></span><span class="sxs-lookup"><span data-stu-id="a0b64-111">The method then calls <xref:System.Xml.Linq.XNode.ReadFrom%2A>, which reads from the <xref:System.Xml.XmlReader> and instantiates an XML fragment.</span></span> <span data-ttu-id="a0b64-112">그런 다음 사용자 지정 축 메서드에 대한 LINQ 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-112">You can then write LINQ queries on your custom axis method.</span></span>  
  
 <span data-ttu-id="a0b64-113">스트리밍 기법은 소스 문서를 한 번만 처리해야 하고 문서 순서의 요소를 처리할 수 있는 경우에 가장 효과적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-113">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="a0b64-114">특정 표준 쿼리 연산자와 같은 <xref:System.Linq.Enumerable.OrderBy%2A>, 자신의 소스를 반복, 모든 데이터를 수집, 정렬 및 다음 시퀀스의 첫 번째 항목을 최종적으로 생성 합니다.</xref:System.Linq.Enumerable.OrderBy%2A></span><span class="sxs-lookup"><span data-stu-id="a0b64-114">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="a0b64-115">첫 번째 항목을 생성하기 전에 소스를 유형화하는 쿼리 연산자를 사용하는 경우 작은 메모리 사용 공간이 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-115">Note that if you use a query operator that materializes its source before yielding the first item, you will not retain a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0b64-116">예제</span><span class="sxs-lookup"><span data-stu-id="a0b64-116">Example</span></span>  
 <span data-ttu-id="a0b64-117">좀 더 흥미로운 문제가 발생하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-117">Sometimes the problem gets just a little more interesting.</span></span> <span data-ttu-id="a0b64-118">다음 XML 문서에서 사용자 지정 축 메서드의 소비자는 각 항목을 소유하는 고객의 이름도 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-118">In the following XML document, the consumer of your custom axis method also has to know the name of the customer that each item belongs to.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Root>  
  <Customer>  
    <Name>A. Datum Corporation</Name>  
    <Item>  
      <Key>0001</Key>  
    </Item>  
    <Item>  
      <Key>0002</Key>  
    </Item>  
    <Item>  
      <Key>0003</Key>  
    </Item>  
    <Item>  
      <Key>0004</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Fabrikam, Inc.</Name>  
    <Item>  
      <Key>0005</Key>  
    </Item>  
    <Item>  
      <Key>0006</Key>  
    </Item>  
    <Item>  
      <Key>0007</Key>  
    </Item>  
    <Item>  
      <Key>0008</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Southridge Video</Name>  
    <Item>  
      <Key>0009</Key>  
    </Item>  
    <Item>  
      <Key>0010</Key>  
    </Item>  
  </Customer>  
</Root>  
```  
  
 <span data-ttu-id="a0b64-119">이 예제에서 사용하는 방법은 이 헤더 정보를 확인하고 저장한 다음 헤더 정보와 열거하고 있는 세부 정보를 모두 포함하는 작은 XML 트리를 빌드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-119">The approach that this example takes is to also watch for this header information, save the header information, and then build a small XML tree that contains both the header information and the detail that you are enumerating.</span></span> <span data-ttu-id="a0b64-120">축 메서드는 이 새로운 작은 XML 트리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-120">The axis method then yields this new, small XML tree.</span></span> <span data-ttu-id="a0b64-121">이 경우 쿼리는 세부 정보뿐만 아니라 헤더 정보에도 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-121">The query then has access to the header information as well as the detail information.</span></span>  
  
 <span data-ttu-id="a0b64-122">이 방법에서는 작은 메모리 공간이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-122">This approach has a small memory footprint.</span></span> <span data-ttu-id="a0b64-123">각 세부 XML 조각이 생성될 때 이전 조각에 대한 참조는 유지되지 않으며 가비지 수집에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-123">As each detail XML fragment is yielded, no references are kept to the previous fragment, and it is available for garbage collection.</span></span> <span data-ttu-id="a0b64-124">이 기법을 사용하면 힙에 수명이 짧은 개체가 많이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-124">Note that this technique creates many short lived objects on the heap.</span></span>  
  
 <span data-ttu-id="a0b64-125">다음 예제에서는 URI로 지정된 파일에서 XML 조각을 스트림하는 사용자 지정 축 메서드를 구현하고 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-125">The following example shows how to implement and use a custom axis method that streams XML fragments from the file specified by the URI.</span></span> <span data-ttu-id="a0b64-126">이 사용자 지정 축은 문서에 `Customer`, `Name` 및 `Item` 요소가 있고 이러한 요소가 위에 있는 `Source.xml` 문서의 경우와 마찬가지로 정렬되어 있다고 가정하고 작성된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-126">This custom axis is specifically written such that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the above `Source.xml` document.</span></span> <span data-ttu-id="a0b64-127">이것은 매우 단순화된 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-127">It is a simplistic implementation.</span></span> <span data-ttu-id="a0b64-128">더욱 강력한 구현은 잘못된 문서의 구문을 분석할 준비가 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-128">A more robust implementation would be prepared to parse an invalid document.</span></span>  
  
```vb  
Module Module1  
  
    Sub Main()  
        Dim xmlTree = <Root>  
                          <%=  
                              From el In New StreamCustomerItem("Source.xml")  
                              Let itemKey = CInt(el.<Key>.Value)  
                              Where itemKey >= 3 AndAlso itemKey <= 7  
                              Select <Item>  
                                         <Customer><%= el.Parent.<Name>.Value %></Customer>  
                                         <%= el.<Key> %>  
                                     </Item>  
                          %>  
                      </Root>  
  
        Console.WriteLine(xmlTree)  
    End Sub  
  
End Module  
  
Public Class StreamCustomerItem  
    Implements IEnumerable(Of XElement)  
  
    Private _uri As String  
  
    Public Sub New(ByVal uri As String)  
        _uri = uri  
    End Sub  
  
    Public Function GetEnumerator() As IEnumerator(Of XElement) Implements IEnumerable(Of XElement).GetEnumerator  
        Return New StreamCustomerItemEnumerator(_uri)  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator Implements IEnumerable.GetEnumerator  
        Return Me.GetEnumerator()  
    End Function  
End Class  
  
Public Class StreamCustomerItemEnumerator  
    Implements IEnumerator(Of XElement)  
  
    Private _current As XElement  
    Private _customerName As String  
    Private _reader As Xml.XmlReader  
    Private _uri As String  
  
    Public Sub New(ByVal uri As String)  
        _uri = uri  
        _reader = Xml.XmlReader.Create(_uri)  
        _reader.MoveToContent()  
    End Sub  
  
    Public ReadOnly Property Current As XElement Implements IEnumerator(Of XElement).Current  
        Get  
            Return _current  
        End Get  
    End Property  
  
    Public ReadOnly Property Current1 As Object Implements IEnumerator.Current  
        Get  
            Return Me.Current  
        End Get  
    End Property  
  
    Public Function MoveNext() As Boolean Implements IEnumerator.MoveNext  
        Dim item As XElement  
        Dim name As XElement  
  
        ' Parse the file, save header information when encountered, and return the  
        ' current Item XElement.  
  
        ' loop through Customer elements  
        While _reader.Read()  
            If _reader.NodeType = Xml.XmlNodeType.Element Then  
                Select Case _reader.Name  
                    Case "Customer"  
                        ' move to Name element  
                        While _reader.Read()  
  
                            If _reader.NodeType = Xml.XmlNodeType.Element AndAlso  
                                _reader.Name = "Name" Then  
  
                                name = TryCast(XElement.ReadFrom(_reader), XElement)  
                                _customerName = If(name IsNot Nothing, name.Value, "")  
                                Exit While  
                            End If  
  
                        End While  
                    Case "Item"  
                        item = TryCast(XElement.ReadFrom(_reader), XElement)  
                        Dim tempRoot = <Root>  
                                           <Name><%= _customerName %></Name>  
                                           <%= item %>  
                                       </Root>  
                        _current = item  
                        Return True  
                End Select  
            End If  
        End While  
  
        Return False  
    End Function  
  
    Public Sub Reset() Implements IEnumerator.Reset  
        _reader = Xml.XmlReader.Create(_uri)  
        _reader.MoveToContent()  
    End Sub  
  
#Region "IDisposable Support"  
    Private disposedValue As Boolean ' To detect redundant calls  
  
    ' IDisposable  
    Protected Overridable Sub Dispose(ByVal disposing As Boolean)  
        If Not Me.disposedValue Then  
            If disposing Then  
                _reader.Close()  
            End If  
        End If  
        Me.disposedValue = True  
    End Sub  
  
    Public Sub Dispose() Implements IDisposable.Dispose  
        Dispose(True)  
        GC.SuppressFinalize(Me)  
    End Sub  
#End Region  
  
End Class  
```  
  
 <span data-ttu-id="a0b64-129">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a0b64-129">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a0b64-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0b64-130">See Also</span></span>  
 [<span data-ttu-id="a0b64-131">고급 LINQ to XML 프로그래밍 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0b64-131">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)

