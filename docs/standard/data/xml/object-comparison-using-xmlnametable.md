---
title: "XmlNameTable을 사용한 개체 비교"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8d94e041-d340-4ddf-9a2c-d7319e3f4f86
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0cd1a3bad69499b4804299adecabad3a43b5eab1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="object-comparison-using-xmlnametable"></a>XmlNameTable을 사용한 개체 비교
**XmlDocuments**만들어지면 이름 표는 없지만 해당 문서를 생성 합니다. 특성 및 요소 이름이 넣을 XML 문서를 로드 하거나 새 요소 또는 특성이 만들어지면는 **XmlNameTable**합니다. 만들 수도 있습니다는 **XmlDocument** 기존 **NameTable** 다른 문서에서 합니다. 때 **XmlDocuments** 사용 하는 생성자를 사용 하 여 만들어진는 **XmlNameTable** 매개 변수를 문서에 노드 이름, 네임 스페이스 및 접두사에 이미 저장에 대 한 액세스는  **XmlNameTable**합니다. 이름 테이블에 이름이 로드되는 방법에 관계없이 테이블에 이름을 저장한 후에는 문자열 비교 대신 개체 비교를 통해 이름을 신속하게 비교할 수 있습니다. 문자열도 사용 하 여 이름 테이블에 추가할 수는 <xref:System.Xml.NameTable.Add%2A>합니다. 다음 코드 샘플은 이름 테이블을 만들고 및 문자열 **MyString** 테이블에 추가 되 고 있습니다. 그 이후에 **XmlDocument** 해당 테이블과에서 요소 및 특성 이름을 사용 하 여 만들어집니다 **Myfile.xml** 기존 이름 테이블에 추가 됩니다.  
  
```vb  
Dim nt As New NameTable()  
nt.Add("MyString")  
Dim doc As New XmlDocument(nt)  
doc.Load("Myfile.xml")  
```  
  
```csharp  
NameTable nt = new NameTable();  
nt.Add("MyString");  
XmlDocument doc = new XmlDocument(nt);  
doc.Load("Myfile.xml");  
```  
  
 다음 코드 예제에서는 문서를 만들고, 해당 문서에 새 요소 두 개를 추가하여 문서 이름 테이블에 추가하고, 이름에 대한 개체 비교를 수행하는 방법을 보여 줍니다.  
  
```vb  
Dim doc1 As XmlDocument = imp.CreateDocument()  
Dim node1 As XmlElement = doc.CreateElement("node1")  
Dim doc2 As XmlDocument = imp.CreateDocument()  
Dim node2 As XmlElement = doc.CreateElement("node2")  
if (CType(node1.Name, object) = CType(node2.Name, object))  
```  
  
```csharp  
XmlDocument doc1 = imp.CreateDocument();  
node1 = doc1.CreateElement ("node1");  
XmlDocument doc2 = imp.CreateDocument();  
node2 = doc2.CreateElement ("node1");  
if (((object)node1.Name) == ((object)node2.Name))  
{ ...  
```  
  
 두 문서 사이에서 이름 테이블이 전달되는 위의 시나리오는 주로 XSD(XML 스키마 정의 언어) 스키마나 DTD(문서 종류 정의)를 따르고 동일한 문자열이 반복되는 전자 상거래 사이트의 주문서와 같이 동일한 종류의 문서를 반복적으로 처리하는 경우에 해당합니다. 이 경우 동일한 이름 테이블을 사용하면 여러 문서에서 동일한 요소 이름이 나타나기 때문에 성능이 향상됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 개체 모델 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
