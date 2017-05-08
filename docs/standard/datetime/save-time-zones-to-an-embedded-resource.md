---
title: "방법: 포함 리소스에 표준 시간대 저장 | Microsoft Docs"
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
  - "표준 시간대 개체[.NET Framework], 저장"
  - "표준 시간대 개체[.NET Framework], serialize"
  - "표준 시간대[.NET Framework], 저장"
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 포함 리소스에 표준 시간대 저장
표준 시간대 인식 응용 프로그램에는 특정 표준 시간대가 있어야 하는 경우가 많습니다.  그러나 통상 사용 가능한 표준 시간대가 없더라도 로컬 시스템의 레지스트리에 저장된 정보에 따라 개별 <xref:System.TimeZoneInfo> 개체의 가용성이 달라집니다.  또한 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 사용하여 인스턴스화한 사용자 지정 표준 시간대에 대한 정보는 다른 표준 시간대 정보와 달리 레지스트리에 저장되지 않습니다.  이러한 표준 시간대를 필요할 때 사용할 수 있으려면 해당 시간대를 serialize하여 저장하고 나중에 deserialize하여 복원할 수 있습니다.  
  
 일반적으로 <xref:System.TimeZoneInfo> 개체의 serialization은 표준 시간대 인식 응용 프로그램과 별도로 발생합니다.  Serialize된 <xref:System.TimeZoneInfo> 개체를 보관하는 데 사용되는 데이터 저장소에 따라 표준 시간대 데이터가 serialize되는 방법이 달라질 수 있습니다. 예를 들어 데이터가 레지스트리의 응용 프로그램 키에 저장되는 경우에는 설치 루틴의 일부로 serialize되고, 데이터가 .NET XML 리소스 파일\(.resx\)에 저장되는 경우에는 최종 응용 프로그램이 컴파일되기 전에 실행되는 유틸리티 루틴의 일부로 serialize될 수 있습니다.  
  
 응용 프로그램에서 컴파일된 리소스 파일 이외에도 표준 시간대 정보를 저장하는 데 사용할 수 있는 다른 여러 데이터 저장소가 있습니다.  이러한 요구 사항은 다음과 같습니다.  
  
-   레지스트리.  응용 프로그램에서는 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Time Zones의 하위 키를 사용하지 않고 고유한 응용 프로그램 키의 하위 키를 사용하여 사용자 지정 표준 시간대 데이터를 저장해야 합니다.  
  
-   구성 파일  
  
-   기타 시스템 파일  
  
### 표준 시간대를 serialize하여 .resx 파일에 저장하려면  
  
1.  기존 표준 시간대를 검색하거나 새 표준 시간대를 만듭니다.  
  
     기존 표준 시간대를 검색하려면 [방법: 미리 정의된 UTC 및 현지 표준 시간대 개체에 액세스](../../../docs/standard/datetime/access-utc-and-local.md) 및 [방법: TimeZoneInfo 개체 인스턴스화](../../../docs/standard/datetime/instantiate-time-zone-info.md)를 참조하십시오.  
  
     새 표준 시간대를 만들려면 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드의 오버로드 중 하나를 호출합니다.  자세한 내용은 [방법: 조정 규칙을 사용하지 않고 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) 및 [방법: 조정 규칙을 사용하여 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)를 참조하십시오.  
  
2.  <xref:System.TimeZoneInfo.ToSerializedString%2A> 메서드를 호출하여 표준 시간대의 데이터가 포함된 문자열을 만듭니다.  
  
3.  <xref:System.IO.StreamWriter> 개체의 이름과 필요한 경우 .resx 파일에 대한 경로를 <xref:System.IO.StreamWriter> 클래스 생성자에 지정하여 이 개체를 인스턴스화합니다.  
  
4.  <xref:System.IO.StreamWriter> 개체를 <xref:System.Resources.ResXResourceWriter> 클래스 생성자에 전달하여 <xref:System.Resources.ResXResourceWriter> 개체를 인스턴스화합니다.  
  
5.  표준 시간대의 serialize된 문자열을 <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=fullName> 메서드에 전달합니다.  
  
6.  <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=fullName> 메서드를 호출합니다.  
  
7.  <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=fullName> 메서드를 호출합니다.  
  
8.  <xref:System.IO.StreamWriter> 개체의 <xref:System.IO.StreamWriter.Close%2A> 메서드를 호출하여 이 개체를 닫습니다.  
  
9. 생성된 .resx 파일을 응용 프로그램의 Visual Studio 프로젝트에 추가합니다.  
  
10. Visual Studio의 **속성** 창을 사용하여 .resx 파일의 **빌드 작업** 속성이 **포함 리소스**로 설정되어 있는지 확인합니다.  
  
## 예제  
 다음 예제에서는 중부 표준시를 나타내는 <xref:System.TimeZoneInfo> 개체와 남극 대륙 파머 기지 시간을 나타내는 <xref:System.TimeZoneInfo> 개체를 SerializedTimeZones.resx라는 .NET XML 리소스 파일로 serialize합니다.  중부 표준시는 일반적으로 레지스트리에 정의되어 있는 반면 남극 대륙 파머 기지는 사용자 지정 표준 시간대입니다.  
  
 [!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
 [!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]  
  
 이 예제에서는 컴파일할 때 리소스 파일에서 사용할 수 있도록 <xref:System.TimeZoneInfo> 개체를 serialize합니다.  
  
 <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=fullName> 메서드에서는 전체 헤더 정보를 .NET XML 리소스 파일에 추가하므로 이 메서드로는 기존 파일에 리소스를 추가할 수 없습니다.  이 예제에서는 SerializedTimeZones.resx 파일이 있는지 확인하고 있는 경우 두 개의 serialize된 표준 시간대 외의 모든 리소스를 제네릭 <xref:System.Collections.Generic.Dictionary%602> 개체에 저장하여 이를 처리합니다.  그러면 기존 파일이 삭제되고 기존 리소스가 새 SerializedTimeZones.resx 파일에 추가됩니다.  Serialize된 표준 시간대 데이터도 이 파일에 추가됩니다.  
  
 리소스의 키\(또는 **이름**\) 필드에는 공백이 포함되어 있으면 안 됩니다.  표준 시간대 식별자를 리소스 파일에 할당하기 전에 <xref:System.String.Replace%28System.String%2CSystem.String%29> 메서드를 호출하여 해당 식별자에 포함된 공백을 모두 제거합니다.  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.Windows.Forms.dll 및 System.Core.dll에 대한 참조를 프로젝트에 추가해야 합니다.  
  
-   다음 네임스페이스를 가져와야 합니다.  
  
     [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
     [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]  
  
## 참고 항목  
 [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)   
 [표준 시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)   
 [방법: 포함 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)