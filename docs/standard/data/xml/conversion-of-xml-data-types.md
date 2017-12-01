---
title: "XML 데이터 형식 변환"
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
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d2f5f5d27b3d21ff12f5eea7613e80e73c5b6597
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="conversion-of-xml-data-types"></a>XML 데이터 형식 변환
에 있는 대부분의 메서드는 **XmlConvert** 클래스는 문자열과 강력한 형식의 서식을 서로 변환 하는 데 사용 됩니다. 메서드는 로캘과 무관합니다. 즉, 변환을 수행하는 경우 메서드는 로캘 설정을 고려하지 않습니다.  
  
## <a name="reading-string-as-types"></a>문자열을 형식으로 읽기  
 다음 샘플에서는 문자열을 읽고으로 변환 하는 **DateTime** 유형입니다.  
  
 다음과 같은 XML 입력을 가정합니다.  
  
 **입력**  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 이 코드는 문자열을 변환의 **DateTime** 형식:  
  
```vb  
reader.ReadStartElement()  
Dim vDateTime As DateTime = XmlConvert.ToDateTime(reader.ReadString())  
Console.WriteLine(vDateTime)  
```  
  
```csharp  
reader.ReadStartElement();  
DateTime vDateTime = XmlConvert.ToDateTime(reader.ReadString());  
Console.WriteLine(vDateTime);  
```  
  
## <a name="writing-strings-as-types"></a>문자열을 형식으로 쓰기  
 다음 샘플 읽기는 **Int32** 를 문자열로 변환 합니다.  
  
 다음과 같은 XML 입력을 가정합니다.  
  
 **입력**  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 이 코드 변환는 **Int32** 에 **문자열**:  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a>참고 항목  
 [문자열을.NET Framework 데이터 형식으로 변환](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)  
 [.NET Framework 형식을 문자열로 변환](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
