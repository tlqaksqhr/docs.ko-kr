---
title: "/target (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/target"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "target compiler options [C#]"
  - "/target compiler options [C#]"
  - "assemblies [C#], compiling"
  - "-target compiler options [C#]"
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# /target (C# Compiler Options)
**\/target** 컴파일러 옵션은 다음 네 가지 형태 중 하나를 사용하여 지정할 수 있습니다.  
  
 [\/target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
 [!INCLUDE[win8_appname_long](../../../csharp/includes/win8-appname-long-md.md)] 앱에 대한 .exe 파일 만들기.  
  
 [\/target:exe](../../../csharp/language-reference/compiler-options/target-exe-compiler-option.md)  
 .exe 파일을 만듭니다.  
  
 [\/target:library](../../../csharp/language-reference/compiler-options/target-library-compiler-option.md)  
 코드 라이브러리를 만듭니다.  
  
 [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)  
 모듈을 만듭니다.  
  
 [\/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 Windows 프로그램을 만듭니다.  
  
 [\/target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
 중간 .winmdobj 파일 만들기.  
  
 \/**\/target:module**을 지정하지 않으면 **\/target**이 .NET Framework 어셈블리 매니페스트를 출력 파일에 저장합니다.  자세한 내용은 [공용 언어 런타임의 어셈블리](../Topic/Assemblies%20in%20the%20Common%20Language%20Runtime.md) 및 [공통 특성](../Topic/Common%20Attributes%20\(C%23%20and%20Visual%20Basic\).md)을 참조하십시오.  
  
 어셈블리 매니페스트는 컴파일에서 첫 번째 .exe 출력 파일에 저장되거나 .exe 출력 파일이 없는 경우 첫 번째 DLL에 저장됩니다.  예를 들어, 다음 명령줄에서 매니페스트는 `1.exe`에 저장됩니다.  
  
```  
csc /out:1.exe t1.cs /out:2.netmodule t2.cs  
```  
  
 컴파일러에서는 컴파일마다 하나의 어셈블리 매니페스트만 만듭니다.  컴파일할 때 모든 파일에 대한 정보는 어셈블리 매니페스트에 저장됩니다.  **\/target:module**을 사용하여 만든 출력 파일을 제외한 모든 출력 파일은 어셈블리 매니페스트를 가질 수 있습니다.  명령줄에서 여러 출력 파일을 생성하는 경우 하나의 어셈블리 매니페스트만 만들 수 있으며 명령줄에서 지정한 첫 번째 출력 파일에 이를 저장해야 합니다.  첫 번째 출력 파일이 어떤 것이든\(**\/target:exe**, **\/target:winexe**, **\/target:library** 또는 **\/target:module**\) 동일한 컴파일에서 생성된 다른 출력 파일은 모듈이어야 합니다\(**\/target:module**\).  
  
 어셈블리를 만드는 경우 코드의 전체 또는 코드 일부가 <xref:System.CLSCompliantAttribute> 특성이 있는 CLS 규격이 되도록 지정할 수 있습니다.  
  
```  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법은 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>을 참조하십시오.  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [\/subsystemversion \(Specify minimum subsystem version\)](../../../csharp/language-reference/compiler-options/subsystemversion-compiler-option.md)