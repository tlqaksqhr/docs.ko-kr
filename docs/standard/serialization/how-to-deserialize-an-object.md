---
title: "방법: 개체 Deserialize"
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
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b28d80951cb2d71f8f8fb532710f738fecdf8508
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-deserialize-an-object"></a>방법: 개체 Deserialize
개체를 deserialize할 때는 전송 형식에 따라 스트림을 만들지 파일 개체를 만들지 여부가 결정됩니다. 전송 형식이 결정된 뒤에는 필요에 따라 <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> 또는 <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> 메서드를 호출할 수 있습니다.  
  
### <a name="to-deserialize-an-object"></a>개체를 deserialize하려면  
  
1.  deserialize할 개체의 형식을 사용하여 <xref:System.Xml.Serialization.XmlSerializer>를 생성합니다.  
  
2.  개체의 복제본을 생성할 <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A> 메서드를 호출합니다. deserialize할 때는 개체를 파일로 deserialize하는(스트림으로 deserialize할 수도 있음) 다음 예제처럼, 반환된 개체를 원래의 형식으로 캐스팅해야 합니다.  
  
    ```vb  
    Dim myObject As MySerializableClass  
    ' Construct an instance of the XmlSerializer with the type  
    ' of object that is being deserialized.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To read the file, create a FileStream.  
    Dim myFileStream As FileStream = _  
    New FileStream("myFileName.xml", FileMode.Open)  
    ' Call the Deserialize method and cast to the object type.  
    myObject = CType( _  
    mySerializer.Deserialize(myFileStream), MySerializableClass)  
    ```  
  
    ```csharp  
    MySerializableClass myObject;  
    // Construct an instance of the XmlSerializer with the type  
    // of object that is being deserialized.  
    XmlSerializer mySerializer =   
    new XmlSerializer(typeof(MySerializableClass));  
    // To read the file, create a FileStream.  
    FileStream myFileStream =   
    new FileStream("myFileName.xml", FileMode.Open);  
    // Call the Deserialize method and cast to the object type.  
    myObject = (MySerializableClass)   
    mySerializer.Deserialize(myFileStream)  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [XML serialization 소개](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [방법: 개체 직렬화](../../../docs/standard/serialization/how-to-serialize-an-object.md)
