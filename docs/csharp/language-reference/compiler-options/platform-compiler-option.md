---
title: "/platform (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/platform"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "platform compiler option [C#]"
  - "-platform compiler option [C#]"
  - "/platform compiler option [C#]"
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
caps.latest.revision: 46
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 46
---
# /platform (C# Compiler Options)
어셈블리를 실행할 수 있는 CLR\(공용 언어 런타임\) 버전을 지정합니다.  
  
## 구문  
  
```  
/platform:string  
```  
  
#### 매개 변수  
 `string`  
 ARM, x86, Itanium, x64 또는 anycpu\(기본값\), 선호된anycpu32비트 입니다.  
  
## 설명  
  
-   **anycpu** \(기본값\)를 사용하면 어셈블리가 모든 플랫폼에서 실행되도록 컴파일됩니다.  응용 프로그램은 가능한 64 비트 프로세스로 실행 하고 모드가 사용 가능 할 때만 32 비트로 떨어질 수 있습니다.  
  
-   **anycpu32bitpreferred**를 지정하면 임의의 플랫폼에서 실행되도록 어셈블리를 컴파일합니다.  응용 프로그램은 64 비트와 32 비트 응용 프로그램이 모두 지원하는 32 비트 모드 시스템에서 실행 됩니다.  .NET Framework 4.5를 대상으로 하는 프로젝트에 대해서만 이 옵션을 지정할 수 있습니다.  
  
-   **ARM** 은 고급 RISC 컴퓨터 \(ARM\) 프로세서를 가진 컴퓨터에서 실행 되도록 어셈블리를 컴파일합니다.  
  
-   **x64** 는 AMD64 또는 EM64T 명령 집합을 지원하는 컴퓨터의 64비트 공용 언어 런타임에서 실행되는 어셈블리를 컴파일 합니다.  
  
-   **x86** 는 32비트, x86 호환 공용 언어 런타임에서 실행되도록 컴파일됩니다.  
  
-   **Itanium** 는 어셈블리가 Itanium 프로세서 탑재 컴퓨터의 64비트 공용 언어 런타임에서 실행되도록 컴파일 합니다.  
  
 64비트 Windows 운영 체제의 경우  
  
-   **\/platform:x86**으로 컴파일된 어셈블리는 WOW64에서 실행되는 32비트 CLR에서 실행됩니다.  
  
-   **\/platform:anycpu** 로 컴파일된 DLL은 이 DLL이 로드된 프로세스와 동일한 CLR에서 실행됩니다.  
  
-   **\/platform:anycpu**로 컴파일된 실행 파일은 64비트 CLR에서 실행됩니다.  
  
-   **\/platform:anycpu32bitpreferred** 로 컴파일된 실행 파일은 32비트 CLR에서 실행됩니다.  
  
 **anycpu32bitpreferred** 설정은 실행 파일인 \(.EXE\) 파일에 대해서만 유효하고, 이것은 .NET Framework 4.5을 필요로 합니다.  
  
 Windows 64비트 운영 체제에서 실행할 응용 프로그램 개발에 대한 자세한 내용은 [64비트 응용 프로그램](../Topic/64-bit%20Applications.md)을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **빌드** 속성 페이지를 클릭합니다.  
  
3.  **플랫폼 대상** 속성을 수정하고, .NET Framework 4.5를 대상으로 하는 프로젝트를 선택 하거나 **선호 32 비트** 확인란을 선택 취소하세요.  
  
 **편지지** Visual C\# Express 개발 환경에서는 **\/platform**을 사용할 수 없습니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>을 참조하십시오.  
  
## 예제  
 다음 예제에서는 **\/platform** 옵션을 사용하여 응용 프로그램이 64비트 Windows 운영 체제의 64비트 CLR에서만 실행되도록 지정하는 방법을 보여 줍니다.  
  
```  
csc /platform:anycpu filename.cs  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)