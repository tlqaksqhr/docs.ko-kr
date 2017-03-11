---
title: "/link (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/l compiler option [C#]"
  - "/link compiler option [C#]"
  - "-l compiler option [C#]"
  - "EmbedInteropTypes"
  - "l compiler option [C#]"
  - "embed interop types [COM Interop]"
  - "-link compiler option [C#]"
  - "link compiler option [C#]"
ms.assetid: 00da70c6-9ea1-43c2-86f2-aa7f26c03475
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# /link (C# Compiler Options)
컴파일러가 현재 컴파일하려는 프로젝트에서 지정된 어셈블리의 COM 형식 정보를 사용할 수 있도록 합니다.  
  
## 구문  
  
```  
/link:fileList  
// -or-  
/l:fileList  
```  
  
## 인수  
 `fileList`  
 필수적 요소로서,  쉼표로 구분된 어셈블리 파일 이름입니다.  파일 이름에 공백이 포함되어 있으면 이름을 따옴표로 묶습니다.  
  
## 설명  
 `/link` 옵션을 사용하여 포함된 형식 정보가 있는 응용 프로그램을 배포할 수 있습니다.  그러면 이 응용 프로그램은 런타임 어셈블리에서 런타임 어셈블리에 대한 참조를 요구하지 않고 포함된 형식 정보를 구현하는 형식을 사용할 수 있습니다.  런타임 어셈블리의 여러 버전을 게시하면 포함된 형식 정보가 있는 응용 프로그램은 다시 컴파일되지 않고도 여러 버전으로 작업할 수 있습니다.  예제를 보려면 [연습: 관리되는 어셈블리의 형식 포함](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
 `/link` 옵션은 COM interop 작업을 수행할 때 특히 유용합니다.  응용 프로그램에서 대상 컴퓨터의 PIA\(기본 interop 어셈블리\)를 더 이상 사용하지 않아도 되도록 COM 형식을 포함할 수 있습니다.  `/link` 옵션은 컴파일러에서 참조된 interop 어셈블리의 COM 형식 정보를 컴파일된 결과 코드에 포함하도록 지시합니다.  COM 형식은 CLSID\(GUID\) 값으로 식별됩니다.  결과적으로 같은 CLSID 값을 가지는 같은 COM 형식이 설치된 대상 컴퓨터에서 응용 프로그램을 실행할 수 있습니다.  Microsoft Office 응용 프로그램을 자동화하는 응용 프로그램이 좋은 예입니다.  Office와 같은 응용 프로그램에서는 대개 다양한 버전에 대해 같은 CLSID 값을 유지하므로 .NET Framework 4 이상이 대상 컴퓨터에 설치되어 있고 응용 프로그램에서 참조된 COM 형식에 포함된 메서드, 속성 또는 이벤트를 사용하는 경우 응용 프로그램에서 참조된 COM 형식을 사용할 수 있습니다.  
  
 `/link` 옵션은 인터페이스, 구조체 및 대리자만 포함합니다.  COM 클래스를 포함하는 기능은 지원되지 않습니다.  
  
> [!NOTE]
>  코드에서 포함된 COM 형식의 인스턴스를 만들려면 적합한 인터페이스를 사용하여 인스턴스를 만들어야 합니다.  CoClass를 사용하여 포함된 COM 형식의 인스턴스를 만들려고 하면 오류가 발생합니다.  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]에서 `/link` 옵션을 설정하려면 어셈블리 참조를 추가하고 `Embed Interop Types` 속성을 **true**로 설정합니다.  `Embed Interop Types` 속성의 기본값은 **false**입니다.  
  
 자체적으로 다른 COM 어셈블리\(Assembly B\)를 참조하는 COM 어셈블리\(Assembly A\)에 연결할 때 다음과 같은 경우에는 Assembly B에도 연결해야 합니다.  
  
-   Assembly A에서 사용하는 형식이 Assembly B의 형식에서 상속되었거나 Assembly B의 인터페이스로 구현된 경우  
  
-   Assembly B의 반환 형식이나 매개 변수 형식의 필드, 속성, 이벤트 또는 메서드를 호출하는 경우  
  
 [\/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) 컴파일러 옵션과 마찬가지로 `/link` 컴파일러 옵션은 자주 사용되는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 어셈블리를 참조하는 Csc.rsp 응답 파일을 사용합니다.  컴파일러에 Csc.rsp 파일을 사용하지 않으려면 [\/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md) 컴파일러 옵션을 사용합니다.  
  
 `/link`의 약식 표현은 `/l`입니다.  
  
## 제네릭 및 포함된 형식  
 다음 단원에서는 interop 형식이 포함된 애플리케이션에서 제네릭 형식을 사용할 때의 제한 사항에 대해 설명합니다.  
  
### 제네릭 인터페이스  
 interop 어셈블리에서 포함된 제네릭 인터페이스는 사용할 수 없습니다.  다음 예제에서 이를 확인할 수 있습니다.  
  
 [!code-cs[VbLinkCompilerCS#1](../../../csharp/language-reference/compiler-options/codesnippet/csharp/vblinkcompilercs/program.cs#1)]  
  
### 제네릭 매개 변수가 있는 형식  
 interop 어셈블리에서 포함된 형식이 외부 어셈블리에서 온 경우 해당 형식의 제네릭 매개 변수를 가지는 형식은 사용할 수 없습니다.  이러한 제한은 인터페이스에 적용되지 않습니다.  예를 들어 <xref:Microsoft.Office.Interop.Excel> 어셈블리에 정의된 <xref:Microsoft.Office.Interop.Excel.Range> 인터페이스를 생각해 볼 수 있습니다.  라이브러리에서 <xref:Microsoft.Office.Interop.Excel> 어셈블리의 interop 형식을 포함한 후 <xref:Microsoft.Office.Interop.Excel.Range> 인터페이스 형식의 매개 변수가 있는 제네릭 형식을 반환하는 메서드를 노출하는 경우 해당 메서드는 다음 코드 예제에서와 같이 제네릭 인터페이스를 반환해야 합니다.  
  
 [!code-cs[VbLinkCompilerCS#2](../../../csharp/language-reference/compiler-options/codesnippet/csharp/vblinkcompilercs/utility.cs#2)]  
[!code-cs[VbLinkCompilerCS#3](../../../csharp/language-reference/compiler-options/codesnippet/csharp/vblinkcompilercs/utility.cs#3)]  
[!code-cs[VbLinkCompilerCS#4](../../../csharp/language-reference/compiler-options/codesnippet/csharp/vblinkcompilercs/utility.cs#4)]  
  
 다음 예제에서 클라이언트 코드는 오류 없이 <xref:System.Collections.IList> 제네릭 인터페이스를 반환하는 메서드를 호출할 수 있습니다.  
  
 [!code-cs[VbLinkCompilerCS#5](../../../csharp/language-reference/compiler-options/codesnippet/csharp/vblinkcompilercs/program.cs#5)]  
  
## 예제  
 다음 코드에서는 소스 파일 `OfficeApp.cs`를 컴파일하고 `COMData1.dll` 및 `COMData2.dll`의 어셈블리를 참조하여 `OfficeApp.exe`를 생성합니다.  
  
```c#  
csc /link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.cs  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [연습: 관리되는 어셈블리의 형식 포함](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [\/reference \(Import Metadata\)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)   
 [\/noconfig \(Ignore csc.rsp\)](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md)   
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)   
 [상호 운용성 개요](../../../csharp/programming-guide/interop/interoperability-overview.md)