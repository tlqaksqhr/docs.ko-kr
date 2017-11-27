---
title: "방법: 개체 Serialize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 76b6006c34b29e17ea725a5f7d104c1b085b5edc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-serialize-an-object"></a><span data-ttu-id="d6277-102">방법: 개체 Serialize</span><span class="sxs-lookup"><span data-stu-id="d6277-102">How to: Serialize an Object</span></span>
<span data-ttu-id="d6277-103">개체를 serialize하려면 먼저 serialize될 개체를 만들고 해당 public 속성과 필드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6277-103">To serialize an object, first create the object that is to be serialized and set its public properties and fields.</span></span> <span data-ttu-id="d6277-104">이렇게 하려면 XML 스트림이 저장될 전송 형식을 스트림 또는 파일 중에서 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6277-104">To do this, you must determine the transport format in which the XML stream is to be stored, either as a stream or as a file.</span></span> <span data-ttu-id="d6277-105">예를 들어 XML 스트림을 영구적 형태로 저장해야 하는 경우에는 <xref:System.IO.FileStream> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6277-105">For example, if the XML stream must be saved in a permanent form, create a <xref:System.IO.FileStream> object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6277-106">XML serialization에 대한 다른 예제를 보려면 [XML Serialization 예제](../../../docs/standard/serialization/examples-of-xml-serialization.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6277-106">For more examples of XML serialization, see [Examples of XML Serialization](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object"></a><span data-ttu-id="d6277-107">개체를 serialize하려면</span><span class="sxs-lookup"><span data-stu-id="d6277-107">To serialize an object</span></span>  
  
1.  <span data-ttu-id="d6277-108">개체를 만들고 해당 public 필드 및 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6277-108">Create the object and set its public fields and properties.</span></span>  
  
2.  <span data-ttu-id="d6277-109">개체의 형식을 사용하여 <xref:System.Xml.Serialization.XmlSerializer>를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6277-109">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object.</span></span> <span data-ttu-id="d6277-110">자세한 내용은 <xref:System.Xml.Serialization.XmlSerializer> 클래스 생성자를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6277-110">For more information, see the <xref:System.Xml.Serialization.XmlSerializer> class constructors.</span></span>  
  
3.  <span data-ttu-id="d6277-111"><xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> 메서드를 호출하여 개체의 public 속성 및 필드의 파일 표현 또는 XML 스트림을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6277-111">Call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> method to generate either an XML stream or a file representation of the object's public properties and fields.</span></span> <span data-ttu-id="d6277-112">다음 예제에서는 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6277-112">The following example creates a file.</span></span>  
  
    ```vb  
    Dim myObject As MySerializableClass = New MySerializableClass()  
    ' Insert code to set properties and fields of the object.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To write to a file, create a StreamWriter object.  
    Dim myWriter As StreamWriter = New StreamWriter("myFileName.xml")  
    mySerializer.Serialize(myWriter, myObject)  
    myWriter.Close()  
    ```  
  
    ```csharp  
    MySerializableClass myObject = new MySerializableClass();  
    // Insert code to set properties and fields of the object.  
    XmlSerializer mySerializer = new   
    XmlSerializer(typeof(MySerializableClass));  
    // To write to a file, create a StreamWriter object.  
    StreamWriter myWriter = new StreamWriter("myFileName.xml");  
    mySerializer.Serialize(myWriter, myObject);  
    myWriter.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d6277-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6277-113">See Also</span></span>  
 [<span data-ttu-id="d6277-114">XML serialization 소개</span><span class="sxs-lookup"><span data-stu-id="d6277-114">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="d6277-115">방법: 개체 deserialize</span><span class="sxs-lookup"><span data-stu-id="d6277-115">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
