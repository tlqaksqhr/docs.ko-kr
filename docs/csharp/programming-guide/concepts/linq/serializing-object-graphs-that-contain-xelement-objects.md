---
title: "XElement 개체를 포함하는 개체 그래프 serialize(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: fcbc3951-3cc4-4d0f-9259-e97549ed68f0
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8b7da4429360beb20fa304b592020d48666fe732
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="serializing-object-graphs-that-contain-xelement-objects-c"></a>XElement 개체를 포함하는 개체 그래프 serialize(C#)
이 항목에서는 <xref:System.Xml.Linq.XElement> 형식의 개체에 대한 참조가 포함된 개체 그래프를 serialize하는 기능에 대해 소개합니다. 이러한 유형의 serialize를 용이하게 수행하기 위해 <xref:System.Xml.Linq.XElement>는 <xref:System.Xml.Serialization.IXmlSerializable> 인터페이스를 구현합니다.  
  
 <xref:System.Xml.Linq.XElement> 클래스만 serialization을 구현합니다.  
  
## <a name="in-this-section"></a>단원 내용  
  
|항목|설명|  
|-----------|-----------------|  
|[방법: XmlSerializer를 사용하여 serialize(C#)](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<xref:System.Xml.Serialization.XmlSerializer>를 사용하여 serialize하는 방법을 보여 줍니다.|  
|[방법: DataContractSerializer를 사용하여 serialize(C#)](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<xref:System.Runtime.Serialization.DataContractSerializer>를 사용하여 serialize하는 방법을 보여 줍니다.|  
  
## <a name="see-also"></a>참고 항목  
 [고급 LINQ to XML 프로그래밍(C#)](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
