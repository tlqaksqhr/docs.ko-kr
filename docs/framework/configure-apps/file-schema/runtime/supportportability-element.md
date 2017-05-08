---
title: "&lt;supportPortability&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
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
  - "<supportPortability> 요소"
  - "supportPortability 요소"
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# &lt;supportPortability&gt; 요소
응용 프로그램 이식성을 위해 어셈블리를 같은 것으로 간주하는 기본 동작을 비활성화하여 응용 프로그램이 .NET Framework의 두 가지 다른 구현에 있는 같은 어셈블리를 참조할 수 있도록 지정합니다.  
  
## 구문  
  
```  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|PKT|필수 특성입니다.<br /><br /> 영향을 받는 어셈블리의 공개 키 토큰을 문자열로 지정합니다.|  
|enabled|선택적 특성입니다.<br /><br /> 지정된 .NET Framework 어셈블리의 구현 간 이식성 지원을 활성화할지 여부를 지정합니다.|  
  
## enabled 특성  
  
|값|설명|  
|-------|--------|  
|true|지정된 .NET Framework 어셈블리의 구현 간 이식성 지원을 활성화합니다.  이 값이 기본값입니다.|  
|false|지정된 .NET Framework 어셈블리의 구현 간 이식성 지원을 비활성화합니다.  이는 응용 프로그램이 지정된 어셈블리의 여러 구현을 참조하도록 할 수 있습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|어셈블리 바인딩 및 가비지 수집에 대한 정보를 포함합니다.|  
|`assemblyBinding`|어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.|  
  
## 설명  
 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]부터 .NET Framework의 두 구현 즉, .NET Framework 구현 또는 .NET Framework for Silverlight 구현을 사용할 수 있는 응용 프로그램에 대해 지원이 자동으로 제공됩니다.  특정 .NET Framework 어셈블리의 두 구현은 어셈블리 바인더와 같은 것으로 볼 수 있습니다.  몇 가지 시나리오에서 이 응용 프로그램 이식성 기능은 문제를 일으킵니다.  이러한 시나리오에서는 기능을 비활성화하는 데 `<supportPortability>` 요소를 사용할 수 있습니다.  
  
 이런 시나리오는 .NET Framework 구현과 특정 참조 어셈블리의 .NET Framework for Silverlight 구현을 참조해야 하는 어셈블리입니다.  예를 들어, WPF\(Windows Presentation Foundation\)로 작성된 XAML 디자이너는 디자이너 사용자 인터페이스용 WPF 데스크톱 및 Silverlight구현이 포함된 WPF의 하위 집합을 모두 참조해야 할 수 있습니다.  기본적으로 별도의 참조는 어셈블리 바인딩이 두 어셈블리를 동일하게 간주하기 때문에 컴파일러 오류가 발생합니다.  이 요소는 기본 동작을 비활성화하고 컴파일이 성공하도록 합니다.  
  
> [!IMPORTANT]
>  컴파일러가 공용 언어 런타임의 어셈블리 바인딩 논리에 정보를 전달하려면 `/appconfig` 컴파일러 옵션을 사용하여 이 요소를 포함하는 app.config 파일의 위치를 지정해야 합니다.  
  
## 예제  
 다음 예제에서는 응용 프로그램에서 두 구현에 존재하는 모든 .NET Framework 어셈블리의 .NET Framework 구현 및 .NET Framework for Silverlight 구현을 모두 참조할 수 있습니다.  이 app.config 파일의 위치를 지정하려면 `/appconfig` 컴파일러 옵션을 사용해야 합니다.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## 참고 항목  
 [\/appconfig \(C\# 컴파일러 옵션\)](http://msdn.microsoft.com/library/ee523958.aspx)   
 [.NET Framework Assembly Unification Overview](http://msdn.microsoft.com/ko-kr/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)