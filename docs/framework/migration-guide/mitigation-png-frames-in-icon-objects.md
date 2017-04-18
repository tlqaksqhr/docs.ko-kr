---
title: "완화: 아이콘 개체의 PNG 프레임 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# 완화: 아이콘 개체의 PNG 프레임
.NET Framework 4.6부터는 <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> 메서드가 PNG 프레임이 있는 아이콘을 <xref:System.Drawing.Bitmap> 개체로 성공적으로 변환합니다.  
  
 .NET Framework 4.5.2 및 이전 버전을 대상으로 하는 앱에서는 <xref:System.Drawing.Icon> 개체에 PNG 프레임이 있는 경우 <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> 메서드가 <xref:System.ArgumentOutOfRangeException> 예외를 throw합니다.  
  
## 영향  
 이 변경은 <xref:System.Drawing.Icon> 개체에 PNG 프레임이 있을 때 throw되는 <xref:System.ArgumentOutOfRangeException>에 대해 특수 처리를 구현하고 .NET Framework 4.6을 대상으로 다시 컴파일되는 앱에 영향을 줍니다. .NET Framework 4.6에서 실행되는 경우 변환이 성공하고 <xref:System.ArgumentOutOfRangeException>이 더 이상 throw되지 않습니다. 따라서 예외 처리기가 더 이상 호출되지 않습니다.  
  
### 완화  
 이 동작이 필요 없는 경우 다음 요소를 app.config 파일의 [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 추가하여 이전 동작을 유지할 수 있습니다.  
  
```  
<AppContextSwitchOverrides value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
  
```  
  
 App.config 파일에 이미 `AppContextSwitchOverrides` 요소가 포함되어 있는 경우 새 값은 다음과 같이 `value` 특성과 병합되어야 합니다.  
  
```  
<AppContextSwitchOverrides value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;<previous key>=<previous value>" />  
  
```  
  
## 참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)