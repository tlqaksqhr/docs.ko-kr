---
title: ".NET Framework 4.5.2의 변경 내용 대상 변경 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2be2a828-9052-4738-a965-d4a836cc6384
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# .NET Framework 4.5.2의 변경 내용 대상 변경
드문 경우지만 대상 다시 지정 변경 내용은 .NET Framework 4.5.2를 대상으로 다시 컴파일되는 앱에 영향을 줄 수 있습니다. 다음 테이블에 지정된 변경 내용 이외에 이러한 변경 내용은 이전 버전의 .NET Framework를 대상으로 하지만 버전 4.5.2에서 실행되는 이진 파일에 영향을 주지 않습니다. .NET Framework 4.5.2의 다음과 같은 영역에 대상 다시 지정 변경 내용이 포함되어 있습니다.  
  
-   [Entity Framework](#EF)  
  
-   [Windows Forms](#WinForms)  
  
<a name="EF"></a>   
## Entity Framework 대상 다시 지정 변경 내용  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|정렬되지 않은 제한 작업을 사용할 때의 단순한 쿼리|`JOIN` 문을 생성하며 <xref:System.Data.Objects.ObjectQuery%601.OrderBy%2A>를 먼저 사용하지 않고 제한 작업에 대한 호출을 포함한 쿼리가 이제는 단순한 SQL을 생성합니다.[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]로 업그레이드한 후 이러한 쿼리는 이전 버전보다 더욱 복잡한 SQL을 생성했습니다.|이 기능은 기본적으로 비활성화되어 있습니다. Entity Framework가 성능 저하를 일으키는 추가 `JOIN` 문을 생성하는 경우 다음의 항목을 응용 프로그램 구성 파일\(app.config\)의 `<appSettings>` 섹션에 추가하여 이 기능을 활성화할 수 있습니다.<br /><br /> `<add key="EntityFramework_SimplifyLimitOperations" value="true" />`|사소함|  
  
<a name="WinForms"></a>   
## Windows Forms 대상 다시 지정 변경 내용  
  
|기능|변경|영향|범위|  
|--------|--------|--------|--------|  
|<xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName> 메서드로 클립보드에서 HTML 형식의 데이터 검색|[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]를 대상으로 하거나 .NET Framework 4.5.1 이하 버전에서 실행되는 앱의 경우, <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName>는 HTML 형식의 데이터를 ASCII 문자열로 검색합니다. 그 결과 ASCII 문자가 아닌 문자\(ASCII 코드가 0x7F보다 큰 문자\)는 임의의 두 문자로 표시됩니다. 예를 들어 é 문자\(0xE9\)는 Ã©\(0xC3 0xA9\) 문자로 표시됩니다.<br /><br /> [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 이상을 대상으로 하거나 .NET Framework 4.5.2에서 실행되는 앱의 경우, <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=fullName>는 HTML 형식의 데이터를 UTF\-8로 검색하여 0x7F보다 큰 문자를 올바르게 나타낼 수 있습니다.|HTML 형식 문자열 인코딩 문제에 대한 해결 방법을 구현한 상태에서\(예를 들어 클립보드에서 검색한 HTML 문자열을 <xref:System.Text.UTF8Encoding.GetString%2A?displayProperty=fullName> 메서드에 전달하여 명시적으로 인코딩함으로써\) 앱의 대상을 버전 4에서 4.5로 다시 지정하려면 해당 해결 방법을 제거해야 합니다.|사소함|  
  
## 참고 항목  
 [런타임 변경 내용](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-2.md)   
 [4.5의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [4.5.1의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)