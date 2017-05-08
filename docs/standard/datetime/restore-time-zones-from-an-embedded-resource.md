---
title: "방법: 포함 리소스에서 표준 시간대 복원 | Microsoft Docs"
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
  - "표준 시간대[.NET Framework], deserialize"
  - "표준 시간대[.NET Framework], 복원"
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 포함 리소스에서 표준 시간대 복원
이 항목에서는 리소스 파일에서 저장된 표준 시간대를 복원하는 방법에 대해 설명합니다.  표준 시간대를 저장하는 방법에 대한 자세한 내용과 지침은 [방법: 포함 리소스에 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)을 참조하십시오.  
  
### 포함 리소스에서 TimeZoneInfo 개체를 deserialize하려면  
  
1.  검색할 표준 시간대가 사용자 지정 표준 시간대가 아닌 경우 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 메서드를 사용하여 해당 표준 시간대를 인스턴스화합니다.  
  
2.  포함 리소스 파일의 정규화된 이름과 리소스 파일을 포함하는 어셈블리에 대한 참조를 전달하여 <xref:System.Resources.ResourceManager> 개체를 인스턴스화합니다.  
  
     포함 리소스 파일의 정규화된 이름을 확인할 수 없으면 [Ildasm.exe\(IL 디스어셈블러\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)를 사용하여 어셈블리 매니페스트를 검사합니다.  `.mresource` 엔트리는 리소스를 식별합니다.  이 예제에서 리소스의 정규화된 이름은 `SerializeTimeZoneData.SerializedTimeZones`입니다.  
  
     리소스 파일이 표준 시간대 인스턴스화 코드가 있는 동일한 어셈블리에 포함되어 있는 경우 `static`\(Visual Basic의 경우 `Shared`\) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> 메서드를 호출하여 어셈블리에 대한 참조를 검색할 수 있습니다.  
  
3.  <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 메서드 호출에 실패하거나 사용자 지정 표준 시간대를 인스턴스화해야 하는 경우 <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName> 메서드를 호출하여 serialize된 표준 시간대가 포함된 문자열을 검색합니다.  
  
4.  <xref:System.TimeZoneInfo.FromSerializedString%2A> 메서드를 호출하여 표준 시간대 데이터를 deserialize합니다.  
  
## 예제  
 다음 예제에서는 포함 .NET XML 리소스 파일에 저장된 <xref:System.TimeZoneInfo> 개체를 deserialize합니다.  
  
 [!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
 [!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]  
  
 이 코드에서는 응용 프로그램에 필요한 <xref:System.TimeZoneInfo> 개체가 있는지 확인하는 예외 처리를 보여 줍니다.  이 코드에서는 먼저 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 메서드를 사용하여 레지스트리에서 <xref:System.TimeZoneInfo> 개체를 검색하여 해당 개체를 인스턴스화합니다.  표준 시간대를 인스턴스화할 수 없는 경우 코드에서는 포함 리소스 파일에서 표준 시간대를 검색합니다.  
  
 사용자 지정 표준 시간대\(<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 사용하여 인스턴스화한 표준 시간대\)에 대한 데이터가 레지스트리에 저장되어 있지 않으므로 코드에서는 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>를 호출하여 남극 대륙의 파머 반도에 대한 표준 시간대를 인스턴스화하지 못합니다.  대신 <xref:System.TimeZoneInfo.FromSerializedString%2A> 메서드를 호출하기 전에 곧바로 포함 리소스 파일에 표준 시간대 데이터가 포함된 문자열이 있는지 검색합니다.  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.Windows.Forms.dll 및 System.Core.dll에 대한 참조를 프로젝트에 추가해야 합니다.  
  
-   다음 네임스페이스를 가져와야 합니다.  
  
     [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
     [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]  
  
## 참고 항목  
 [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)   
 [표준 시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)   
 [방법: 포함 리소스에 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)