---
title: "dateTimeInvalidLocalFormat MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "dates [.NET Framework], formatting"
  - "invalid date time local format"
  - "invalid local formats"
  - "MDAs (managed debugging assistants), invalid local formats"
  - "managed debugging assistants (MDAs), invalid local formats"
  - "dateTimeInvalidLocalFormat MDA"
  - "date formatting"
  - "time formatting"
  - "UTC formatting"
ms.assetid: c4a942bb-2651-4b65-8718-809f892a0659
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# dateTimeInvalidLocalFormat MDA
`dateTimeInvalidLocalFormat` MDA는 UTC\(협정 세계시\)로 저장된 <xref:System.DateTime> 인스턴스가 현지 <xref:System.DateTime> 인스턴스에 대해서만 사용할 수 있는 형식을 사용하여 서식이 지정된 경우 활성화됩니다.  이 MDA는 지정되지 않았거나 기본 <xref:System.DateTime> 인스턴스에 대해서는 활성화되지 않습니다.  
  
## 증상  
 응용 프로그램에서는 로컬 형식을 사용하여 UTC <xref:System.DateTime> 인스턴스를 수동으로 serialize합니다.  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffzzz"));  
```  
  
### 원인  
 <xref:System.DateTime.ToString%2A?displayProperty=fullName> 메서드의 'z' 형식에는 현지 시간 영역 오프셋이 포함됩니다\(예: 시드니 시간의 경우 "\+10:00"\).  이와 같이 <xref:System.DateTime> 값이 현지 시간인 경우에만 의미 있는 결과가 산출됩니다.  해당 값이 UTC 시간인 경우 <xref:System.DateTime.ToString%2A?displayProperty=fullName>에는 현지 시간 영역 오프셋이 포함되지만 시간 영역 지정자를 표시하거나 조정하지는 않습니다.  
  
### 해결  
 UTC <xref:System.DateTime> 인스턴스는 UTC임을 나타내는 방식으로 서식을 지정해야 합니다.  UTC 시간의 권장 형식은 'Z'를 사용하여 UTC 시간을 표시하는 것입니다.  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffZ"));  
```  
  
 또한 인스턴스가 로컬인지, UTC인지 또는 지정되지 않았는지의 여부와 관계없이 올바르게 serialize하는 <xref:System.DateTime.Kind%2A> 속성을 활용하여 <xref:System.DateTime>을 serialize하는 "o" 형식도 있습니다.  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("o"));  
```  
  
## 런타임 효과  
 이 MDA는 런타임에 아무런 영향을 주지 않습니다.  
  
## Output  
 이 MDA 활성화의 결과에 해당하는 특수한 출력은 없습니다. 그러나 호출 스택을 사용하여 MDA를 활성화한 <xref:System.DateTime.ToString%2A> 호출의 위치를 확인할 수 있습니다.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <dateTimeInvalidLocalFormat />  
  </assistants>  
</mdaConfig>  
```  
  
## 예제  
 <xref:System.Xml.XmlConvert> 또는 <xref:System.Data.DataSet> 클래스를 다음과 같은 방법으로 사용하여 UTC <xref:System.DateTime> 값을 간접적으로 serialize하는 응용 프로그램을 고려하십시오.  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XMLConvert.ToString(myDateTime);  
```  
  
 <xref:System.Xml.XmlConvert> 및 <xref:System.Data.DataSet> serialization은 기본적으로 serialization에 로컬 형식을 사용합니다.  UTC와 같은 다른 종류의 <xref:System.DateTime> 값을 serialize하는 데에는 추가 옵션이 필요합니다.  
  
 다음 특정 예제에서는 `XmlConvert`에서 `ToString` 호출에 `XmlDateTimeSerializationMode.RoundtripKind`를 전달합니다.  이렇게 하면 데이터를 UTC 시간으로 serialize합니다.  
  
 <xref:System.Data.DataSet>을 사용하는 경우 <xref:System.Data.DataColumn> 개체의 <xref:System.Data.DataColumn.DateTimeMode%2A> 속성을 <xref:System.Data.DataSetDateTime>로 설정합니다.  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XmlConvert.ToString(myDateTime,   
    XmlDateTimeSerializationMode.RoundtripKind);  
```  
  
## 참고 항목  
 <xref:System.Globalization.DateTimeFormatInfo>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)