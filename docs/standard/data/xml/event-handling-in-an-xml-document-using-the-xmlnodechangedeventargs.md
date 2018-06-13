---
title: XmlNodeChangedEventArgs를 사용한 XML 문서의 이벤트 처리
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 0fe844e3-5b6f-4fe7-ad15-22459501738b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 00ed0437f51650cd335d528632f9f0cc14af6422
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569735"
---
# <a name="event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs"></a><span data-ttu-id="42b56-102">XmlNodeChangedEventArgs를 사용한 XML 문서의 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="42b56-102">Event Handling in an XML Document Using the XmlNodeChangedEventArgs</span></span>
<span data-ttu-id="42b56-103">**XmlNodeChangedEventArgs**는 이벤트 처리를 위해 **XmlDocument** 개체에 등록된 이벤트 처리기에 전달되는 인수를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="42b56-103">The **XmlNodeChangedEventArgs** encapsulates the arguments passed to the event handlers registered on the **XmlDocument** object for handling events.</span></span> <span data-ttu-id="42b56-104">다음 표에서는 이벤트와 해당 이벤트가 발생하는 시기에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="42b56-104">The events and a description of when they are fired is given in the following table.</span></span>  
  
|<span data-ttu-id="42b56-105">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="42b56-105">Event</span></span>|<span data-ttu-id="42b56-106">발생 시기</span><span class="sxs-lookup"><span data-stu-id="42b56-106">Fired</span></span>|  
|-----------|-----------|  
|<xref:System.Xml.XmlDocument.NodeInserting>|<span data-ttu-id="42b56-107">현재 문서에 속한 노드가 다른 노드에 삽입되기 직전</span><span class="sxs-lookup"><span data-stu-id="42b56-107">When a node belonging to the current document is about to be inserted into another node.</span></span>|  
|<xref:System.Xml.XmlDocument.NodeInserted>|<span data-ttu-id="42b56-108">현재 문서에 속한 노드가 다른 노드에 삽입된 후</span><span class="sxs-lookup"><span data-stu-id="42b56-108">When a node belonging to the current document has been inserted into another node.</span></span>|  
|<xref:System.Xml.XmlDocument.NodeRemoving>|<span data-ttu-id="42b56-109">이 문서에 속한 노드가 문서에서 제거되기 직전</span><span class="sxs-lookup"><span data-stu-id="42b56-109">When a node belonging to this document is about to be removed from the document.</span></span>|  
|<xref:System.Xml.XmlDocument.NodeRemoved>|<span data-ttu-id="42b56-110">이 문서에 속한 노드가 부모로부터 제거된 직후</span><span class="sxs-lookup"><span data-stu-id="42b56-110">When a node belonging to this document has been removed from its parent.</span></span>|  
|<xref:System.Xml.XmlDocument.NodeChanging>|<span data-ttu-id="42b56-111">노드 값이 변경되기 직전</span><span class="sxs-lookup"><span data-stu-id="42b56-111">When the value of a node is about to be changed.</span></span>|  
|<xref:System.Xml.XmlDocument.NodeChanged>|<span data-ttu-id="42b56-112">노드 값이 변경된 직후</span><span class="sxs-lookup"><span data-stu-id="42b56-112">When the value of a node has been changed.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="42b56-113">**XmlDataDocument** 메모리 사용이 **DataSet** 저장소를 사용하도록 완전히 최적화된 경우 기본 **DataSet**이 변경될 때 **XmlDataDocument**에서 위에 나열된 어떠한 이벤트도 발생시키지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42b56-113">If the **XmlDataDocument** memory usage is fully optimized to use **DataSet** storage, the **XmlDataDocument** might not raise any of the events listed above when changes are made to the underlying **DataSet**.</span></span> <span data-ttu-id="42b56-114">이러한 이벤트가 필요한 경우 전체 **XmlDocument**를 한 번 트래버스하여 메모리 사용이 완전히 최적화되지 않은 상태로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42b56-114">If you need these events, you must traverse the whole **XmlDocument** once to make the memory usage non-fully optimized.</span></span>  
  
 <span data-ttu-id="42b56-115">다음 코드 예제에서는 이벤트 처리기를 정의하는 방법과 이벤트에 이벤트 처리기를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42b56-115">The following code example shows how to define an event handler and how to add the event handler to an event.</span></span>  
  
```vb  
' Attach the event handler, NodeInsertedHandler, to the NodeInserted  
' event.  
Dim doc as XmlDocument = new XmlDocument()  
Dim XmlNodeChgEHdlr as XmlNodeChangedEventHandler = new XmlNodeChangedEventHandler(addressof MyNodeChangedEvent)   
AddHandler doc.NodeInserted, XmlNodeChgEHdlr   
  
Dim n as XmlNode = doc.CreateElement( "element" )  
Console.WriteLine( "Before Event Inserting" )   
  
' This is the point where the new node is being inserted in the tree,  
' and this is the point where the NodeInserted event is raised.  
doc.AppendChild( n )  
Console.WriteLine( "After Event Inserting" )   
  
' Define the event handler that handles the NodeInserted event.  
sub NodeInsertedHandler(src as Object, args as XmlNodeChangedEventArgs)  
    Console.WriteLine("Node " + args.Node.Name + " inserted!!")  
end sub  
```  
  
```csharp  
// Attach the event handler, NodeInsertedHandler, to the NodeInserted  
// event.  
XmlDocument doc = new XmlDocument();  
doc.NodeInserted += new XmlNodeChangedEventHandler(NodeInsertedHandler);  
XmlNode n = doc.CreateElement( "element" );  
Console.WriteLine( "Before Event Inserting" );  
  
// This is the point where the new node is being inserted in the tree,  
// and this is the point where the NodeInserted event is raised.  
doc.AppendChild( n );  
Console.WriteLine( "After Event Inserting" );   
  
// Define the event handler that handles the NodeInserted event.  
void NodeInsertedHandler(Object src, XmlNodeChangedEventArgs args)  
{  
    Console.WriteLine("Node " + args.Node.Name + " inserted!!");  
}  
```  
  
 <span data-ttu-id="42b56-116">일부 XML DOM(문서 개체 모델) 작업은 여러 이벤트가 발생될 수 있는 복합 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="42b56-116">Some XML Document Object Model (DOM) operations are compound operations that can result in multiple events being fired.</span></span> <span data-ttu-id="42b56-117">예를 들어 **AppendChild**는 추가되는 노드를 이전 부모에서 제거해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42b56-117">For example, **AppendChild** may also have to remove the node being appended from its previous parent.</span></span> <span data-ttu-id="42b56-118">이 경우 먼저 **NodeRemoved** 이벤트가 발생한 다음, **NodeInserted** 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="42b56-118">In this case, you see a **NodeRemoved** event fired first, followed by a **NodeInserted** event.</span></span> <span data-ttu-id="42b56-119">**InnerXml**을 설정하는 것과 같은 작업으로 여러 이벤트가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42b56-119">Operations like setting **InnerXml** could result in multiple events.</span></span>  
  
 <span data-ttu-id="42b56-120">다음 코드 예제에서는 이벤트 처리기를 만드는 방법과 **NodeInserted** 이벤트를 처리하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="42b56-120">The following code example shows the creation of the event handler and the handling of the **NodeInserted** event.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports Microsoft.VisualBasic  
  
Public Class Sample  
  
    Private Const filename As String = "books.xml"  
  
    Shared Sub Main()  
        Dim mySample As Sample = New Sample()  
        mySample.Run(filename)  
    End Sub  
  
    Public Sub Run(ByVal args As String)  
        ' Create and load the XML document.  
        Console.WriteLine("Loading file 0 ...", args)  
        Dim doc As XmlDocument = New XmlDocument()  
        doc.Load(args)  
  
        ' Create the event handlers.  
        Dim XmlNodeChgEHdlr As XmlNodeChangedEventHandler = New XmlNodeChangedEventHandler(AddressOf MyNodeChangedEvent)  
        Dim XmlNodeInsrtEHdlr As XmlNodeChangedEventHandler = New XmlNodeChangedEventHandler(AddressOf MyNodeInsertedEvent)  
        AddHandler doc.NodeChanged, XmlNodeChgEHdlr  
        AddHandler doc.NodeInserted, XmlNodeInsrtEHdlr  
  
        ' Change the book price.  
        doc.DocumentElement.LastChild.InnerText = "5.95"  
  
        ' Add a new element.  
        Dim newElem As XmlElement = doc.CreateElement("style")  
        newElem.InnerText = "hardcover"  
        doc.DocumentElement.AppendChild(newElem)  
  
        Console.WriteLine(Chr(13) + Chr(10) + "Display the modified XML...")  
        Console.WriteLine(doc.OuterXml)  
    End Sub  
  
    ' Handle the NodeChanged event.  
    Public Sub MyNodeChangedEvent(ByVal src As Object, ByVal args As XmlNodeChangedEventArgs)  
        Console.Write("Node Changed Event: <0> changed", args.Node.Name)  
        If Not (args.Node.Value Is Nothing) Then  
            Console.WriteLine(" with value  0", args.Node.Value)  
        Else  
            Console.WriteLine("")  
        End If  
    End Sub  
  
    ' Handle the NodeInserted event.  
    Public Sub MyNodeInsertedEvent(ByVal src As Object, ByVal args As XmlNodeChangedEventArgs)  
        Console.Write("Node Inserted Event: <0> inserted", args.Node.Name)  
        If Not (args.Node.Value Is Nothing) Then  
            Console.WriteLine(" with value 0", args.Node.Value)  
        Else  
            Console.WriteLine("")  
        End If  
    End Sub  
  
End Class        ' End class  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
  private const String filename = "books.xml";  
  
  public static void Main()  
  {  
     Sample mySample = new Sample();  
     mySample.Run(filename);  
  }  
  
  public void Run(String args)  
  {  
  
     // Create and load the XML document.  
     Console.WriteLine ("Loading file {0} ...", args);  
     XmlDocument doc = new XmlDocument();  
     doc.Load (args);  
  
     // Create the event handlers.  
     doc.NodeChanged += new XmlNodeChangedEventHandler(this.MyNodeChangedEvent);  
     doc.NodeInserted += new XmlNodeChangedEventHandler(this.MyNodeInsertedEvent);  
  
     // Change the book price.  
     doc.DocumentElement.LastChild.InnerText = "5.95";  
  
     // Add a new element.  
     XmlElement newElem = doc.CreateElement("style");  
     newElem.InnerText = "hardcover";  
     doc.DocumentElement.AppendChild(newElem);  
  
     Console.WriteLine("\r\nDisplay the modified XML...");  
     Console.WriteLine(doc.OuterXml);             
  
  }  
  
  // Handle the NodeChanged event.  
  public void MyNodeChangedEvent(Object src, XmlNodeChangedEventArgs args)  
  {  
     Console.Write("Node Changed Event: <{0}> changed", args.Node.Name);  
     if (args.Node.Value != null)  
     {  
        Console.WriteLine(" with value  {0}", args.Node.Value);  
     }  
     else  
       Console.WriteLine("");  
  }  
  
  // Handle the NodeInserted event.  
  public void MyNodeInsertedEvent(Object src, XmlNodeChangedEventArgs args)  
  {  
     Console.Write("Node Inserted Event: <{0}> inserted", args.Node.Name);  
     if (args.Node.Value != null)  
     {  
        Console.WriteLine(" with value {0}", args.Node.Value);  
     }  
     else  
        Console.WriteLine("");  
  }  
  
} // End class   
```  
  
 <span data-ttu-id="42b56-121">자세한 내용은 <xref:System.Xml.XmlNodeChangedEventArgs> 및 <xref:System.Xml.XmlNodeChangedEventHandler>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42b56-121">For more information, see <xref:System.Xml.XmlNodeChangedEventArgs> and <xref:System.Xml.XmlNodeChangedEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42b56-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42b56-122">See Also</span></span>  
 [<span data-ttu-id="42b56-123">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="42b56-123">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
