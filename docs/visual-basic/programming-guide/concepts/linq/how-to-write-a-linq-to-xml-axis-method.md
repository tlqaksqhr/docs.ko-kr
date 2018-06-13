---
title: '방법: LINQ to XML 축 메서드 (Visual Basic) 작성'
ms.date: 07/20/2015
ms.assetid: b676f025-a24c-4076-8713-aa809b2b8ce0
ms.openlocfilehash: b77be0d9b1f9f6c5dcfe7aed90b0e16b614f26aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33645670"
---
# <a name="how-to-write-a-linq-to-xml-axis-method-visual-basic"></a><span data-ttu-id="a33c7-102">방법: LINQ to XML 축 메서드 (Visual Basic) 작성</span><span class="sxs-lookup"><span data-stu-id="a33c7-102">How to: Write a LINQ to XML Axis Method (Visual Basic)</span></span>
<span data-ttu-id="a33c7-103">XML 트리에서 컬렉션을 검색하는 축 메서드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a33c7-103">You can write your own axis methods to retrieve collections from an XML tree.</span></span> <span data-ttu-id="a33c7-104">축 메서드를 작성하는 가장 좋은 방법 중 하나는 요소나 특성의 컬렉션을 반환하는 확장 메서드를 작성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a33c7-104">One of the best ways to do this is to write an extension method that returns a collection of elements or attributes.</span></span> <span data-ttu-id="a33c7-105">응용 프로그램의 요구 사항에 따라 요소나 특성의 특정 하위 집합을 반환하는 확장명 메서드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a33c7-105">You can write your extension method to return specific subsets of elements or attributes, based on the requirements of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a33c7-106">예제</span><span class="sxs-lookup"><span data-stu-id="a33c7-106">Example</span></span>  
 <span data-ttu-id="a33c7-107">다음 예제에서는 두 가지 확장명 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a33c7-107">The following example uses two extension methods.</span></span> <span data-ttu-id="a33c7-108">첫 번째 확장 메서드인 `GetXPath`는 <xref:System.Xml.Linq.XObject>에 대해 작동하며 계산될 때 노드나 특성을 반환할 XPath 식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a33c7-108">The first extension method, `GetXPath`, operates on <xref:System.Xml.Linq.XObject>, and returns an XPath expression that when evaluated will return the node or attribute.</span></span> <span data-ttu-id="a33c7-109">두 번째 확장 메서드인 `Find`는 <xref:System.Xml.Linq.XElement>에 대해 작동하며</span><span class="sxs-lookup"><span data-stu-id="a33c7-109">The second extension method, `Find`, operates on <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="a33c7-110">지정된 일부 텍스트가 포함된 <xref:System.Xml.Linq.XAttribute> 개체와 <xref:System.Xml.Linq.XElement> 개체의 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a33c7-110">It returns a collection of <xref:System.Xml.Linq.XAttribute> objects and <xref:System.Xml.Linq.XElement> objects that contain some specified text.</span></span>  
  
 <span data-ttu-id="a33c7-111">이 예제에서는 XML 문서 [샘플 XML 파일: 여러 구매 주문(LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a33c7-111">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
Imports System.Text  
  
Module Module1  
    Sub Main()  
        Dim purchaseOrders = XElement.Load("..\..\PurchaseOrders.xml")  
  
        Dim subset = From xobj In purchaseOrders.Find("1999")  
  
        For Each obj In subset  
            Console.WriteLine(obj.GetXPath())  
            If obj.GetType() = GetType(XElement) Then  
                Console.WriteLine(CType(obj, XElement).Value)  
            ElseIf obj.GetType() = GetType(XAttribute) Then  
                Console.WriteLine(CType(obj, XAttribute).Value)  
            End If  
        Next  
    End Sub  
End Module  
  
Public Module MyExtensions  
  
    Private Function GetQName(ByVal xe As XElement) As String  
        Dim prefix = xe.GetPrefixOfNamespace(xe.Name.Namespace)  
        If xe.Name.Namespace = XNamespace.None OrElse prefix Is Nothing Then  
            Return xe.Name.LocalName  
        Else  
            Return prefix & ":" & xe.Name.LocalName  
        End If  
    End Function  
  
    Private Function GetQName(ByVal xa As XAttribute) As String  
        Dim prefix = xa.Parent.GetPrefixOfNamespace(xa.Name.Namespace)  
        If xa.Name.Namespace = XNamespace.None OrElse prefix Is Nothing Then  
            Return xa.Name.LocalName  
        Else  
            Return prefix & ":" & xa.Name.LocalName  
        End If  
    End Function  
  
    Private Function NameWithPredicate(ByVal el As XElement) As String  
        If el.Parent IsNot Nothing AndAlso  
           el.Parent.Elements(el.Name).Count() <> 1 Then  
            Return GetQName(el) & "[" &  
                (el.ElementsBeforeSelf(el.Name).Count() + 1) & "]"  
        Else  
            Return GetQName(el)  
        End If  
    End Function  
  
    <Extension()>  
    Public Function StrCat(Of T)(ByVal source As IEnumerable(Of T),  
                                 ByVal separator As String) As String  
        Return source.Aggregate(New StringBuilder,  
                                Function(sb, i) sb.  
                                    Append(i.ToString()).  
                                    Append(separator),  
                                    Function(s) s.ToString())  
    End Function  
  
    <Extension()>  
    Public Function GetXPath(ByVal xobj As XObject) As String  
  
        If xobj.Parent Is Nothing Then  
            Dim doc = TryCast(xobj, XDocument)  
            If doc IsNot Nothing Then Return "."  
  
            Dim el = TryCast(xobj, XElement)  
            If el IsNot Nothing Then Return "/" + NameWithPredicate(el)  
  
            ' the XPath data model does not include white space text nodes  
            ' that are children of a document, so this method returns null.  
  
            Dim xt = TryCast(xobj, XText)  
            If xt IsNot Nothing Then Return Nothing  
  
            Dim com = TryCast(xobj, XComment)  
            If com IsNot Nothing Then  
                Return "/" &  
                    If(com.Document.Nodes().OfType(Of XComment)().Count() <> 1,  
                       "comment()[" & (com.NodesBeforeSelf().OfType(Of XComment)().Count() + 1) & "]",  
                       "comment()")  
            End If  
  
            Dim pi = TryCast(xobj, XProcessingInstruction)  
            If pi IsNot Nothing Then  
                Return "/" &  
                    If(pi.Document.Nodes().OfType(Of XProcessingInstruction)().Count() <> 1,  
                       "processing-instruction()[" &  
                           (pi.NodesBeforeSelf().OfType(Of XProcessingInstruction)().Count() + 1) & "]",  
                       "processing-instruction()")  
            End If  
            Return Nothing  
        Else  
            Dim el = TryCast(xobj, XElement)  
            If el IsNot Nothing Then  
                Return "/" &  
                    el.Ancestors().  
                    InDocumentOrder().  
                    Select(Function(e) NameWithPredicate(e)).StrCat("/") & NameWithPredicate(el)  
            End If  
            Dim at = TryCast(xobj, XAttribute)  
            If at IsNot Nothing Then  
                Return "/" &  
                    at.Parent.  
                    AncestorsAndSelf().  
                    InDocumentOrder().  
                    Select(Function(e) NameWithPredicate(e)).StrCat("/") & "@" & GetQName(at)  
            End If  
            Dim com = TryCast(xobj, XComment)  
            If com IsNot Nothing Then  
                Return "/" &  
                    com.Parent.  
                    AncestorsAndSelf().  
                    InDocumentOrder().  
                    Select(Function(e) NameWithPredicate(e)).StrCat("/") &  
                        If(com.Parent.Nodes().OfType(Of XComment)().Count() <> 1,  
                           "comment()[" & (com.NodesBeforeSelf().OfType(Of XComment)().Count() + 1) & "]",  
                           "comment()")  
            End If  
  
            Dim cd = TryCast(xobj, XCData)  
            If cd IsNot Nothing Then  
                Return "/" &  
                    cd.Parent.  
                    AncestorsAndSelf().  
                    InDocumentOrder().  
                    Select(Function(e) NameWithPredicate(e)).StrCat("/") &  
                        If(cd.Parent.Nodes().OfType(Of XText)().Count() <> 1,  
                           "text()[" & (cd.NodesBeforeSelf().OfType(Of XText)().Count() + 1) & "]",  
                           "text()")  
            End If  
            Dim tx = TryCast(xobj, XText)  
            If tx IsNot Nothing Then  
                Return "/" &  
                    tx.Parent.  
                    AncestorsAndSelf().  
                    InDocumentOrder().  
                    Select(Function(e) NameWithPredicate(e)).StrCat("/") &  
                        If(tx.Parent.Nodes().OfType(Of XText)().Count() <> 1,  
                           "text()[" & (tx.NodesBeforeSelf().OfType(Of XText)().Count() + 1) & "]",  
                           "text()")  
            End If  
            Dim pi As XProcessingInstruction = TryCast(xobj, XProcessingInstruction)  
            If pi IsNot Nothing Then  
                Return "/" &  
                    pi.Parent.  
                    AncestorsAndSelf().  
                    InDocumentOrder().  
                    Select(Function(e) NameWithPredicate(e)).StrCat("/") &  
                        If(pi.Parent.Nodes().OfType(Of XProcessingInstruction)().Count() <> 1,  
                           "processing-instruction()[" &  
                               (pi.NodesBeforeSelf().OfType(Of XProcessingInstruction)().Count() + 1) & "]",  
                           "processing-instruction()")  
            End If  
            Return Nothing  
        End If  
    End Function  
  
    <Extension()>  
    Public Function Find(ByVal source As XElement, ByVal value As String) As IEnumerable(Of XObject)  
        Dim results = From att In source.Attributes()  
                      Where att.Value.Contains(value)  
                      Let a As XObject = att  
                      Select a  
  
        If source.Elements().Any Then  
            For Each result In From child In source.Elements() Select Find(child, value)  
                results = If(results Is Nothing, result, results.Union(result))  
            Next  
        Else  
            If source.Value.Contains(value) Then  
                results = If(results Is Nothing,  
                             New List(Of XObject) From {source},  
                             results.Union(New List(Of XObject) From {source}))  
            End If  
        End If  
  
        Return results  
    End Function  
  
End Module  
```  
  
 <span data-ttu-id="a33c7-112">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a33c7-112">This code produces the following output:</span></span>  
  
```  
/PurchaseOrders/PurchaseOrder[1]/@OrderDate  
1999-10-20  
/PurchaseOrders/PurchaseOrder[1]/Items/Item[2]/ShipDate  
1999-05-21  
/PurchaseOrders/PurchaseOrder[2]/@OrderDate  
1999-10-22  
/PurchaseOrders/PurchaseOrder[3]/@OrderDate  
1999-10-22  
```  
  
## <a name="see-also"></a><span data-ttu-id="a33c7-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a33c7-113">See Also</span></span>  
 [<span data-ttu-id="a33c7-114">고급 쿼리 기술 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a33c7-114">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
