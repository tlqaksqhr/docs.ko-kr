---
title: "/appconfig (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/appconfig"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/appconfig compiler option [C#]"
ms.assetid: 1cdbcbcc-7813-4010-b5b8-e67c107c5a98
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /appconfig (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

**\/appconfig** 컴파일러 옵션에서는 C\# 응용 프로그램을 사용하여 어셈블리의 응용 프로그램 구성\(app.config\) 파일 위치를 어셈블리의 바인딩 시간에 CLR\(공용 언어 런타임\)로 지정할 수 있습니다.  
  
## 구문  
  
```  
/appconfig:file  
```  
  
## 인수  
 `file`  
 필수적 요소로서,  어셈블리 바인딩 설정을 포함하는 응용 프로그램 구성 파일입니다.  
  
## 설명  
 **\/appconfig** 의 한 사용은 어셈블리가 .NET Framework 버전 및 특정 참조 어셈블리의 Silverlight 버전용 .NET Framework를 동시에 모두 참조해야 하는 고급 시나리오입니다.  예를 들어, WPF\(Windows Presentation Foundation\)로 작성된 XAML 디자이너는 디자이너 사용자 인터페이스용 WPF 데스크톱 및 Silverlight가 포함된 WPF의 하위 집합을 모두 참조해야 할 수 있습니다.  동일한 디자이너 어셈블리가 두 어셈블리에 모두 액세스해야 합니다.  기본적으로 별도의 참조는 어셈블리 바인딩이 두 어셈블리를 동일하게 간주하기 때문에 컴파일러 오류가 발생합니다.  
  
 **\/appconfig** 컴파일러 옵션을 사용하면 다음 예제와 같이 `<supportPortability>` 태그를 사용하여 기본 동작을 비활성화하는 app.config 파일의 위치를 지정할 수 있습니다.  
  
 `<supportPortability PKT="7cec85d7bea7798e" enable="false"/>`  
  
 컴파일러가 파일의 위치를 CLR의 어셈블리 바인딩 논리에 전달합니다.  
  
> [!NOTE]
>  MSBuild\(Microsoft Build Engine\)을 사용하여 응용 프로그램을 빌드하는 경우 속성 태그를 .csproj 파일에 추가하여 **\/appconfig** 컴파일러 옵션을 설정할 수 있습니다.  프로젝트에 이미 설정된 app.config 파일을 사용하려면 `<UseAppConfigForCompiler>` 속성 태그를 .csproj 파일에 추가하고 해당 값을 `true`로 설정합니다.  다른 app.config 파일을 지정하려면 `<AppConfigForCompiler>` 속성 태그를 추가하고 해당 값을 파일 위치로 설정합니다.  
  
## 예제  
 다음 예제에서는 응용 프로그램에서 두 구현에 존재하는 모든 .NET Framework 어셈블리의 .NET Framework 구현 및 .NET Framework for Silverlight 구현을 모두 참조할 수 있는 app.config 파일을 보여 줍니다.  **\/appconfig** 컴파일러 옵션은 이 app.config 파일의 위치를 지정합니다.  
  
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
 [.NET Framework Assembly Unification Overview](http://msdn.microsoft.com/ko-kr/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)   
 [\<supportPortability\> 요소](../Topic/%3CsupportPortability%3E%20Element.md)   
 [C\# Compiler Options Listed Alphabetically](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)