---
title: XML 데이터에 개체 계층 구조 매핑
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 450e350b-6a68-4634-a2a5-33f4dc33baf0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45f39701d409ba76e3c3f428f484b6fd5e538fbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="mapping-the-object-hierarchy-to-xml-data"></a>XML 데이터에 개체 계층 구조 매핑
메모리에 있는 XML 문서를 개념적으로 표현한 것이 트리입니다. 프로그래밍의 경우에는 트리 노드에 액세스하는 개체 계층 구조가 있습니다. 다음 예제에서는 XML 내용이 노드가 되는 방법을 보여 줍니다.  
  
 XML을 DOM(문서 개체 모델)으로 읽어오면 각 요소가 노드로 변환됩니다. 이러한 노드에는 노드 형식 및 값과 같은 해당 노드 자체에 대한 추가 메타데이터가 포함됩니다. 노드 형식은 자신의 개체이며, 수행할 수 있는 작업과 설정하거나 검색할 수 있는 속성을 결정합니다.  
  
 다음과 같은 단순한 XML을 가정합니다.  
  
 **입력**  
  
```xml  
<book>  
    <title>The Handmaid's Tale</title>  
</book>  
```  
  
 이러한 입력은 지정된 노드 형식 속성이 있는 다음 노드 트리로 메모리에 표현됩니다.  
  
 ![예제 노드 트리](../../../../docs/standard/data/xml/media/simple-xml.gif "Simple_XML")  
book 및 title 노드 트리 표현  
  
 `book` 요소는 **XmlElement** 개체가 되고, 다음 요소인 `title`도 **XmlElement** 개체가 되지만 요소 내용은 **XmlText** 개체가 됩니다. **XmlElement**의 메서드 및 속성은 **XmlText** 개체에서 사용할 수 있는 메서드 및 속성과 다릅니다. 노드 형식에 따라 수행할 수 있는 작업이 결정되기 때문에 XML 태그에서 어떤 노드 형식이 만들어지는지를 반드시 알아야 합니다.  
  
 다음 예제에서는 XML 데이터를 읽고 노드 형식에 따라 다양한 텍스트를 작성합니다. 다음 XML 데이터 파일(**items.xml**)을 입력으로 사용합니다.  
  
 **입력**  
  
```xml  
<?xml version="1.0"?>  
<!-- This is a sample XML document -->  
<!DOCTYPE Items [<!ENTITY number "123">]>  
<Items>  
  <Item>Test with an entity: &number;</Item>  
  <Item>test with a child element <more/> stuff</Item>  
  <Item>test with a CDATA section <![CDATA[<456>]]> def</Item>  
  <Item>Test with a char entity: A</Item>  
  <!-- Fourteen chars in this element.-->  
  <Item>1234567890ABCD</Item>  
</Items>  
```  
  
 다음 코드 예제에서는 **items.xml** 파일을 읽고 각 노드 형식에 대한 정보를 표시합니다.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
    Private Const filename As String = "items.xml"  
  
    Public Shared Sub Main()  
  
        Dim reader As XmlTextReader = Nothing  
  
        Try  
            ' Load the reader with the data file and   
            'ignore all white space nodes.   
            reader = New XmlTextReader(filename)  
            reader.WhitespaceHandling = WhitespaceHandling.None  
  
            ' Parse the file and display each of the nodes.  
            While reader.Read()  
                Select Case reader.NodeType  
                    Case XmlNodeType.Element  
                        Console.Write("<{0}>", reader.Name)  
                    Case XmlNodeType.Text  
                        Console.Write(reader.Value)  
                    Case XmlNodeType.CDATA  
                        Console.Write("<![CDATA[{0}]]>", reader.Value)  
                    Case XmlNodeType.ProcessingInstruction  
                        Console.Write("<?{0} {1}?>", reader.Name, reader.Value)  
                    Case XmlNodeType.Comment  
                        Console.Write("<!--{0}-->", reader.Value)  
                    Case XmlNodeType.XmlDeclaration  
                        Console.Write("<?xml version='1.0'?>")  
                    Case XmlNodeType.Document  
                    Case XmlNodeType.DocumentType  
                        Console.Write("<!DOCTYPE {0} [{1}]", reader.Name, reader.Value)  
                    Case XmlNodeType.EntityReference  
                        Console.Write(reader.Name)  
                    Case XmlNodeType.EndElement  
                        Console.Write("</{0}>", reader.Name)  
                End Select  
            End While  
  
        Finally  
            If Not (reader Is Nothing) Then  
                reader.Close()  
            End If  
        End Try  
    End Sub 'Main ' End class  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    private const String filename = "items.xml";  
  
    public static void Main()  
    {  
        XmlTextReader reader = null;  
  
        try  
        {  
            // Load the reader with the data file and ignore   
            // all white space nodes.  
            reader = new XmlTextReader(filename);  
            reader.WhitespaceHandling = WhitespaceHandling.None;  
  
            // Parse the file and display each of the nodes.  
            while (reader.Read())  
            {  
                switch (reader.NodeType)  
                {  
                    case XmlNodeType.Element:  
                        Console.Write("<{0}>", reader.Name);  
                        break;  
                    case XmlNodeType.Text:  
                        Console.Write(reader.Value);  
                        break;  
                    case XmlNodeType.CDATA:  
                        Console.Write("<![CDATA[{0}]]>", reader.Value);  
                        break;  
                    case XmlNodeType.ProcessingInstruction:  
                        Console.Write("<?{0} {1}?>", reader.Name, reader.Value);  
                        break;  
                    case XmlNodeType.Comment:  
                        Console.Write("<!--{0}-->", reader.Value);  
                        break;  
                    case XmlNodeType.XmlDeclaration:  
                        Console.Write("<?xml version='1.0'?>");  
                        break;  
                    case XmlNodeType.Document:  
                        break;  
                    case XmlNodeType.DocumentType:  
                        Console.Write("<!DOCTYPE {0} [{1}]", reader.Name, reader.Value);  
                        break;  
                    case XmlNodeType.EntityReference:  
                        Console.Write(reader.Name);  
                        break;  
                    case XmlNodeType.EndElement:  
                        Console.Write("</{0}>", reader.Name);  
                        break;  
                }  
            }  
        }  
  
        finally  
        {  
            if (reader != null)  
                reader.Close();  
        }  
    }  
} // End class  
```  
  
 예제의 출력은 데이터의 노드 형식 매핑을 보여 줍니다.  
  
 **출력**  
  
```xml  
<?xml version='1.0'?><!--This is a sample XML document --><!DOCTYPE Items [<!ENTITY number "123">]<Items><Item>Test with an entity: 123</Item><Item>test with a child element <more> stuff</Item><Item>test with a CDATA section <![CDATA[<456>]]> def</Item><Item>Test with a char entity: A</Item><--Fourteen chars in this element.--><Item>1234567890ABCD</Item></Items>  
```  
  
 한 번에 한 줄씩 입력하고 코드에서 생성된 출력을 사용하면 다음 표를 사용하여 출력 줄을 생성한 노드 테스트를 분석할 수 있어 어떤 XML 데이터가 어떤 노드 형식이 되는지 이해할 수 있습니다.  
  
|입력|출력|노드 형식 테스트|  
|-----------|------------|--------------------|  
|\<?xml version="1.0"?>|\<?xml version='1.0'?>|XmlNodeType.XmlDeclaration|  
|\<!-- This is a sample XML document -->|\<!--This is a sample XML document -->|XmlNodeType.Comment|  
|\<!DOCTYPE Items [\<!ENTITY number "123">]>|\<!DOCTYPE Items [\<!ENTITY number "123">]|XmlNodeType.DocumentType|  
|\<Items>|\<Items>|XmlNodeType.Element|  
|\<Item>|\<Item>|XmlNodeType.Element|  
|Test with an entity: &number;|Test with an entity: 123|XmlNodeType.Text|  
|\</Item>|\</Item>|XmlNodeType.EndElement|  
|\<Item>|\<Item>|XmNodeType.Element|  
|test with a child element|test with a child element|XmlNodeType.Text|  
|\<more>|\<more>|XmlNodeType.Element|  
|stuff|stuff|XmlNodeType.Text|  
|\</Item>|\</Item>|XmlNodeType.EndElement|  
|\<Item>|\<Item>|XmlNodeType.Element|  
|test with a CDATA section|test with a CDATA section|XmlTest.Text|  
|<![CDATA[\<456>]]\>|<![CDATA[\<456>]]\>|XmlTest.CDATA|  
|def|def|XmlNodeType.Text|  
|\</Item>|\</Item>|XmlNodeType.EndElement|  
|\<Item>|\<Item>|XmlNodeType.Element|  
|Test with a char entity: &\#65;|Test with a char entity: A|XmlNodeType.Text|  
|\</Item>|\</Item>|XmlNodeType.EndElement|  
|\<!-- Fourteen chars in this element.-->|\<--Fourteen chars in this element.-->|XmlNodeType.Comment|  
|\<Item>|\<Item>|XmlNodeType.Element|  
|1234567890ABCD|1234567890ABCD|XmlNodeType.Text|  
|\</Item>|\</Item>|XmlNodeType.EndElement|  
|\</Items>|\</Items>|XmlNodeType.EndElement|  
  
 노드 형식이 유효한 작업 종류와 설정하고 검색할 수 있는 속성 종류를 제어하기 때문에 지정되는 노드 형식을 알아야 합니다.  
  
 공백에 대한 노드 생성은 **PreserveWhitespace** 플래그에 의해 DOM으로 데이터가 로드될 때 제어됩니다. 자세한 내용은 [DOM을 로드할 경우 공백 문자 및 유효 공백 문자 처리](../../../../docs/standard/data/xml/white-space-and-significant-white-space-handling-when-loading-the-dom.md)를 참조하세요.  
  
 DOM에 새 노드를 추가하려면 [XML 문서에 노드 삽입](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md)을 참조하세요. DOM에서 노드를 제거하려면 [XML 문서에서 노드, 내용 및 값 제거](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md)를 참조하세요. DOM에서 노드 내용을 수정하려면 [XML 문서에서 노드, 내용 및 값 수정](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [XML DOM(문서 개체 모델)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
