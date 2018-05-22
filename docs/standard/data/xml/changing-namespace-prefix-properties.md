---
title: 네임스페이스 접두사 속성 변경
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e3f41ba7281d67cc2ce848597926f5efebf4d489
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="changing-namespace-prefix-properties"></a><span data-ttu-id="b64a1-102">네임스페이스 접두사 속성 변경</span><span class="sxs-lookup"><span data-stu-id="b64a1-102">Changing Namespace Prefix Properties</span></span>
<span data-ttu-id="b64a1-103">**XmlNode** 클래스를 사용하면 지정된 노드와 연결된 네임스페이스 접두사를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b64a1-103">The **XmlNode** class allows you to change the namespace prefix associated with a given node.</span></span> <span data-ttu-id="b64a1-104">예를 들어, 다음 코드에서는 변경될 요소의 접두사를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b64a1-104">For example, the following code shows the prefix of an element being changed.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "b"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "b";  
Console.WriteLine(doc.InnerXml);  
```  
  
 <span data-ttu-id="b64a1-105">**출력**</span><span class="sxs-lookup"><span data-stu-id="b64a1-105">**Output**</span></span>  
  
```xml  
<b:test xmlns:a="123" xmlns:b="456" />  
```  
  
 <span data-ttu-id="b64a1-106">노드의 접두사를 변경해도 해당 네임스페이스는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b64a1-106">Changing the prefix of a node does not change its namespace.</span></span> <span data-ttu-id="b64a1-107">네임스페이스는 노드를 만들 때만 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b64a1-107">The namespace can only be set when the node is created.</span></span> <span data-ttu-id="b64a1-108">트리를 유지하는 경우 설정된 접두사에 맞게 새 네임스페이스 특성이 계속 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b64a1-108">When you persist the tree, new namespace attributes may be persisted out to satisfy the prefix you set.</span></span> <span data-ttu-id="b64a1-109">새 네임스페이스를 만들 수 없으면 노드가 해당 로컬 이름 및 네임스페이스를 유지하도록 접두사가 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="b64a1-109">If the new namespace cannot be created, then the prefix is changed so the node preserves its local name and namespace.</span></span> <span data-ttu-id="b64a1-110">다음 예제에서는 추가될 네임스페이스 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b64a1-110">The following example shows a namespace attribute being added.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<test xmlns='123'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "a"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<test xmlns='123'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "a";  
Console.WriteLine(doc.InnerXml);  
```  
  
 <span data-ttu-id="b64a1-111">**출력**</span><span class="sxs-lookup"><span data-stu-id="b64a1-111">**Output**</span></span>  
  
```xml  
<a:test xmlns="123" xmlns:a="123" />  
```  
  
 <span data-ttu-id="b64a1-112">**doc.InnerXml**을 호출한 결과로 트리가 문자열에 유지된 경우에는 `test` 요소의 네임스페이스를 유지하기 위해 `xmlns:a='123'` 특성이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b64a1-112">When the tree was persisted to a string as a result of the call to **doc.InnerXml**, the `xmlns:a='123'` attribute was added to preserve the namespace of the `test` element.</span></span> <span data-ttu-id="b64a1-113">원래 `'123'`이었으며 `'123'`을 유지했습니다.</span><span class="sxs-lookup"><span data-stu-id="b64a1-113">It was `'123'`, and it remained `'123'`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b64a1-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b64a1-114">See Also</span></span>  
 [<span data-ttu-id="b64a1-115">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="b64a1-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
