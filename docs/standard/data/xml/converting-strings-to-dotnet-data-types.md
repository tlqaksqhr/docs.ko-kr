---
title: "문자열을 .NET Framework 데이터 형식으로 변환"
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
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ce594234e601cd8feb4723bbc383db9e3ed40522
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="converting-strings-to-net-framework-data-types"></a>문자열을 .NET Framework 데이터 형식으로 변환
사용 하 여 문자열을.NET Framework 데이터 형식으로 변환 하려는 경우는 **XmlConvert** 응용 프로그램 요구 사항에 맞는 방법을 합니다. 사용 가능한 변환 메서드의 전체 목록은 **XmlConvert** 클래스를 참조 하십시오. <xref:System.Xml.XmlConvert>합니다.  
  
 반환 된 문자열의 **ToString** 방법은에 전달 되는 데이터의 문자열 버전입니다. 또한를 사용 하 여 변환 하는.NET Framework 유형도 몇 가지는 **XmlConvert** 클래스의 메서드는 사용 하지 않도록 아직는 **System.Convert** 클래스입니다. **XmlConvert** 클래스 XSD (XML 스키마) 데이터 형식 사양을 따르며에 데이터 형식이 있는 **XmlConvert** 매핑될 수 있습니다.  
  
 다음 표에서는 XSD(XML 스키마) 데이터 형식 매핑을 사용할 때 반환되는 .NET Framework 데이터 형식 및 문자열 형식의 목록을 보여 줍니다. 이러한.NET Framework 형식을 사용 하 여 처리할 수 없습니다 **System.Convert**합니다.  
  
|.NET Framework 형식|반환 문자열|  
|-------------------------|---------------------|  
|Boolean|"true", "false"|  
|Single.PositiveInfinity|"INF"|  
|Single.NegativeInfinity|"-INF"|  
|Double.PositiveInfinity|"INF"|  
|Double.NegativeInfinity|"-INF"|  
|DateTime|형식은 "yyyy-MM-ddTHH:mm:sszzzzzz" 및 해당 하위 집합입니다.|  
|Timespan|형식은 PnYnMnTnHnMnS입니다. 즉, `P2Y10M15DT10H30M20S`는 2년 10개월 15일 10시간 30분 20초의 지속 시간을 나타냅니다.|  
  
> [!NOTE]
>  테이블을 사용 하 여 문자열에 나열 된.NET Framework 형식으로 변환 하는 경우는 **ToString** 메서드에서 반환 된 문자열은 기본 형식이 아니라 XSD (XML 스키마) 문자열 형식입니다.  
  
 **DateTime** 및 **Timespan** 하의 값 형식은 다릅니다. 한 **DateTime** 반면은 순간적인 시각을 나타내며는 **TimeSpan** 시간 간격을 나타냅니다. **DateTime** 및 **Timespan** 형식을 XSD (XML 스키마) 데이터 형식 사양에 지정 합니다. 예:  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim [date] As New DateTime(2001, 8, 4)  
writer.WriteElementString("Date", XmlConvert.ToString([date]))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
DateTime date = new DateTime (2001, 08, 04);  
writer.WriteElementString("Date", XmlConvert.ToString(date));  
```  
  
 **출력**  
  
 `<Date>2001-08-04T00:00:00</Date>`.  
  
 다음 코드는 정수를 문자열로 변환합니다.  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim value As Int32 = 200  
writer.WriteElementString("Number", XmlConvert.ToString(value))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
Int32 value = 200;  
writer.WriteElementString("Number", XmlConvert.ToString(value));  
```  
  
 **출력**  
  
 `<Number>200</Number>`  
  
 그러나 문자열을 변환 하는 경우 **부울**, **단일**, 또는 **Double**, 반환 되는.NET Framework 형식을 사용 하는 경우 반환 되는 형식 동일 하지 않습니다는 **System.Convert** 클래스입니다.  
  
## <a name="string-to-boolean"></a>문자열을 Boolean 형식으로 변환  
 다음 표에서 문자열을 변환 하는 경우 지정된 된 입력된 문자열에 대해 생성 되는 형식을 보여 줍니다. **부울** 를 사용 하 여 **ToBoolean** 메서드.  
  
|유효한 문자열 입력 매개 변수|.NET Framework 출력 형식|  
|----------------------------------|--------------------------------|  
|"true"|Boolean.True|  
|"1"|Boolean.True|  
|"false"|Boolean.False|  
|"0"|Boolean.False|  
  
 예를 들어, 다음과 같이 XML을 가정합니다.  
  
 **입력**  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>   
```  
  
 다음 코드를 인식할 수 있는 둘 다 고 **bvalue** 은 **System.Boolean.True**:  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a>문자열을 Single 형식으로 변환  
 다음 표에서 문자열을 변환 하는 경우 지정된 된 입력된 문자열에 대해 생성 되는 형식을 보여 줍니다.는 **단일** 를 사용 하는 **ToSingle** 메서드.  
  
|유효한 문자열 입력 매개 변수|.NET Framework 출력 형식|  
|----------------------------------|--------------------------------|  
|"INF"|Single.PositiveInfinity|  
|"-INF"|Single.NegativeInfinity|  
  
## <a name="string-to-double"></a>문자열을 Double 형식으로 변환  
 다음 표에서 문자열을 변환 하는 경우 지정된 된 입력된 문자열에 대해 생성 되는 형식을 보여 줍니다.는 **단일** 를 사용 하는 **ToDouble** 메서드.  
  
|유효한 문자열 입력 매개 변수|.NET Framework 출력 형식|  
|----------------------------------|--------------------------------|  
|"INF"|Double.PositiveInfinity|  
|"-INF"|Double.NegativeInfinity|  
  
 다음 코드는 `<Infinity>INF</Infinity>`를 작성합니다.  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 데이터 형식 변환](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [.NET Framework 형식을 문자열로 변환](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
