---
title: "표준 시간대 저장 및 복원 | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "deserialization[.NET Framework], 시간대"
  - "표준 시간대 복원"
  - "표준 시간대 저장"
  - "serialization[.NET Framework], 시간대"
  - "표준 시간대 개체[.NET Framework], deserialize"
  - "표준 시간대 개체[.NET Framework], 복원"
  - "표준 시간대 개체[.NET Framework], 저장"
  - "표준 시간대 개체[.NET Framework], serialize"
  - "표준 시간대[.NET Framework], 복원"
  - "표준 시간대[.NET Framework], 저장"
ms.assetid: 4028b310-e7ce-49d4-a646-1e83bfaf6f9d
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 표준 시간대 저장 및 복원
<xref:System.TimeZoneInfo> 클래스는 레지스트리를 통해 미리 정의된 표준 시간대 데이터를 검색합니다.  그러나 레지스트리는 동적 구조입니다.  또한 레지스트리에 포함된 표준 시간대 정보는 운영 체제에서 기본적으로 현재 연도에 대한 시간 조정 및 변환을 처리하기 위해 사용됩니다.  이는 정확한 표준 시간대 데이터를 사용하는 응용 프로그램에 다음 두 가지 주요한 영향을 미칩니다.  
  
-   응용 프로그램에 필요한 표준 시간대가 레지스트리에 정의되어 있지 않거나 레지스트리에서 제거되거나 이름이 바뀌었을 수 있습니다.  
  
-   레지스트리에 정의되어 있는 표준 시간대에 기록 표준 시간대 변환에 필요한 특정 조정 규칙에 대한 정보가 없을 수 있습니다.  
  
 <xref:System.TimeZoneInfo> 클래스는 표준 시간대 데이터의 serialization\(저장\) 및 deserialization\(복원\)에 대한 지원을 통해 이러한 제한 사항을 해결합니다.  
  
## 표준 시간대 serialization 및 deserialization  
 표준 시간대 데이터를 serialize 및 deserialize하여 표준 시간대를 저장 및 복원하려면 다음과 같이 두 메서드만 호출하면 됩니다.  
  
-   <xref:System.TimeZoneInfo> 개체의 <xref:System.TimeZoneInfo.ToSerializedString%2A> 메서드를 호출하여 해당 개체를 serialize할 수 있습니다.  이 메서드는 매개 변수를 사용하지 않으며 표준 시간대 정보가 포함된 문자열을 반환합니다.  
  
-   Serialize된 문자열을 `static`\(Visual Basic의 경우 `Shared`\) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=fullName> 메서드에 전달하여 해당 문자열에서 <xref:System.TimeZoneInfo> 개체를 deserialize할 수 있습니다.  
  
## Serialization 및 deserialization 시나리오  
 <xref:System.TimeZoneInfo> 개체를 문자열로 저장 또는 serialize하고 나중에 사용하기 위해 복원 또는 deserialize하는 기능은 <xref:System.TimeZoneInfo> 클래스의 유용성과 유연성을 향상시킵니다.  이 단원에서는 serialization 및 deserialization이 가장 유용한 몇 가지 상황을 살펴봅니다.  
  
### 응용 프로그램에서 표준 시간대 데이터 serialize 및 deserialize  
 필요한 경우 문자열에서 serialize된 표준 시간대를 복원할 수 있습니다.  레지스트리에서 검색된 표준 시간대가 특정 날짜 범위 내의 날짜 및 시간을 올바르게 변환할 수 없는 경우에 응용 프로그램에서 복원할 수 있습니다.  예를 들어 Windows XP 레지스트리의 표준 시간대 데이터에서는 하나의 조정 규칙을 지원하는 반면 Windows Vista 레지스트리에 정의된 표준 시간대에서는 일반적으로 두 개의 조정 규칙에 대한 정보를 제공합니다.  따라서 기록 시간 변환이 잘못될 수 있습니다.  표준 시간대 데이터의 serialization 및 deserialization을 통해 이 제한 사항을 처리할 수 있습니다.  
  
 다음 예제에서는, 조정 규칙이 없는 사용자 지정 <xref:System.TimeZoneInfo> 클래스가 미국에서 일광 절약 시간을 도입 하기 전에, 1883년 부터 1917년까지 미국 동부 표준 시간을 나타내기 위해 정의합니다.  이 사용자 지정 표준 시간대는 전역 범위를 갖는 변수로 serialize됩니다.  표준 시간대 변환 메서드 `ConvertUtcTime`에 변환할 UTC\(협정 세계시\) 시간이 전달됩니다.  날짜 및 시간이 1917년 이전에 있는 경우 사용자 지정 동부 표준시가 serialize된 문자열에서 복원되고 레지스트리에서 검색된 표준 시간대를 대체합니다.  
  
 [!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
 [!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]  
  
### 표준 시간대 예외 처리  
 레지스트리는 동적 구조이므로 해당 내용이 실수나 고의로 수정될 수 있습니다.  따라서 응용 프로그램을 성공적으로 실행하는 데 필요한 표준 시간대가 레지스트리에 정의되어 있어야 하는 데 없을 수 있습니다.  표준 시간대 serialization 및 deserialization이 지원되지 않으면 <xref:System.TimeZoneNotFoundException>이 발생한 경우 응용 프로그램을 종료하여 이를 처리할 수밖에 없습니다.  그러나 표준 시간대 serialization 및 deserialization을 사용하면 serialize된 문자열에서 필요한 표준 시간대를 복원하여 예기치 않은 <xref:System.TimeZoneNotFoundException>을 처리할 수 있으므로 응용 프로그램이 계속 실행됩니다.  
  
 다음 예제에서는 사용자 지정 중부 표준시를 만들고 serialize합니다.  그런 다음 레지스트리에서 중부 표준시를 검색합니다.  검색 작업에서 <xref:System.TimeZoneNotFoundException> 또는 <xref:System.InvalidTimeZoneException>이 throw되는 경우 예외 처리기에서 표준 시간대를 deserialize합니다.  
  
 [!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
 [!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]  
  
### Serialize된 문자열 저장 및 필요한 경우 복원  
 앞의 예제에서는 표준 시간대 정보를 문자열 변수에 저장하고 필요한 경우에 복원했습니다.  그러나 serialize된 표준 시간대 정보가 포함된 문자열 자체는 외부 파일, 응용 프로그램에 포함된 리소스 파일, 레지스트리 등과 같은 저장 미디어에 저장될 수 있습니다. 사용자 지정 표준 시간대에 대한 정보는 레지스트리에 있는 시스템의 표준 시간대 키와 별도로 저장해야 합니다.  
  
 또한 이와 같은 방식으로 serialize된 표준 시간대 문자열을 저장하면 표준 시간대 작성 루틴이 응용 프로그램 자체에서 분리됩니다.  예를 들어 응용 프로그램이 사용할 수 있는 기록 표준 시간대 정보가 포함된 데이터 파일을 표준 시간대 작성 루틴에서 실행하고 만들 수 있습니다.  그런 다음 이 데이터 파일을 응용 프로그램에 설치하고 응용 프로그램에 표준 시간대가 필요한 경우 이 데이터 파일을 열어 하나 이상의 표준 시간대를 deserialize할 수 있습니다.  
  
 포함 리소스를 사용하여 serialize된 표준 시간대 데이터를 저장하는 예제는 [방법: 포함 리소스에 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) 및 [방법: 포함 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)을 참조하십시오.  
  
## 참고 항목  
 [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)