---
title: "/out (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/out"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/out compiler option [C#]"
  - "out compiler option [C#]"
  - "-out compiler option [C#]"
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /out (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

**\/out** 옵션을 사용하여 출력 파일의 이름을 지정합니다.  
  
## 구문  
  
```  
/out:filename  
```  
  
## 인수  
 `filename`  
 컴파일러가 만드는 출력 파일의 이름입니다.  
  
## 설명  
 명령줄에서 여러 개의 출력 파일을 지정하여 컴파일할 수도 있습니다.  컴파일러는 **\/out** 옵션 다음에 나오는 하나 이상의 소스 코드 파일을 찾습니다.  그런 다음 **\/out** 옵션에 지정된 출력 파일로 모든 소스 코드 파일을 컴파일합니다.  
  
 만들 파일의 전체 이름과 확장명을 지정합니다.  
  
 출력 파일의 이름을 지정하지 않으면,  
  
-   .exe는 **Main** 메서드를 포함하는 소스 코드 파일에서 출력 파일 이름을 가져옵니다.  
  
-   A .dll 또는 netmodule은 첫 번째 소스 코드 파일에서 그 이름을 가져옵니다.  
  
 하나의 출력 파일을 컴파일하는 데 사용된 소스 코드 파일은 동일한 컴파일에서 다른 출력 파일을 컴파일하는 데 사용할 수 없습니다.  
  
 명령줄 컴파일을 통해 여러 개의 출력 파일을 만들 때에는 암시적 또는 명시적으로 **\/out**을 사용하여 지정한 출력 파일 중 첫 번째 출력 파일만 어셈블리가 될 수 있습니다.  
  
 컴파일하는 동안 만들어진 모든 모듈은 해당 컴파일에서 만들어진 모든 어셈블리와 연결된 파일이 됩니다.  어셈블리 매니페스트를 보고 연결된 파일을 확인하려면 [ildasm.exe](../Topic/Ildasm.exe%20\(IL%20Disassembler\).md)를 사용합니다.  
  
 exe가 friend 어셈블리의 대상이 되도록 하려면 \/out 컴파일러 옵션이 필요합니다.  자세한 내용은 [Friend 어셈블리](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **응용 프로그램** 속성 페이지를 클릭합니다.  
  
3.  **어셈블리 이름** 속성을 수정합니다.  
  
     이 컴파일러 옵션을 프로그래밍 방식으로 설정하려면: <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A>은 읽기 전용 속성으로 프로젝트 형식\(exe, 라이브러리 등\)과 어셈블리 이름을 조합하여 만들어집니다.  출력 파일 이름을 설정하려면 이러한 두 속성 중 하나 또는 모두를 수정해야 합니다.  
  
## 예제  
 `t.cs`를 컴파일하여 출력 파일 `t.exe`를 만들고, `t2.cs`를 빌드하여 모듈 출력 파일 `mymodule.netmodule`을 만듭니다.  
  
```  
csc t.cs /out:mymodule.netmodule /target:module t2.cs  
```  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Friend 어셈블리](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)