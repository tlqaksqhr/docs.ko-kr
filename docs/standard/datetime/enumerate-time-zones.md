---
title: "방법: 컴퓨터에 있는 표준 시간대 열거 | Microsoft Docs"
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
  - "표준 시간대 열거[.NET Framework]"
  - "표준 시간대[.NET Framework], 열거"
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 컴퓨터에 있는 표준 시간대 열거
지정한 표준 시간대를 성공적으로 사용하려면 해당 표준 시간대에 대한 정보를 시스템에서 사용할 수 있어야 합니다.  Windows XP 및 Windows Vista 운영 체제에서는 이 정보를 레지스트리에 저장합니다.  그러나 전세계에 있는 표준 시간대의 전체 수는 상당히 많지만 레지스트리에는 이들 중 일부에 대한 정보만 포함되어 있습니다.  또한 레지스트리 자체도 동적 구조이므로 그 내용이 실수나 고의로 변경될 수 있습니다.  따라서 응용 프로그램에 항상 특정 표준 시간대가 정의되어 있고 시스템에서 사용 가능한 것으로 가정할 수 없습니다.  표준 시간대 정보 응용 프로그램을 사용하는 많은 응용 프로그램의 첫 번째 단계로는 필요한 표준 시간대를 로컬 시스템에서 사용할 수 있는지 여부를 확인하거나 사용자에게 표준 시간대를 선택할 수 있는 목록을 제공하는 것입니다.  이를 위해 응용 프로그램에서는 로컬 시스템에 정의되어 있는 표준 시간대를 나열해야 합니다.  
  
> [!NOTE]
>  로컬 시스템에 정의되어 있지 않은 특정 표준 시간대가 응용 프로그램에 필요한 경우 응용 프로그램에서는 표준 시간대에 대한 정보를 serialize 및 deserialize하여 해당 시간대가 있는지 확인할 수 있습니다.  그런 다음 이 표준 시간대를 응용 프로그램 사용자가 선택할 수 있도록 목록 컨트롤에 추가할 수 있습니다.  자세한 내용은 [방법: 포함 리소스에 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) 및 [방법: 포함 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)을 참조하십시오.  
  
### 로컬 시스템에 있는 표준 시간대를 열거하려면  
  
1.  <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=fullName> 메서드를 호출합니다.  이 메서드는 <xref:System.TimeZoneInfo> 개체의 제네릭 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 컬렉션을 반환합니다.  컬렉션의 엔트리는 해당하는 <xref:System.TimeZoneInfo.DisplayName%2A> 속성을 기준으로 정렬됩니다.  예를 들면 다음과 같습니다.  
  
     [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
     [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]  
  
2.  `foreach` 루프\(C\#의 경우\) 또는 `For Each`…`Next` 루프\(Visual Basic의 경우\)를 사용하여 컬렉션의 개별 <xref:System.TimeZoneInfo> 개체를 열거하고 각 개체에 대해 필요한 처리를 수행합니다.  예를 들어 다음 코드에서는 1단계에서 반환된 <xref:System.TimeZoneInfo> 개체의 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 컬렉션을 열거하고 각 표준 시간대의 표시 이름을 콘솔에 나열합니다.  
  
     [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
     [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]  
  
### 사용자에게 로컬 시스템에 있는 표준 시간대의 목록을 제공하려면  
  
1.  <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=fullName> 메서드를 호출합니다.  이 메서드는 <xref:System.TimeZoneInfo> 개체의 제네릭 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 컬렉션을 반환합니다.  
  
2.  1단계에서 반환된 컬렉션을 Windows Forms 또는 ASP.NET 목록 컨트롤의 `DataSource` 속성에 할당합니다.  
  
3.  사용자가 선택한 <xref:System.TimeZoneInfo> 개체를 검색합니다.  
  
 다음 예제에서는 Windows 응용 프로그램에 대해 설명합니다.  
  
## 예제  
 이 예제에서는 시스템에 정의되어 있는 표준 시간대를 목록 상자에 표시하는 Windows 응용 프로그램을 시작합니다.  그런 다음 사용자가 선택한 표준 시간대 개체의 <xref:System.TimeZoneInfo.DisplayName%2A> 속성 값이 포함된 대화 상자를 표시합니다.  
  
 [!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
 [!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]  
  
 <xref:System.Windows.Forms.ListBox?displayProperty=fullName> 또는 <xref:System.Web.UI.WebControls.BulletedList?displayProperty=fullName> 컨트롤과 같은 대부분의 목록 컨트롤을 사용하면 개체 변수의 컬렉션에서 <xref:System.Collections.IEnumerable> 인터페이스를 구현하는 경우 해당 컬렉션을 `DataSource` 속성에 할당할 수 있습니다. 제네릭 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 클래스를 사용하여 이렇게 합니다. 컬렉션의 개별 개체를 표시하려면 컨트롤에서 개체의 `ToString` 메서드를 호출하여 개체를 나타내는 데 사용되는 문자열을 추출합니다.  <xref:System.TimeZoneInfo> 개체의 경우 `ToString` 메서드는 <xref:System.TimeZoneInfo> 개체의 표시 이름 즉, <xref:System.TimeZoneInfo.DisplayName%2A> 속성의 값을 반환합니다.  
  
> [!NOTE]
>  목록 컨트롤에서는 개체의 `ToString` 메서드를 호출하므로 <xref:System.TimeZoneInfo> 개체의 컬렉션을 컨트롤에 할당하고 컨트롤에 각 개체에 대한 의미 있는 이름을 표시할 수 있으며 사용자가 선택한 <xref:System.TimeZoneInfo> 개체를 검색할 수 있습니다.  그러면 컬렉션에 있는 각 개체의 문자열을 추출하고, 이 문자열을 컬렉션에 할당한 다음 다시 컨트롤의 `DataSource` 속성에 할당하고, 사용자가 선택한 문자열을 검색한 다음 이 문자열을 사용하여 문자열이 설명하는 개체를 추출하는 일련의 작업이 필요하지 않습니다.  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.Core.dll에 대한 참조를 프로젝트에 추가해야 합니다.  
  
-   다음 네임스페이스를 가져와야 합니다.  
  
     <xref:System>\(C\# 코드의 경우\)  
  
     <xref:System.Collections.ObjectModel>  
  
## 참고 항목  
 [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)   
 [방법: 포함 리소스에 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)   
 [방법: 포함 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)